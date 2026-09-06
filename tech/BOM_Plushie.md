<!--
© 2025 Fabien Buisson — Plushie “Breathe-With-Me”
=================================================
Dual licence :
• Code: MIT  
• Docs & media: CC BY-NC-SA 4.0  
Non-commercial use is free of charge with attribution.

➡️  Commercial use
Commercial use of the hardware design is allowed under CERN-OHL-S 2.0 with the
share-alike obligation. Commercial use of the documentation and media is outside
CC BY-NC-SA 4.0 and is handled case by case by e-mail. Nothing is sold.

By using this file you agree to the terms detailed in
`governance/DUAL_LICENSE.md`.
Contact : scgfamp@hotmail.com
-->

# 📦 Plushie Prototype — Bill of Materials & EU Standards  
*Version: July 2025*

Prototype couvrant : respiration gonflable, réanimation CPR, clignement mécanique des yeux.  
Tous prix au détail (€), sans pièces recyclées. Inclut les éléments de sécurité (câblage, fusible, cage, amortisseur bruit).

| # | Composant | Fonction | Fournisseur | Qté | PU € | Total € |
|---|-----------|----------|-------------|----:|-----:|--------:|
| 1 | Arduino Pro Mini 5 V 16 MHz | Microcontrôleur | AliExpress | 1 | 2.60 | 2.60 |
| 2 | Pompe DC 370 3 V | Actuateur respiration | AliExpress | 1 | 1.80 | 1.80 |
| 3 | Poire silicone 45 mm | « Poumon » manuel | BV Medical | 1 | 10.20 | 10.20 |
| 4 | Clapet anti-retour 3/16″ | Stop reflux air | Amazon | 1 | 0.37 | 0.37 |
| 5 | Tube silicone Ø 3 mm ID 1 m | Conduit air | Générique | 1 | 1.50 | 1.50 |
| 6 | FSR Ø 38 mm (Interlink) | Détection pression CPR | DigiKey | 1 | 6.70 | 6.70 |
| 7 | MOSFET IRLZ44N | Pilotage pompe | Amazon | 1 | 0.83 | 0.83 |
| 8 | 18650 3400 mAh protected | Batterie Li-ion | Amazon | 1 | 4.74 | 4.74 |
| 9 | TP4056 USB charger | Charge batterie | AliExpress | 1 | 0.09 | 0.09 |
| 10 | MT3608 boost 5 V | Rail 5 V MCU/servo | Joom | 1 | 1.40 | 1.40 |
| 11 | Super-condensateur 5 F 5.5 V | Buffer pompe | DigiKey | 1 | 4.18 | 4.18 |
| 12 | Servo SG90 9 g × 2 | Paupières | AliExpress | 2 | 2.50 | 5.00 |
| 13 | Tissu Minky 0,3 m | Peau externe | Mondial Tissus | 0.3 m | 2.73 | 0.82 |
| 14 | Ouate polyester 250 g | Rembourrage | Mondial Tissus | 1 | 8.99 | 8.99 |
| 15 | JST XH-2 (pack) | Connectique interne | DigiKey | 3 | 0.09 | 0.27 |
| 16 | Fil silicone AWG26 1 m | Câblage souple | AliExpress | 1 | 0.40 | 0.40 |
| 17 | Gaine thermo 2 mm 1 m | Isolation | AliExpress | 1 | 0.10 | 0.10 |
| 18 | Silent-blocks 10 × 5 mm (4) | Amortir pompe | Amazon | 1 | 0.80 | 0.80 |
| 19 | Vis M2×6 inox (20) | Fixations | AliExpress | 1 | 0.60 | 0.60 |
| 20 | Polyfuse PTC 2 A | Protection batterie | DigiKey | 1 | 0.22 | 0.22 |
| 21 | Cage PETG 3D 10 g | Protection électronique | Imprimé | 1 | 0.25 | 0.25 |
| **—** | **TOTAL** | | | | | **51.86 €** |

## 🏷️ Normes européennes à vérifier

- **Directive Jouets 2009/48/CE**  
  - EN 71-1 : Sécurité mécanique  
  - EN 71-2 : Inflammabilité  
  - EN 71-3 : Migration d’éléments  
