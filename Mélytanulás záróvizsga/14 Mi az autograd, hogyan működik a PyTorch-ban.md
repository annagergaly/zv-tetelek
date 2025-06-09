Autograd:
- Automatikus gradiens számításra
- Tudunk írni saját autograd függvényt is, ekkor a forward és backward függvényeket kell írni
- Amikor gradiens számítunk, akkor létrejön a backwards gráf is (ennek elemeit megcsinálja automatikusan)
- Ha elkészült a számítási gráf, akkor .backward() kiszámolja a gradients, amit a .grad-dal lehet elérni a tenzoron, grad_fn meg a konkrét függvény
- with torch.nograd() kontextussal meg lehet azt csinálni, hogy ne számoljon gradienst
- a forward pass közben dinamikusan építi a backwards gráfot is

![image](figs/13_03_graph.PNG)