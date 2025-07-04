 # Plushie Breathe With Me – Extensions « Jouet Vivant »

    Ce document décrit trois ajouts qui donnent l’illusion d’un compagnon vivant : **battements de cœur**, **chaleur corporelle** et **réactions spontanées**.  
    Chaque section précise le concept, le matériel minimal, ainsi qu’un exemple d’implantation avec un micro‑contrôleur ESP32‑C3 ou Arduino.

    ---

    ## 1. Battements de cœur

    | Élément | Choix recommandé | Prix indicatif |
    |---------|-----------------|----------------|
    | Micro‑contrôleur | ESP32‑C3 DevKit‐M1 | 4 € |
    | Moteur « vibration » | Moteur excentrique 8 mm / 3 V (Ecc‑motor) | 1 € |
    | Pilotage | Transistor NPN 2N2222 + diode roue libre | 0,30 € |
    | Alimentation | 3 × AAA (NiMH) **ou** LiFePO₄ 3,2 V 700 mAh | 3–6 € |

    ```mermaid
    graph TD
      A[ESP32-C3 GPIO] -->|PWM 30–120 bpm| B(Moteur vibreur)
      B --> C[Vibre la coque ABS]
    ```

    1. **Connexion**  
       - GPIO XX → base 2N2222 (via résistance 1 kΩ)  
       - +3 V → moteur → collecteur 2N2222 → GND  
       - Diode 1N4148 en antiparallèle sur le moteur

    2. **Code (extrait)**  
       ```cpp
       const int motor = 18;
       void setup(){{ pinMode(motor, OUTPUT); }}
       void loop(){{
         // battement double « lub‑dub »
         analogWrite(motor, 255); delay(80);
         analogWrite(motor,   0); delay(80);
         analogWrite(motor, 255); delay(80);
         analogWrite(motor,   0); delay(560);   // 75 bpm
       }}
       ```

    3. **Calibration** – Ajuster la durée pour cibler 60–120 bpm selon l’émotion simulée.

    ---

    ## 2. Chaleur corporelle

    | Élément | Choix recommandé | Prix |
    |---------|-----------------|------|
    | Résistance PTC | Film chauffant 5 V / 2 W | 2 € |
    | Capteur température | Thermistance 10 kΩ NTC | 0,20 € |
    | MOSFET | AO3415 ou IRLML2502 | 0,25 € |

    **Implantation**
    1. Coudre une **poche thermo‑isolante** (feutrine + aluminium mince) sous la « poitrine ».  
    2. Coller la PTC sur un dissipateur alu 30 × 30 mm.  
    3. Boucle PID simple : maintenir 35–38 °C.  
    4. **Sécurité** : fusible thermique 50 °C + coupure logicielle à 40 °C.

    ```cpp
    int T = analogRead(NTC);     // conversion en °C
    if (T < 35) heaterOn();
    if (T > 38) heaterOff();
    ```

    ---

    ## 3. Réactions spontanées

    | Capteur | Action | Rendu « vivant » |
    |---------|--------|------------------|
    | Tactile capacitif (CAP1188) | Changer rythme cardiaque | Ralentit quand on caresse |
    | Micro MEMS | Sursaute si on tape dans les mains | Vibration + yeux LED « surpris » |
    | Photodiode | Mode veille lorsque la pièce s’assombrit | Respiration longue + yeux mi‑clos |

    **Machine d’états simple**

    ```mermaid
    stateDiagram-v2
      [*] --> Awake : lumière > 15 lx
      Awake --> Surprised : Clap > 60 dB
      Surprised --> Awake : 3 s
      Awake --> Sleep : inactivité 120 s
      Sleep --> Awake : touche ≠ 0
    ```

    Exemple de boucle (pseudo‑Arduino) :
    ```cpp
    void loop(){{
      updateSensors();
      switch(state){{
        case AWAKE:
           breatheRate = 10; heartbeat = 75;
           if (clap) to(SURPRISED);
           if (inactive) to(SLEEP);
           break;
        case SURPRISED:
           breatheRate = 20; heartbeat = 120; vibrate(200);
           if (millis() - tSurprise > 3000) to(AWAKE);
           break;
        case SLEEP:
           breatheRate = 6; heartbeat = 60;
           if (touched) to(AWAKE);
           break;
      }}
    }}
    ```

    ---

    ## Intégration mécanique

    ```mermaid
    graph LR
       subgraph Shell lavable
         P(Poche chauffe) --- S(Soufflet respiration)
       end
       C((Cœur ABS)) --> V[Moteur vibr.]
       C --> H(PTC + NTC)
       C --> FSR[Capteur CPR]
       C --> CAP[8x Pads tactiles]
    ```

    *Le module ABS (“cœur”) se glisse dans un compartiment ventral fermé par velcro ; extraction en 5 s avant lavage machine.*

    ---

    ## Sécurité & conformité rapide

    1. **EN 71-1** : petites pièces → vis M3 auto‑freinées.  
    2. **EN 71-2** : textile polyester < 30 mm/s à la flamme.  
    3. **EN 71-3** : teintures non toxiques, test migration métaux.  
    4. **Batteries** : pack AAA NiMH ou LiFePO₄ protégé, pas de Li‑ion pouch nus.

    ---

    ## Bill of Materials (v1 proto)

    | Qty | Item | Prix (€) | Sous‑total |
    |-----|------|---------:|-----------:|
    | 1 | ESP32‑C3 DevKit | 4 | 4 |
    | 1 | Vibreur 3 V | 1 | 1 |
    | 1 | Pompe/servo 5 V | 4 | 4 |
    | 1 | Film PTC 5 V 2 W | 2 | 2 |
    | 1 | Thermistance NTC 10 k | 0.2 | 0.2 |
    | 8 | CAP pads (fil inox) | 0.1 | 0.8 |
    | 1 | CAP1188 I²C | 2 | 2 |
    | 1 | FSR 38 mm | 2 | 2 |
    | 1 | Coque ABS imprimée | 3 | 3 |
    | 1 | Peluche 40 cm (sans rembourrage) | 7 | 7 |
    | **Total** |  |  | **26 €** |

    ---

    ## Prochaine étape

    1. Monter le **cœur ABS** avec vibreur + PTC + capteurs.  
    2. Tester la boucle d’états (réactions spontanées).  
    3. Incorporer le soufflet respiration puis affiner le storyboard CPR.

    *Fichier rédigé : 2025-07-04*
