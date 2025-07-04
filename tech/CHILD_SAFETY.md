# 🛡️ CHILD_SAFETY.md  
Plushie – breathe with me

_Version : 2025-07-xx – Auteur : Fabien Buisson_

---

## 1 · Référentiels normatifs

| Norme | Domaine | Objectif pour le projet |
|-------|---------|-------------------------|
| **EN 71-1** | Propriétés mécaniques & physiques | Pas d’arêtes coupantes, aucune petite pièce détachable < ø 31,7 mm, résistance coutures ≥ 70 N. |
| **EN 71-2** | Inflammabilité | Tissu retardateur : propagation flamme < 30 mm/s. |
| **EN 71-3** | Migration éléments chimiques | Tissus OEKO-TEX® 100, fils & encres certifiés sans métaux lourds. |
| **EN 71-11** | Son émis par jouet | < 40 dB(A) à 30 cm (pompe + clapet). |
| **EN 62115 / EN IEC 61558** | Jouets électriques (basse tension) | T° < 45 °C sur surface accessible, isolation batterie conforme. |

---

## 2 · Conception mécanique

| Point | Mesure concrète |
|-------|-----------------|
| **Boîtier électronique** | Bloc ABS imprimé / moulé **vissé (2 × M2.5)**, tête de vis cruciforme cachée sous un rabat tissu → ouverture réservée à l’adulte. |
| **Trappe batterie** | Marquage « Parent only », 2 vis, joint mousse pour éviter accès liquide. |
| **Accès pompe / clapets** | Ensemble encapsulé dans le boîtier ; aucun tube libre accessible. |
| **Coutures structurelles** | Fil polyester haute ténacité, surpiqûre triple, traction ≥ 70 N. |
| **Poids total** | Objectif < 300 g (18650 ≈ 46 g, pompe ≈ 25 g, boîtier ≈ 40 g, reste = ouate). |
| **Volume ballon** | Ø ≤ 8 cm, pression interne max < 15 kPa. |
| **Choc & chute** | Test 1 m chute sur sol parquet : aucune pièce ne se détache. |

---

## 3 · Sécurité électrique / thermique

| Risque | Mesure |
|--------|--------|
| Surchauffe | MCU coupe la pompe si T° boîtier > 45 °C. |
| Court-circuit batterie | BMS DW01 + MOSFET 8205A : OVP 4,25 V, UVP 2,5 V, OCP 3 A. |
| Recharge | Module USB-C 5 V/1 A (TP4056) avec indicateur LED rouge/verte. |
| ESD | Joint silicone + PCB vernis Conformal Coating. |

---

## 4 · Bruit & confort

- **Mesure visée** : 35 dB(A) max à 30 cm (pompe XZ-05A @ PWM 30 mA).  
- Tests à effectuer dans une pièce < 25 dB(A) fond.  
- **Plan B** : mousse acoustique 3 mm autour du boîtier si > 38 dB.

---

## 5 · Lavage & entretien

| Procédure | Détail |
|-----------|--------|
| **Déconnexion rapide** | Avant toute manipulation, **débrancher** :<br>• le connecteur JST « LED / Yeux »<br>• le raccord rapide du **tube ballon** (push-fit 4 mm). |
| **Retrait bloc interne** | Boîtier (batterie + pompe + MCU) maintenu par 2 vis M2.5. Après déconnexion des deux câbles ci-dessus, le bloc sort en < 30 s. |
| **Lavage peluche** | Housse extérieure **déhoussable** (zip caché) ; lavage 30 °C cycle délicat, essorage ≤ 800 tr/min. |
| **Séchage** | À plat 24 h, pas de sèche-linge (risque de rétrécissement). |
| **Remontage** | Replacer le bloc, revisser, rebrancher les connecteurs (clics audibles) ; vérifier que le tube est bien emboîté jusqu’au verrou. |
| **Notice parent** | PDF + étiquette tissu avec pictogrammes : ① Débrancher LED/yeux ② Débrancher tube ballon ③ Retirer module ④ Laver housse ⑤ Réassembler. |


---

## 6 · Tests à planifier (Checklist)

1. **Traction couture** → dynamomètre 70 N.  
2. **Chute** → 5 × 1 m.  
3. **Bruit** → sonomètre smartphone + calibrateur.  
4. **Température boîtier** après 3 h respiration.  
5. **Ouverture trappe batterie** → tournevis only, < 60 s adulte, impossible enfant < 3 ans.  
6. **Lavabilité** : 5 cycles sans dégradation fermeture/zip.  

---

## 7 · Mise à jour & traçabilité

