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
- Erre vannak speciális komponensek mint a CTC, Transducer vagy attention alignment (lásd [[33 Milyen neurális architektúrák jönnek szóba end-to-end ASR-nél]])

