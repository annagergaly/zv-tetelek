Bizonyos részeket task függően érdemes megválogatni.
Legfontosabb: konvolúció (conv2d), pooling (maxpool), normalizáció, residual/skip connection, dropout.
Konvolúciós rétegek:
- Spatial információt könnyebben dolgoz fel
- Kernelek/filterek tanulható súlyokkal, amik valamilyen lokális mintákat ismernek fel
- Dekonvolúciós réteg a generatív taskokhoz pl
Pooling rétegek:
- Average pooling, max pooling
- Csökkenti a dimenziót
Aktivációs függvények:
- Általában ReLU, Leaky ReLU
- Ezek segítik a jobb konvergálást
Normalizációs rétegek:
- Batch norm, layer norm
- stabilizálja és gyorsítja a tanítást
Skip/residual connection:
- gradient flow miatt, hogy ne legyenek vanishing gradient problémák
Attention:
- modern hálókban
Dense réteg:
- Általában csak a legvégén (pl osztályozáshoz)
Előtanított hálók:
- Rengeteg erőforrás 0-ról betanítani egy hálót, így hatékonyabb egy előre betanítottat használni és azt finomhangolni