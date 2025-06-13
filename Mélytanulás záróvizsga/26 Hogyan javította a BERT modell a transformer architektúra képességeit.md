Bidirectional rész:
- Nagyjából ugyanazt az architechtúrát használta, mint az eredeti transformer, de csak az encoder résszt
- Only uses the encoder and focuses on producing deep bidirectional representations of text
- Bidirectional (kétirányú) jelentése itt az, hogy a tokenek mindkét irányba tudnak attendálni egymásra (tehát pl nem csak hátra, mint ha le lenne maszolka)
	- Ha le van korlátozva egy irányra (pl. balról jobbra), akkor csak abba az irányba tud hatni
	- Mivel ez mindkét irányba tud hatni (tokenekre előtte és mögötte is), így a szélesebb kontextust dolgoz fel
- Nem egy right-to-left és egy left-to-right model kombinációja
Tanítás:
- 2 unsupervised (talán inkább self-supervised?) taskon tanítják
- Masked Language Modeling (Masked LM):
	- A tokenek 15%-t kimaszkolták egy [MASK] tokennel, és a modell feladata volt ennek a predikciója
		- Pontosabban ezt még továbbcsavarták, a kimaszkolandó tokenek 80%-át maszkolták ki ténylegesen 10%-ot hagytak úgy ahogy volt, 10%-ot random mással behelyettesítettek, de végig ugyanúgy a kimaszkolandó $i$. tokent prediktáltatták a modellel
- Next Sentence Prediction (NSP):
	- Van 2 mondat (token szekvencia) A és B és arról kell eldöntenie a modellnek, hogy B A-t követi-e. (tehát ez egy bináris osztályozás). Az esetek felében random mondat volt a második, a másik felében az eseteknek pedig a valódi mondat volt ami követte.
	- pl question answering és natural langauge inference downstream taskoknál jön jól
	- A 2 mondatot egy [SEP] tokennel választják el, sőt tesznek egy segment embeddinget is a token embeddingekre
Ezek sokkal gazdagabb nyelvi reprezentációt eredményeztek, amit utána a downstream taskra könnyebb finetuneolni. Elegendő csak a megfelelő input-outputokat megadni a modellnek.