# ecmocalculators

Calcolatori ECMO in HTML statico, senza dipendenze: si aprono direttamente in Chrome.

| File | Contenuto |
|---|---|
| `index.html` | Indice dei calcolatori |
| `flussi-cannule.html` | Ripartizione di Qb tra cannule di drenaggio e di rientro in parallelo |
| `portata-vti-lvot.html` | Portata cardiaca e indici da VTI LVOT ecocardiografico |

## Ripartizione flussi tra cannule

- Resistenza relativa da Poiseuille: R ∝ L / ID⁴, con ID = Fr/3 − 2 × spessore parete.
- Drenaggio: gradiente comune PVC − P1, Qb ripartito per 1/R.
- Rientro: gradiente P3 − PAM (arterioso) o P3 − PVC (venoso); Qᵢ ∝ (ΔPᵢ/Rᵢ)^(1/n), normalizzato a Qb.
- Esponente n regolabile (1 = laminare, ~1,75 = quota turbolenta).

Limiti: stima d'ordine di grandezza. P3 è misurata prima di linee e Y; fori laterali, punta e connettori sono ignorati. Per uso clinico tarare sulle curve ΔP/flusso del produttore.

## Portata da VTI LVOT

- CSA = π·(D/2)²; GS = CSA × VTI; GC = GS × FC.
- Indicizzazione su BSA Mosteller (DuBois per confronto).
- Default: VTI 18 cm, D 2,0 cm, FC 80; maschio 170 cm/70 kg, femmina 160 cm/60 kg.
- Sensibilità: variazione % di GS per ±1 mm di D; minute distance (VTI × FC) indipendente dal diametro.

Limiti: in VA-ECMO il VTI LVOT misura solo l'eiezione nativa, il flusso di circuito non è incluso. Soglia GSi < 35 mL/m² mutuata dal basso flusso nella stenosi aortica (ESC/ASE).
