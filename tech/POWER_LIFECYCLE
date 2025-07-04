# 🔋 POWER & LIFECYCLE — Plushie “breathe with me”

> Version : 2025-07-04  
> Auteur : Fabien Buisson (EI — SIREN 988 516 506)

---

## 1 · Objectifs de fonctionnement

| Paramètre | Cible |
|-----------|-------|
| **Rythme de respiration** | 8 cycles/min (sommeil enfant) |
| **Durée d’usage quotidienne** | 1 – 3 h / jour |
| **Autonomie sans recharge** | ≈ 3 semaines |
| **Réanimation** | 2 – 4 pressions “massage cœur” |
| **Mise en veille automatique** (T_pause) | 10 – 60 min d’inactivité (configurable) |
| **Reset minuteur** | Tout mouvement / déplacement léger pendant la phase active |
| **Recharge parentale** | USB-C (Li-ion) — mensuelle |

---

## 2 · Architecture énergétique

| Bloc | Référence & specs | Fonction |
|------|-------------------|----------|
| **Batterie** | 1× 18650 Li-ion 3 000 mAh (≈ 11 Wh) <br>*(option : 21700 5 000 mAh = 18 Wh)* | Réserve longue durée |
| **BMS** | TP4056 + DW01 | Protection charge / décharge |
| **Supercondensateur** | 5 F / 5 V | Stock le pic d’énergie “massage” (boot + pompe) |
| **Micro-dynamo** | 5 V / 0,5 A pic (≈ 2,5 W mécano-élec) | 1 pression ≈ 2–3 J mécaniques → 1 J électriques |
| **MCU ultra-low-power** | nRF52 ou STM32L0 (< 3 µA deep sleep) | Gestion états, PWM pompe, capteurs |
| **Mini-pompe à air** | XZ-05A (5 V / 30 mA, < 35 dB) | Inspiration active ~ 0,3 s |
| **Clapet sortie** | Valve silicone Ø 4 mm (umbrella) | Expiration passive silencieuse |
| **Capteurs** | • Interrupteur de pression (“cœur”) <br>• Accéléromètre 3-axes (reset minuteur) | Déclenche réanimation + reset activité |


---

## 3 · Cycle d’activité

| État | Déclencheur | Conso typique | Description |
|------|-------------|--------------|-------------|
| **SLEEP profond** | — | < 10 µA | Tous modules OFF, MCU deep-sleep |
| **WAKE-UP** | 2–4 pressions “massage cœur” (dynamo) | Pic 100 mA (1 s) | Le supercondo monte à 4–5 V, MCU boote |
| **RESPIRATION active** | MCU PWM pompe 0,15 W <br>+ LED cœur | 1 – 3 h | 8 resp./min (0,3 s IN) <br>Expiration clapet |
| **RESET T_pause** | Mouvement détecté (accéléro) | +0 s | Le minuteur d’inactivité repart à zéro |
| **PAUSE auto** | Inactivité > `T_pause` | Retour SLEEP | Pompe OFF, MCU deep-sleep |

---

## 4 · Dimensionnement autonomie

### Consommation moyenne

- Pompe + MCU actif : **0,15 W**  
- Veille profonde : **≈ 0,007 Wh/j**

| Usage quotidien | Énergie/jour | Énergie/21 j |
|-----------------|-------------|--------------|
| 1 h respiration | 0,15 Wh | 3,1 Wh |
| 3 h respiration | 0,45 Wh | 9,4 Wh |

### Batterie nécessaire

| Batterie | Énergie utile | Autonomie @ 1 h/j | Autonomie @ 3 h/j |
|----------|---------------|-------------------|-------------------|
| **18650 3 000 mAh** | 11 Wh | 73 j | 24 j |
| **21700 5 000 mAh** | 18 Wh | 120 j | 40 j |

→ **1×18650 suffit** pour 3 semaines même à 3 h/j, avec marge.

---

## 5 · Interaction utilisateur

1. **Réanimation**  
   - 2–4 pressions verticales (≈ 3 cm) sur le “cœur” → la dynamo génère ~4 J → MCU ON → respiration démarre.
2. **Jeu / utilisation active**  
   - Tant que l’enfant câline ou déplace le doudou, le minuteur `T_pause` se réinitialise.
3. **Veille automatique**  
   - Après 10–60 min sans mouvement, le système s’endort pour économiser la batterie.  
   - LED cœur → fade out.
4. **Recharge parentale**  
   - USB-C 5 V ; une charge complète ≈ 3 h (courant 1 A).

---

## 6 · Sécurité & normes

| Exigence | Mesure |
|----------|--------|
| **EN 71-1** (mécanique) | Coutures > 70 N, aucune petite pièce libre |
| **EN 71-3** (chimique) | Tissus OEKO-TEX®, encres non toxiques |
| **EN 71-11** (son) | < 40 dB @ 30 cm |
| Sur-température pompe | Duty-cycle limit, coupure si T° > 45 °C |
| Accès batterie | Trappe vissée “Parent only” |

---

## 7 · Prochaines étapes R&D

