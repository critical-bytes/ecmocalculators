# ecmocalculators

Calcolatori ECMO in HTML statico, senza dipendenze: si aprono direttamente in Chrome.

| File | Contenuto |
|---|---|
| `index.html` | Indice dei calcolatori |
| `flussi-cannule.html` | Ripartizione di Qb tra cannule di drenaggio e di rientro in parallelo |
| `portata-vti-lvot.html` | Portata cardiaca e indici da VTI LVOT ecocardiografico |
| `ricircolo-vv.html` | Frazione di ricircolo in VV-ECMO con il metodo a saturazioni |

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

## Ricircolo in VV-ECMO

- R = (SpreO₂ − SvO₂)/(SpostO₂ − SvO₂), frazione 0–1; Qrec = Qb·R; Qeff = Qb·(1 − R).
- Notazione come Badulak 2024 (ELSO): ML/NL, pre/post-ML, FdO₂. SvO₂ qui è il sangue venoso prima della miscela con il rientro, non il prelievo in arteria polmonare.
- Fonte di SvO₂ dichiarata (EGA venoso centrale pre-avvio, sweep spento con sensore pre-ML, CVC a flusso attivo, altro) con la direzione attesa dell'errore su R.
- Sensibilità di R a SvO₂ ± 5 punti; V̇O₂ML con Hb (e O₂ disciolto se si inseriscono le P); Qb/GC e Qeff/GC se GC è noto; criterio di Locker 2003.
- Riepilogo copiabile.

Limiti: il metodo dipende interamente da SvO₂; le saturazioni ignorano l'O₂ disciolto post-ML e tendono a sovrastimare R rispetto ai contenuti. La soglia del 10% viene da misure con diluizione a ultrasuoni.
