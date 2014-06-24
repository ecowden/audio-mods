# DBX 160XT

Note: I'm using the _unbalanced_ output!

### Recipe

| Part | Before  | After     | Notes |
| ---- | ------- | --------- | ----- |
| U1   | LF353   | OPA2134  | Input op amp |
| U2   | LF351   | OPA134    | Unbalanced output, driving transistor pair |
| U8   | LF353   | OPA2134   | Sidechain. According to [JW](http://www.gearslutz.com/board/geekslutz-forum/53182-dbx-160xt-mods-schematic.html): "The non-linear capacitor circuit also benefits from the use of a very low noise fet input opamp...The 353's are too noisy and add THD to the mix." I _think_ this is right, but I could be wrong. |
| U11  | DBX1252 | THAT2180A | Bend back or cut off pin 4 to circumvent trimming circuitry. The THAT2180 series is pre-trimmed. |
| C16  | 1uF 63V Film | 2.2uF Solen "Fast Cap" | I had it lying around and it fit. Don't judge me. |
| C14, C18 | 1uF 50V Elec | 56uF 50V Panasonic FR | Decoupling U1. Bypassed with 0.01uF ceramic beneath the PCB. |
| C35, C46 | 1uF 50V Elec | 56uF 50V Panasonic FR | Decoupling U8. Bypassed with 0.01uF ceramic beneath the PCB. |
| C25 | 10uF 50V Elec | 56uF 50V Panasonic FR | Decoupling U2. It uses one cap rail-to-rail instead of two caps to ground. Unusual, but the OPA134 seems stable. |
| C27, C31 | 22uF 25V | 22uF 50V Panasonic FR | Around unabalanced output transistor pair. I _think_ I know what they do, but I'm not 100% certain, so I left original values. |
| C48, C50, C51, C52 | 1uF 50V Elec | 1.5uF 50V Wima MKS2 | Decoupling U5 & U6 (4558 in sidechain). I used film caps only because I had them and they fit.|
| C9, C10, C54, C56 | 1uF 50V Elec | 1.5uF 50V Wima MKS2 | Decoupling U7 & U9 (misc 4558 & LF353). See above. |
| C58, C59 | 1uF 50V Elec | 1.5uF 50V Wima MKS2 | Decoupling U10 (LM339). See above. |
| C17 | 10uF 50V Elec | 10uF 50V Panasonic FC | Hanging off VCA pin 7 (Vcc). Could probably have upsized, but I don't understand enough to be certain. |
| C39, C42 | 1uF 50V Elec | | NO CHANGE. RMS detector. Probably decoupling, but time constants can be tricky. |
| C40, C43 | 10uF 50V Elec | | NO CHANGE. RMS detector See above. |
| C3, C4, C5, C6 | 470uF 50V | PSU pre-regulator filter. 1000uF 50V Panasonic FR. | My unit had been modded and original values may be wrong. |
| C7, C8 | 22uF 50V | 220uF 50V Panasonic FR | PSU post-regulator filter. Bypassed with .1uF poly beneath PCB. My unit had been modded and original values may be wrong. |
| C41 | 10uF 25V | 10uF 25V Panasonic FC | Leave as 10uF since I believe this is part of the timing cirtcuit. Probably unnecessary, but I measured several and chose the closest to 10uF. |
| CR13, CR14, CR15, CR16   | Probably 1N400-Something | 100V 1A Schottky Diode | Not sure if it makes much difference, but I had them lying around... |

### Bill of Materials

| Qty | Part  | Mouser #  |
| --- | --------------- | --------- |
| 1   | OPA134   Single FET-input Op Amp | 595-OPA134PA  |
| 2   | OPA2134  Dual FET-input Op Amp   | 595-OPA2134PA |
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

I chose a lot of parts because that's what I had lying around. For instance, when replacing the 1uF electrolytic decoupling caps, I grabbed some 1.5uF Wima polyester film caps. Who makes 1uF electrolytics nowadays, anyway? I used that 2.2uF Solen because I had it from years ago. 

I chose OPA2134/OPA134 to replace LF353/LF351 because it's by default FET-input op amp. It worked well on the first go, so I moved on. In general, I try to match input types, then focus on decoupling.