1. Tester **pompe XZ-05A** : débit, bruit, courant réel.  
2. Imprimer **module dynamo + crémaillère** (PLA).  
3. Développer **firmware états + réglage `T_pause`**.  
4. Logger autonomie réelle (tension batterie vs temps).  
5. Pré-check conformité EN 71 (liste matières, bruit).

---

# 🔋 POWER & LIFECYCLE — Plushie “breathe with me”

> Version: 2025‑07‑04  
> Author: Fabien Buisson (EI — SIREN 988 516 506)

---

## 1 · Operating Targets

| Parameter | Target |
|-----------|--------|
| **Breathing rate** | 8 cycles / min (child sleep) |
| **Daily usage time** | 1 – 3 h / day |
| **Autonomy without recharge** | ≈ 3 weeks |
| **Resuscitation** | 2 – 4 “heart‑massage” presses |
| **Auto‑sleep timeout** (`T_pause`) | 10 – 60 min inactivity (configurable) |
| **Timer reset** | Any slight movement during active phase |
| **Parental recharge** | USB‑C (Li‑ion) — monthly |

---

## 2 · Power Architecture

| Block | Reference & specs | Function |
|-------|-------------------|----------|
| **Battery** | 1× 18650 Li‑ion 3 000 mAh (≈ 11 Wh) <br>*option: 21700 5 000 mAh = 18 Wh* | Long‑term reserve |
| **BMS** | TP4056 + DW01 | Charge / discharge protection |
| **Super‑capacitor** | 5 F / 5 V | Stores “massage” energy peak (boot + pump) |
| **Micro‑dynamo** | 5 V / 0.5 A peak (≈ 2.5 W mech‑elec) | 1 press ≈ 2–3 J mechanical → 1 J electrical |
| **Ultra‑low‑power MCU** | nRF52 or STM32L0 (< 3 µA deep sleep) | State handling, pump PWM, sensors |
| **Mini air pump** | XZ‑05A (5 V / 30 mA, < 35 dB) | Active inhalation ~ 0.3 s |
| **Outlet valve** | Ø 4 mm silicone umbrella valve | Silent passive exhalation |
| **Sensors** | • Pressure switch (“heart”) <br>• 3‑axis accelerometer (timer reset) | Triggers resuscitation + activity reset |

---

## 3 · Activity Cycle

| State | Trigger | Typical draw | Description |
|-------|---------|--------------|-------------|
| **Deep SLEEP** | — | < 10 µA | All modules OFF, MCU deep‑sleep |
| **WAKE‑UP** | 2–4 “heart‑massage” presses (dynamo) | Peak 100 mA (1 s) | Super‑cap rises to 4–5 V, MCU boots |
| **Active BREATHING** | MCU PWM pump 0.15 W <br>+ heart LED | 1 – 3 h | 8 breaths/min (0.3 s IN) <br>Exhalation valve |
| **RESET `T_pause`** | Movement detected (accelerometer) | +0 s | Inactivity timer resets |
| **Auto‑PAUSE** | Inactivity > `T_pause` | Back to SLEEP | Pump OFF, MCU deep‑sleep |

---

## 4 · Autonomy Sizing

### Average consumption

- Pump + MCU active: **0.15 W**  
- Deep sleep: **≈ 0.007 Wh/day**

| Daily usage | Energy/day | Energy/21 d |
|-------------|-----------|-------------|
| 1 h breathing | 0.15 Wh | 3.1 Wh |
| 3 h breathing | 0.45 Wh | 9.4 Wh |

### Required battery

| Battery | Usable energy | Autonomy @ 1 h/day | Autonomy @ 3 h/day |
|---------|---------------|--------------------|--------------------|
| **18650 3 000 mAh** | 11 Wh | 73 d | 24 d |
| **21700 5 000 mAh** | 18 Wh | 120 d | 40 d |

→ **One 18650 is enough** for 3 weeks even at 3 h/day, with margin.

---

## 5 · User Interaction

1. **Resuscitation**  
   - 2–4 vertical presses (~ 3 cm) on the “heart” → dynamo generates ~ 4 J → MCU ON → breathing starts.  
2. **Play / active use**  
   - As long as the child cuddles or moves the plush, the `T_pause` timer resets.  
3. **Auto‑sleep**  
   - After 10–60 min without movement, the system sleeps to save battery.  
   - Heart LED → fade out.  
4. **Parental recharge**  
   - USB‑C 5 V; full charge ≈ 3 h (1 A current).

---

## 6 · Safety & Standards

| Requirement | Measure |
|-------------|---------|
| **EN 71‑1** (mechanical) | Seams > 70 N, no loose small parts |
| **EN 71‑3** (chemical) | OEKO‑TEX® fabrics, non‑toxic inks |
| **EN 71‑11** (sound) | < 40 dB @ 30 cm |
| Pump over‑temperature | Duty‑cycle limit, cut‑off if T > 45 °C |
| Battery access | Screwed “Parent only” hatch |

---

## 7 · Next R&D Steps

1. Test **pump XZ‑05A**: flow, noise, actual current.  
2. Print **dynamo + rack module** (PLA).  
3. Develop **firmware states + adjustable `T_pause`**.  
4. Log real autonomy (battery voltage vs time).  
5. Preliminary EN 71 compliance check (materials list, noise).
