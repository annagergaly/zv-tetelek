Early stopping:
- Tanításkor megfigyelhetjük, hogy a training loss csökken, de a validation loss nő. Ez gyakran előfordulhat és a túltanulás jele lehet.
- Visszaadunk a tanítás végén olyan modellparamétereket, amelyre alacsony a validation loss, remélve, hogy a teszt adaton is alacsony lesz a loss.
- Early stopping: ha a validation loss csökken, eltároljuk azokat a paramétereket, ha bizonyos iterációig (ez a patience) nem javul a validation loss, akkor megállítjuk a tanítást.
- Tekinthetünk rá úgy, mint egy hyperparaméter szelekció, csak az tanító iterációk számára.
- Egyfajta regularizáció is.
Mini-batch:
- Gradient descent során nem az egész tanító adathalmazt használjuk egyszerre.
- Mini-batch módszerek több, mint 1, de kevesebb, mint az egész adathalmazt használják egyszerre.
- Nagyobb mini-batch size jobban közelíti a gradienst.
- Random vannak kiválasztva a mini-batchek, ehhez kell egy shuffle a teljes datasetre.
- Természetesen nem fér el a teljes adathalmaz a videókártyán, így nem tudjuk egyben lefuttatni rajta a modellt, ezért szükséges kisebb darabokra darabolni. SGD-vel így viszont inkább egy átlagos gradienshez közelítünk és minden batch-et egy parameter update követ.