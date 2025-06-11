Előtanított modell:
- Áltában sokparaméteres, nagy modell, amit nagyon drága betanítani
- Egy nagy, széleskörű adathalmazon betanítva
Felhasználása:
- Promptolással: LLM-ek pl., ilyenkor nem tanítunk semmit
- Feature extractorként: a tetejére helyezünk további réteget, az alap modellt csak egy feature extractorként használjuk.
	- kevésbé flexiblis
	- nincsen forgetting
	- az alap modellt könnyű más taskokra is feature extractorként használni
	- Hatékony memóriában és a felső rétegek betanításában
- Fine-tuning: Helyezünk rá színtén rétegeket a saját taskukhoz illeszkedően, de a teljes modellt tanítjuk, az alap modell rétegeit is
	- Több flexibilitás
	- Általában jobb accuracy
	- Előfordulhat forgetting, catastrophic forgetting
- Adapterek: a pretrained modell rétegeit nem tanítjuk, nem módosítjuk, közbe helyezünk be adapter rétegeket, amiket tanítunk
- Side-tuning [sidetuning.berkeley.edu](https://sidetuning.berkeley.edu/): Nem a pretrained modellt tanítja, hanem egy kisebb másik (akár hasonló vagy disztillált) modellt. Ez a modell annál komplexebb, minél távolabbi feladatra akarjuk tanítani a modellt (a pretrainedhez képest). A kettő kiköp egy-egy reprezentációt, ezeket $\alpha$-blendinggel mossuk össze, ahol $\alpha$ szintén tanult paraméter.

![image](23_01_pretrained.PNG)