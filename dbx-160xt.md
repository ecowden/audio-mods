# DBX 160XT

Note: I'm using the _unbalanced_ output!

### Recipe

| Part | Before  | After     | Notes |
| ---- | ------- | --------- | ----- |
| U1   | LF353   | LME49860  | |
| U2   | LF351   | OPA134    | |
| U8   | LF353   | OPA2134    | According to [JW](http://www.gearslutz.com/board/geekslutz-forum/53182-dbx-160xt-mods-schematic.html): "The non-linear capacitor circuit also benefits from the use of a very low noise fet input opamp...The 353's are too noisy and add THD to the mix." I _think_ this is right, but I could be wrong. |
| U11  | DBX1252 | THAT2180A | Also need to change surrounding circuitry. |
| C16  | 1uF 63V Film | 2.2uF Solen "Fast Cap" | N/A |
| C??? | 1uF 50V Elec | 22uF 50V Panasonic FR | Replaced 21 capacitors. Basically, all the little blue ones except the meter board, since it would have been tricky to get to those. (TODO did I use 56uF on some of these?) |
| C??? | 1uF 50V Elec | 56uF 50V Panasonic FR | See above. |



### Bill of Materials

| Qty | Part | Description | Mouser #  |
| --- | ---- | ----------- | --------- |
| 1   | LME49860 | Dual Op Amp | 926-LME49860NA/NOPB |
| 1   | OPA134   | Single FET-input Op Amp | 595-OPA134PA  |
| 1   | OPA2134  | Dual FET-input Op Amp   | 595-OPA2134PA |
| 1   | THAT2180A | VCA | 887-2180AL08-U |
| 21 ??? | EEU-FR1H220 | 22uf 50V Electrolytic Capacitor | 667-EEU-FR1H220 |
| ??? | EEU-FR1H560 | 56uf 50V Electrolytic Capacitor | 667-EEU-FR1H560 |

### Thoughts

I'm using the _unbalanced_ output, so I've left the balanced output alone. That said, even if I were using it, I'd still probably leave the 5534's in there.
