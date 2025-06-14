Hugging Face Transformers:
- low-code library
- Előtanított modelleket könnyű betölteni, és később fine-tuneolni
- betölti a modell tokenizerét, amit lehet konfigurálni (pl truncation, padding)
- Van trainer api, ami magas szinten tanítja
- Akár teljes pipeline-okat is be lehet tölteni task specifikusan, ami még low-code-abb
Hugging Face datasets:
- dataseteket lehet betölteni vele
- vannak benne preprocessing függvények is, filtering, mapping, tokenization, formatting
- memory efficient
- könnyen integrálható a transformerssel
Peft (by hugging face): ezzel lehet LoRÁ-val tanítani például
Accelerate (by hugging face): multi-GPU, mixed precision tanítás
Training backendek: PyTorch, Tensorflow, JAX
- Ezek a mögöttes deep learning frameworkök a tanításra és fine-tuningra
Egyebek: pl wandb logolásra, hyperparaméter optimalizációra és checkpoint mentésre