- Numéro de lot + date assemblage imprimés dans le boîtier.  
- Historique des tests conservé dans `/docs/test-reports/`.  
- Mise à jour du présent document à chaque changement de matériau ou composant.

---

*Ce fichier constitue le référentiel sécurité de la version prototype ; il sera complété après essais laboratoire.*

---

# 🛡️ CHILD_SAFETY.md  
Plushie – breathe with me

_Version: 2025-07-xx – Author: Fabien Buisson_

---

## 1 · Regulatory References

| Standard | Scope | Project target |
|----------|-------|----------------|
| **EN 71‑1** | Mechanical & physical properties | No sharp edges, no detachable small part < ø 31.7 mm, seam strength ≥ 70 N |
| **EN 71‑2** | Flammability | Flame‑spread < 30 mm s⁻¹ (retardant fabric) |
| **EN 71‑3** | Migration of chemical elements | OEKO‑TEX® 100 fabrics, certified threads & inks free of heavy metals |
| **EN 71‑11** | Sound emitted by toy | < 40 dB(A) at 30 cm (pump + valve) |
| **EN 62115 / EN IEC 61558** | Electrical toys (low voltage) | Surface T° < 45 °C, battery insulation compliant |

---

## 2 · Mechanical Design

| Point | Concrete measure |
|-------|------------------|
| **Electronic enclosure** | ABS block (3‑D printed / molded) **screwed (2 × M2.5)**, cross‑head screws hidden under a fabric flap → adult‑only access |
| **Battery hatch** | Marked “Parent only”, 2 screws, foam gasket to keep liquids out |
| **Pump / valve access** | Assembly encapsulated inside the enclosure; no loose tube accessible |
| **Structural seams** | High‑tenacity polyester thread, triple top‑stitch, traction ≥ 70 N |
| **Total weight** | Target < 300 g (18650 ≈ 46 g, pump ≈ 25 g, enclosure ≈ 40 g, rest = stuffing) |
| **Bladder volume** | Ø ≤ 8 cm, internal pressure max < 15 kPa |
| **Shock & drop** | 1 m drop on wooden floor: no parts detach |

---

## 3 · Electrical / Thermal Safety

| Risk | Mitigation |
|------|-----------|
| Over‑temperature | MCU shuts pump off if case T° > 45 °C |
| Battery short‑circuit | BMS DW01 + MOSFET 8205A: OVP 4.25 V, UVP 2.5 V, OCP 3 A |
| Charging | USB‑C 5 V / 1 A module (TP4056) with red/green LED |
| ESD | Silicone gasket + conformal‑coated PCB |

---

## 4 · Noise & Comfort

- **Target:** 35 dB(A) max at 30 cm (pump XZ‑05A @ PWM 30 mA)  
- Tests carried out in a room with < 25 dB(A) background noise  
- **Plan B:** 3 mm acoustic foam around the enclosure if > 38 dB

---

## 5 · Washing & Maintenance

| Procedure | Detail |
|-----------|--------|
| **Quick disconnect** | Before any handling, **unplug**:<br>• “LED / Eyes” JST connector<br>• **Balloon tube** quick coupling (4 mm push‑fit) |
| **Internal block removal** | Enclosure (battery + pump + MCU) held by 2 × M2.5 screws. After the two plugs above are disconnected the block comes out in < 30 s |
| **Plush washing** | Outer cover **removable** (hidden zip); wash 30 °C delicate, spin ≤ 800 rpm |
| **Drying** | Flat for 24 h, no tumble dryer (shrink risk) |
| **Re‑assembly** | Put the block back, screw, reconnect the plugs (audible clicks); ensure tube is fully seated to the lock |
| **Parent notice** | PDF + fabric label with pictograms: ① Unplug LED/eyes ② Unplug balloon tube ③ Remove module ④ Wash cover ⑤ Reassemble |

---

## 6 · Tests to Plan (Checklist)

1. **Seam traction** → dynamometer 70 N  
2. **Drop** → 5 × 1 m  
3. **Noise** → smartphone sound meter + calibrator  
4. **Case temperature** after 3 h breathing  
5. **Battery hatch opening** → screwdriver only, < 60 s adult, impossible for child < 3 yrs  
6. **Washability** → 5 cycles without zipper / fabric degradation  

---

## 7 · Updates & Traceability

- Lot number + assembly date printed inside the enclosure  
- Test history stored in `/docs/test-reports/`  
- This document is updated whenever a material or component changes  

---

*This file is the safety reference for the prototype version; it will be completed after laboratory tests.*
