Hiperparaméter optimalizálás in general:
- lehet manuálisan
- grid search: szisztematikusan végigmegy rácsszerűen a hiperparaméter téren
- random search: véletlenszerűen választ hiperparamétereket
- First coarse, then fine details: random search és utána finomabban egy régiőban csinál random search-öt, ami ígéretesnek tűnt
- Libek: optuna?, hyperopt
TPE (Tree-structured Parzen Estimators):
- Bayesi optimalizációs megközelítés
- Az elején fix hiperparaméter kombókat próbál ki, vagy random search
- Minden iterációban eldönti, hogy melyik hiperparaméter halmazzal érdemes folytatni
- Minden iteráció után 2 csoport alakul ki:
	- Felső 10-25%-ba tartozó hiperparaméterek aszerint, hogy milyen pontosságot érnek el a teszt adaton
	- Ezután próbál újra olyan hiperparamétereket kipróbálni, amik a jó kategóriában vannak
HyperBand/pruning:
- A lényege az, hogy nem fejezi be az összes tanítást, hanem már a tanítás elején megnézi, hogy mi a trend (hogyan csökken a loss) és alapján dönti el, hogy érdemes-e folytatni
- Pl tanít 2 epochig többet, majd eldönti, hogy melyikeket érdemes folytatni és így minden alkalommal felezi a hiperparamétertért