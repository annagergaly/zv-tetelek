[link](https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning)
MLOps: ML system development and ML system operation
Development:
	Különböző paraméterek teszetlése, modellek, algoritmusok. Számon kell tartani, hogy mi működött és mi nem.
Testing:
	unit és integrációs tesztek mellett kell data validation, model quality evaluation és model validation
Deployment:
	Általában a deployment többlépéses, mert kell bele pl automatikus újratanítás és deployment, kiértékelés
Production:
	Hibák nem csak a kódból eredhetnek, hanem az adat változásából is. Model decay fordulhat elő, ezért trackelni kell a modell eredményét, akár modelleket rollbackelni.
CI részbe kerül validation data, data scemas and models.
CD-be kerül ML training pipeline deploymentje, ami akár a model prediction service-t is deployolja.
CT (continuous training): ami a modellek automatikus újratanításával és kiszolgálásával foglalkozik.
Lépések: Data extraction -> Data analysis -> Data preparation -> Model training -> Model evaluation -> Model validation -> Model serving -> Model monitoring

MLOPS Level 0: Manual process:
- nincsen benne automatizáció, manuális a model building és deployment
- manual, script-driven, általában experimental code notebookban
- elválik az ML és az operations, ritkán iterálják, nincsen CI, nincsen CD
- Nincsen aktív monitoring
![image](31_01_MLOPS.PNG)
MLOPS Level 1: ML pipeline automation
- az ML kísérlet orkesztrált, a lépések között automatizált, gyorsabban lehet kísérletezni, iterálni
- CT (continous training) van a prodban: új adat jön be, akkor triggernél újratanítja a modelt
- a pipeline használva van a testben és a prodban is
- modularizált komponensekből áll, amik pipeline-ok között is megoszthatók. Remélhetőleg konténerizált is
- Prodba nyomja ki az új modelleket automatikusan
- Deploylod a teljes training pipeline-t, ami automatikusan betanít egy modellt és kiszolgálja, nem csak a modellt magát, mint a korábbiban
- Egyéb addonok:
	- data and model validation
	- feature store:
		- tárolja a feature seeteket, későbbi újrahasználásra
	- metadata management
		- ML pipeline exectuion info: komponensek, pipeline verziók, mikor, ki futtatta, milyen paraméterekkel, artifaktok
	- ML pipeline trigger
		- mikor tanítson újra új adattal
		- lehet on demand, on schedule (pl. minden héten), on availability of new training data (pl amikor több adat áll rendelkezésre), on model performance degradation (ha már szarul teljesít a modell), on significant changes in the data distributions (concept drift)
![image](31_02_MLOPS.PNG)
MLOPS Level 2: CI/CD pipeline automation
- itt már maguk az ML pipeline-ok is CI/CD-zve vannak
- Új pipeline komponensek készíthetők, testelhetők, deployolhatók
- Az én megértésem szerint itt lényegében magának a komponenseknek a CI/CD-je zajlik, mint egy normális szoftverfejlesztésnél. (Pl. elkészül egy új data preparation komponens, akkor az is átmegy egy teszten mielőtt kimenne a prodba)
![image](31_03_MLOPS.PNG)