- **EN IEC 62115 :2020** – Jouets électriques ≤ 24 V  
- **EN 62133-2** – Batteries lithium rechargeables  
- **ETSI EN 301 489-1 / 489-17** – Compatibilité électromagnétique (moteur/servo)  
- **EN 71-1 § 4.21** – Pression acoustique < 80 dB (A) (pompe ≈ 50 dB avec silent-block)  
- **Directive 2011/65/UE (RoHS)** – Composants listés conformes  

> **Remarque :** Les tests physiques (traction des coutures, cycles pompe, température batterie) doivent être documentés dans le dossier technique avant apposition du marquage **CE**.

---

Prototype features: inflatable breathing, CPR-feedback, mechanical eye-blink.  
All prices are retail (EUR) with no recycled parts. Safety extras included
(wiring, fuse, cage, vibration damping).

| # | Component | Function | Supplier | Qty | Unit € | Total € |
|---|-----------|----------|----------|----:|-------:|--------:|
| 1 | Arduino Pro Mini 5 V 16 MHz | Micro-controller | AliExpress | 1 | 2.60 | 2.60 |
| 2 | DC Pump 370 3 V | Breathing actuator | AliExpress | 1 | 1.80 | 1.80 |
| 3 | Silicone bulb Ø 45 mm | Manual “lung” | BV Medical | 1 | 10.20 | 10.20 |
| 4 | Check valve 3/16″ | Air back-flow stop | Amazon | 1 | 0.37 | 0.37 |
| 5 | Silicone tube Ø 3 mm ID 1 m | Air conduit | Generic | 1 | 1.50 | 1.50 |
| 6 | FSR Ø 38 mm Interlink | CPR pressure sensor | DigiKey | 1 | 6.70 | 6.70 |
| 7 | MOSFET IRLZ44N | Pump driver | Amazon | 1 | 0.83 | 0.83 |
| 8 | 18650 3400 mAh protected | Li-ion battery | Amazon | 1 | 4.74 | 4.74 |
| 9 | TP4056 charger board | Battery charging | AliExpress | 1 | 0.09 | 0.09 |
|10 | MT3608 5 V booster | 5 V rail MCU/servo | Joom | 1 | 1.40 | 1.40 |
|11 | Super-capacitor 5 F 5.5 V | Pump in-rush buffer | DigiKey | 1 | 4.18 | 4.18 |
|12 | SG90 9 g servo × 2 | Eyelids | AliExpress | 2 | 2.50 | 5.00 |
|13 | Minky fabric 0.3 m | Outer skin | Mondial Tissus | 0.3 | 2.73 | 0.82 |
|14 | Polyester stuffing 250 g | Filling | Mondial Tissus | 1 | 8.99 | 8.99 |
|15 | JST XH-2 pack | Internal connectors | DigiKey | 3 | 0.09 | 0.27 |
|16 | Silicone wire AWG26 1 m | Flexible wiring | AliExpress | 1 | 0.40 | 0.40 |
|17 | Heat-shrink 2 mm 1 m | Joint insulation | AliExpress | 1 | 0.10 | 0.10 |
|18 | Silent-blocks 10 × 5 mm (4) | Pump damping | Amazon | 1 | 0.80 | 0.80 |
|19 | M2 × 6 mm inox screws (20) | Fixings | AliExpress | 1 | 0.60 | 0.60 |
|20 | PTC poly-fuse 2 A | Battery over-current | DigiKey | 1 | 0.22 | 0.22 |
|21 | PETG 3D-printed cage 10 g | Electronics shield | Self-print | 1 | 0.25 | 0.25 |
|—| **TOTAL** | | | | | **51.86 €** |

## 🏷️ EU standards to be verified

- **Toy Safety Directive 2009/48/EC**  
  - EN 71-1 — Mechanical & physical safety  
  - EN 71-2 — Flammability  
  - EN 71-3 — Migration of certain elements  
- **EN IEC 62115 :2020** — Electrical toys ≤ 24 V  
- **EN 62133-2** — Rechargeable lithium batteries  
- **ETSI EN 301 489-1 / 489-17** — EMC (motor/servo)  
- **EN 71-1 § 4.21** — Acoustic level < 80 dB(A) (pump ≈ 50 dB with silent-blocks)  
- **RoHS Directive 2011/65/EU** — Listed components compliant  

> **Note:** Physical tests (seam traction, pump cycles, battery temperature)
> must be documented in the technical file before **CE** marking.

---
