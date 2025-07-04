# ⚙️ Fonctionnement de Plushie - breathe with me

Le Doudou est conçu pour simuler une **respiration rythmée**, apportant un **réconfort émotionnel et tactile** à l’enfant à travers des cycles réalistes d’**inspiration et d’expiration**. Un système interne composé d’un ballon souple, d’un circuit d’air unidirectionnel et d’un mécanisme d’activation alimenté par une micro-dynamo, supercondensateur et batterie permet d’imiter le souffle naturel, de façon passive et douce.

Mais l’innovation majeure du Doudou réside dans sa **capacité à "s’arrêter de respirer"** et à pouvoir être **réanimé manuellement**. Si le doudou cesse toute activité (par exemple après une longue période d'inutilisation), un **massage cardiaque doux** exercé sur la zone du cœur relance la dynamo et permet au cycle respiratoire de reprendre. Ce mécanisme rend l’objet **interactif et éducatif**, en sensibilisant l’enfant aux gestes de premiers secours dans une logique ludique et symbolique.

Cette fonctionnalité de **réanimation simulée** donne vie au Doudou, en renforçant le lien affectif et en favorisant une **prise de conscience précoce de l'importance de prendre soin de l’autre**.

---

## 🔋 Énergie embarquée

- Le système est **alimenté par une batterie Li-ion**, elle-même réveillée grâce à une micro-dynamo.
- Cette dynamo est **activée par 2 - 4 pressions manuelles** sur la zone du "cœur" du Doudou (massage cardiaque).
- L’énergie générée permet d’actionner :
  - un **Supercondensateur** qui stocke le coup de fouet pour réveiller l’électronique et lancer :
    - une **pompe inspirante miniature** pour gonfler le ballon interne,
    - un **petit circuit de contrôle** (clignement des yeux, rythme…).

Quand inutiliser pendant x temps :
- Le Doudou cesse de respirer (comme endormi).
- L’utilisateur doit **réactiver la dynamo** pour "le réveiller".

---

## 🌬️ Respiration simulée (inspiration/expiration)

- **Inspiration :**
  - L’énergie de la batterie alimente une **pompe** qui remplit un **ballon souple** à l’intérieur du Doudou.
  - Clapet entrée intégré à la pompe : empêche l’air de refluer.

- **Expiration :**
  - Clapet sortie silicone (umbrella) : s’ouvre dès que la pression interne dépasse ~2 kPa → **expiration douce et silencieuse**.

- **Blocage alterné entrée/sortie :**
  - L’entrée est **automatiquement bloquée** pendant la phase d’expiration, et inversement, assurant un cycle respiratoire fluide.

---

Pression → Dynamo → Supercondo → MCU (+ batterie) → Pompe → Ballon → Clapet.

---

## 👁️ Clignement des yeux (optionnel)

- Un **capteur de lumière** permet de déclencher le clignement régulier des yeux du Doudou (ex. toutes les 20 sec).
- Ce module consomme peu et fonctionne tant que la batterie à de l’énergie et que le système n'est pas en veille.

---

# ⚙️ How Plushie – breathe with me Works

The Plushie is designed to simulate **rhythmic breathing**, providing **emotional and tactile comfort** to the child through realistic cycles of **inhalation and exhalation**.  
An internal system made up of a flexible bladder, a one‑way air circuit and an activation mechanism powered by a micro‑dynamo, super‑capacitor and battery gently imitates natural breathing in a passive way.

The key innovation of the Plushie lies in its **ability to “stop breathing”** and be **manually resuscitated**.  
If the plush stops all activity (for example after a long period of disuse), a **gentle chest massage** on the heart area spins the dynamo and allows the breathing cycle to resume. This mechanism makes the object **interactive and educational**, familiarising the child with first‑aid gestures in a playful, symbolic manner.

This **simulated resuscitation** feature brings the Plushie to life, strengthening the emotional bond and fostering an **early awareness of the importance of caring for others**.

---

## 🔋 On‑board Energy

- The system is **powered by a Li‑ion battery**, which is itself awakened via a micro‑dynamo.  
- This dynamo is **activated by 2–4 manual presses** on the Plushie’s “heart” area (chest massage).  
- The generated energy does the following:  
  - Charges a **super‑capacitor** that stores the initial surge to wake up the electronics and start:  
    - a **mini inhalation pump** to inflate the internal bladder,  
    - a **small control circuit** (eye blinking, rhythm, etc.).

When the toy has been unused for a set period:  
- The Plushie stops breathing (as if asleep).  
- The user must **reactivate the dynamo** to “wake it up”.

---

## 🌬️ Simulated Breathing (Inhalation / Exhalation)

- **Inhalation:**  
  - Battery energy powers the **pump** that fills a **flexible bladder** inside the Plushie.  
  - An intake check valve integrated into the pump prevents backflow.

- **Exhalation:**  
  - A **silicone umbrella outlet valve** opens as soon as internal pressure exceeds ~2 kPa → **soft, silent exhalation**.

- **Alternating inlet/outlet blocking:**  
  - The inlet is **automatically blocked** during exhalation and vice versa, ensuring a smooth breathing cycle.

---

Pressure → Dynamo → Super-capacitor → MCU (+ battery) → Pump → Bladder → Valve.

---

## 👁️ Eye Blinking (Optional)

- A **light sensor** triggers regular blinking of the Plushie’s eyes (e.g. every 20 s).  
- This module consumes little power and works as long as the battery has power and the system is not in standby mode.

