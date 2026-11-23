# ecmocalculators

Calcolatori ECMO in HTML statico, senza dipendenze: si aprono direttamente in Chrome.

| File | Contenuto |
|---|---|
| `index.html` | Indice dei calcolatori |
| `flussi-cannule.html` | Ripartizione di Qb tra cannule di drenaggio e di rientro in parallelo |

## Ripartizione flussi tra cannule

- Resistenza relativa da Poiseuille: R ∝ L / ID⁴, con ID = Fr/3 − 2 × spessore parete.
- Drenaggio: gradiente comune PVC − P1, Qb ripartito per 1/R.
- Rientro: gradiente P3 − PAM (arterioso) o P3 − PVC (venoso); Qᵢ ∝ (ΔPᵢ/Rᵢ)^(1/n), normalizzato a Qb.
- Esponente n regolabile (1 = laminare, ~1,75 = quota turbolenta).

Limiti: stima d'ordine di grandezza. P3 è misurata prima di linee e Y; fori laterali, punta e connettori sono ignorati. Per uso clinico tarare sulle curve ΔP/flusso del produttore.
