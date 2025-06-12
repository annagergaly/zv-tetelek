Kondícionálás:
+ alapbemenet mellé valamilyen kondícionáló, kontroll kiegészítő információ
+ cél: felhasználó megadva az elvártat azzal egyező kimenetet kapjon
+ kondícionált generálás

Tanításkor:
+ Vagy az extra infót korán embeddinghez konkatenáljuk (early fusion)
+ Vagy később, dekóderen keresztül, vagy attention-nél

Kell:
+ Tanítási adat legyen a használni kívánt tulajdonságokkal címkézve
+ Lehet egy plusz loss egy diszkriminátor alapján hogy mennyire sikerült eltalálni a kért tulajdonságot