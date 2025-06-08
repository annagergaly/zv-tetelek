(1) mind a tanítási, mind a validációs hiba magas (underfitting), ha (2) a tanítási hiba alacsony, de a validációs hiba magas (overfitting), illetve ha (3) a validációs hiba alacsonyabb, mint a tanítási hiba (overregularizáció)


1. underfittingnél a modell nem képes jól rátanulni a tanító adatra, nem elég magas a paraméter szám, nem megfelelő az architektúra, nincs elég adat, nem tanult még eleget a modell
2. overfittingnél a modell túlságosan rátanul a tanító adatra és nem tud generalizálni. túl magas paraméterszám, túl kevés adat, túl hosszú tanítás (early stopping), regularizáció szükséges
3. overregularizáció (erre kb semmi találat nincs lol), túl sok constraint van a modelben amitől nem tud igazán rátanulni az adatra