CTC (Connectionist Temporal Classification):
+ sok frame-hez jósolunk kevés karaktert
+ modell frame-enként jósol karaktert vagy blank-et
+ CTC lossnál összevonjuk az ismétlődéseket, eldobjuk a blanket: nem számít mennyire sikerült az alignment

Transducer RNN-T:
+ Három komponens, hangot, korábban kiadott szimbólumokat nézi és a harmadik ezeket egyesíti
+ Nemcsak idő szerint hanem karakter szerint is lép, kb egy 2D gridben
+ Jobban kezeli a kontextust, tanul a nyelvi mintázatokra

Attention (Listen-Attend-Spell):
+ Hangra encoder, attention az alignmenthez, dekóder a kimeneti karakterekhez

![[20_01_asr.png]]