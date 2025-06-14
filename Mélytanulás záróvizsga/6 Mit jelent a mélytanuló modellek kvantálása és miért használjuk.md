súlyokat kevésbé precíz reprezentációba tesszük (kevesebb bites float, int), tanítás után, vagy már tanítás közben is lehet rá készülni
- QAT (Quantization Aware Training): tanítás közben hangolja kvantálási paramétereket
- PTQ (Post-Training Quantization): tanítás után valami mágiával átkvantálja

kevesebb helyet foglal, gyorsabban lehet futtatni, inference mehet kisebb teljesítményű (mobil, edge) eszközökön, cost-effective
ideális esetben nem sokat csökken a pontosság közben