# DBX 160XT

Note: I'm using the _unbalanced_ output!

### Recipe

| Part | Before  | After     | Notes |
| ---- | ------- | --------- | ----- |
| U1   | LF353   | LME49860  | |
| U2   | LF351   | OPA134    | |
| U8   | LF353   | OPA2134    | According to [JW](http://www.gearslutz.com/board/geekslutz-forum/53182-dbx-160xt-mods-schematic.html): "The non-linear capacitor circuit also benefits from the use of a very low noise fet input opamp...The 353's are too noisy and add THD to the mix." I _think_ this is right, but I could be wrong. |
| U11  | DBX1252 | THAT2180A | Also need to change surrounding circuitry. |
| C16  | 1uF 63V Film | 2.2uF Solen "Fast Cap" | I had it lying around and it fit. Don't judge me. |
| C??? | 1uF 50V Elec | 22uF 50V Panasonic FR | Replaced 21 capacitors. Basically, all the little blue ones except the meter board, since it would have been tricky to get to those. Some fit the larger 56uF, some didn't. |
| C14, C18 | 1uF 50V Elec | 56uF 50V Panasonic FR | See above. |
| C17 | 10uF 50V Elec | 10uF 50V Panasonic FC | Hanging off VCA pin 7 (Vcc). Could probably have upsized, but I don't understand enough to be certain. |
| C25 | 10uF 50V Elec | 56uF 50V Panasonic FR | See above. |

| Bypass C14, C18 | - | 0.01uF Ceramic | Bypass capacitors added underneath the PCB. |

| C3, C4, C5, C6 | 470uF 50V | 1000uF 50V Panasonic FR | My unit had been modded. Original values may be wrong. |
| C7, C8 | 22uF 50V | 220uF 50V Panasonic FR | My unit had been modded. Original values may be wrong. |
| C27, C31 | 22uF 25V | 220uF 50V Panasonic FR | Did I leave these as 22uF? I _think_ I know what they do, but I'm not 100% certain... |
| Bypass C7, C8, C27, C31 | - | 0.1uF Film | Bypass capacitors added underneath the PCB. Yeah yeah, I know they're not Wimas, but they fit better and the longer leads make them easier to work with. |
| CR13, CR14, CR15, CR16   | Probably 1N400-Something | 100V 1A Schottky Diode | Not sure if it makes much difference, but I had them lying around... |
| C | 10uF 25V | 10uF 25V Panasonic FC | Leave as 10uF since I believe this is part of the timing cirtcuit. Probably unnecessary, but I measured several and chose the closest to 10uF. |



### Bill of Materials

| Qty | Part  | Mouser #  |
| --- | --------------- | --------- |
| 1   | LME49860 Dual Op Amp | 926-LME49860NA/NOPB |
| 1   | OPA134   Single FET-input Op Amp | 595-OPA134PA  |
| 1   | OPA2134  Dual FET-input Op Amp   | 595-OPA2134PA |
| 1   | THAT2180A VCA | 887-2180AL08-U |
| 4   | 220uf 50V Panasonic FR Electrolytic Capacitor | 667-EEU-FR1H221 |
| 4   | 0.1uF Panasonic ECWF Polypropylene Capacitor | 667-ECW-F2104HAB |
| ??? | 0.01uF TDK C0G Ceramic Capacitor | 810-FK18C0G1H103J |
| 21 ??? | 22uf 50V Panasonic FR Electrolytic Capacitor | 667-EEU-FR1H220 |
| ??? | 56uf 50V Panasonic FR Electrolytic Capacitor | 667-EEU-FR1H560 |
| 1 | 2.2uF Solen "Fast Cap" Polypropylene Capacitor (SOLEN-51548) | N/A. Try [PartsConnexion](http://www.partsconnexion.com/capacitor_film_solen_pb.html), or substitute any good 2uF - 4uF that you can fit in there. The bigger, the more sub-20Hz will pass. |
| 4 | 100V 1A Schottky Diode | 625-SB1H100-E3 |
| 3 | DIP8 Socket | 115-43-308-41-003000 |

### Thoughts

I'm using the _unbalanced_ output, so I've left the balanced output alone. That said, even if I were using it, I'd still probably leave the 5534's in there. If I wanted to enhance the balanced output, I'd probably try inserting a transformer, either an Edcor WSM600/600 if I could fit it or the original Jensen [JT-123-DBX](http://www.jensen-transformers.com/datashts/123dbx.pdf) if I couldn't.
