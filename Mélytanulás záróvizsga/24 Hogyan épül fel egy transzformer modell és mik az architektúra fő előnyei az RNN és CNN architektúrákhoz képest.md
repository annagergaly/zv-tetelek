Lenti képeken látszik az architektúra.
Modell felépítése:
- Enkóder-dekóder
- Input embedding, amihez hozzájön a positional encoding:
	- Utóbbi egy szinusz alapú encoding
	- Ennek célja, mivel nem látja a modell az input szekvenciális mivoltát (mivel nem úgy dolgozza fel mint pl egy rnn), így szükséges valami, ami megmondja, hogy hol foglal helyet a szekvenciában, erre jó a positional encoding
- Base attention layer:
	- kvázi egy fuzzy, differenciálható vektorizált dictonary lookup
	- query, amit keresünk
	- key ami benne van a dictionaryben
	- value maga az információ
	- Ez egy multi-head attention meg egy add és layer normalizáció
- Causal self-attention:
	- Ez a dekóderben van
	- mivel autoregresszív a model, azaz tokenenként generálja az outputot, ahol beadja az előző generált tokent is
	- A kauzalitás ide ott kell, hogy a "jövőbe ne lásson", csak az előtte lévő generált tokeneket lássa
	- A kauzális maszk azt eredményezi, hogy mindenki csak vissza felé attendálhat
- Layer norm: feature-önként és nem batchenként
Előnyei:
- RNN-nel szemben:
	- Könnyen párzuhamosítható, mert a recurrent réteget felváltja az attention
	- Így nem kell backpropagation through time. (Ez a hosszabb szekvenciák miatt lassú lehet, mert a teljes szekvenciát végig kell tolni a hálón, hogy megkapjuk a megfelelő gradienst?) Máshogyan: az egyes rétegek között is párhuzamosítható. Amikor bemegy a szekvencia az RNN-be, akkor végig kell mennie az egészen mire a legvégén kapunk eredményt?
	- Jobban megragadja a hosszútávú függőségeket a messzebb lévő szekvencia elemek között az inputban és az outputban. Az attentionnel minden hely képes az egész inputtal attendálni.
- CNN-nel szemben:
	- dinamikus hosszú szekvenciát fel tud dolgozni, szemben a fix mérettel
	- hosszabb dependenciát meg tud jegyezni
	- nincsen memóriája, a CNN-nek

![image](24_01_transformer.PNG)
![image](24_02_attention.PNG)
