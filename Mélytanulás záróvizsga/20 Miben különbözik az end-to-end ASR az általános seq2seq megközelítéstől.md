ASR (Automatic Speech Recognition) 
Speech-To-Text (STT): acoustic pressure(time) signal) → text transcription
felismerhetjük mellé pl a beszélőt vagy az érzelmeit
seq2seq: bemeneti szekvenciából kimeneti szekvenciát generál

+ Classic approach: HMM-DNN hibrid
+ End-to-end approach: DNN

ASR with S2S:
+ Encoder-Decoder structures
+ Special loss function: CTC (for time alignment problem) + attention for best results
+ Transducer

Az **end-to-end ASR** egy speciális **seq2seq probléma**, ahol:
- A bemenet folyamatos, hosszú és akusztikus
- Kimenet sokkal rövidebb tokensorozat
- Az alignment nem triviális, mivel a bemenet hosszabb, és az időbeli illesztés nem ismert
- Erre vannak speciális komponensek mint a CTC, Transducer vagy attention alignment

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