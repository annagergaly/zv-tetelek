+ tanító: ez alapján tanulja meg az eloszlást/összerendeléseket a modell
+ validációs: validáljuk vele hogy milyen jól generalizál túltanult-e, mikor álljunk le a tanítással. elkülönül a teszttől hogy az semmilyen módon ne befolyásolja a tanítást
	+ ez arra is jó, hogy ha több modell példányunk/architektúránk van akkor közöttük dönteni
+ teszt: megmutatja hogy tanítás után mennyire képes a modell helyesen "válaszolni" teljesen ismeretlen adatra
	+ ez meg az ami mintha a valóságban futtatnánk

amennyire lehet mindegyiknek egyezzen az eloszlása a teljes adathalmazzal, pl osztályozásnál a classok eloszlása, egyébként random?
temporal/sequential adatnál különböző időpontok legyenek, ne keveredjenek össze