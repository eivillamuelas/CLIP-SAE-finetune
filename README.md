### CLIP finetune: SAE-informed adversarial training 💥🤖💫

Descripción General
Este repositorio contiene código experimental que combina CLIP (Contrastive Language-Image Pre-training) con Autoencoders Dispersos (SAE). Para código estable y probado, se recomienda consultar el repositorio zer0int/CLIP-fine-tune.
Actualización (19/DIC/2024)

Nuevo modelo SAE-Long-CLIP con precisión del 90% en ImageNet/ObjectNet
Código disponible en este repositorio
Modelo disponible en Hugging Face: zer0int/LongCLIP-SAE-ViT-L-14

Contenido del Repositorio

Código utilizado para el ajuste fino del modelo CLIP-SAE-ViT-L-14
Carpeta "attack" con datasets necesarios para 'a1-finetune.py'
Scripts auxiliares:

a2: Conversión del modelo GmP a formato .weight para uso general
a4: Pruebas rápidas de zero-shot en imágenes de ataque tipográfico



Metodología

Dataset de ataque curado mediante SAE, disponible en Hugging Face
Enfoque: Parametrización Geométrica (GmP) + escalado de neuronas sensibles al texto
Base teórica: Toy Models of Superposition

Implementación del Autoencoder

Arquitectura: Encoder-Decoder con pesos vinculados y función Top-K
Inspirado en investigaciones de:

Anthropic.AI: "Golden Gate Claude"
OpenAI: Función de activación Top-K



Observaciones del Autor

La efectividad óptima del SAE aún está en investigación
Diferentes dimensiones ocultas producen resultados variados:

Dimensión pequeña: conceptos muy específicos
Dimensión grande (8192): conceptos más aleatorios, menor precisión
Dimensión intermedia: conceptos complejos pero significativos



Nota: El código del SAE será publicado después de una revisión y optimización exhaustiva.

---

For now, here's a fun concept of "things on the back of other things" in CLIP ViT-L/14 that the SAE learned:

![6](https://github.com/user-attachments/assets/2a4521b8-3a18-4c56-b68e-2e09d9280697)

Example of the effect of images the SAE had chosen as salient typographic attacks for CLIP.

![8](https://github.com/user-attachments/assets/ec3205e2-1420-4baa-a3a2-1e3100776865)

And zero-shot results via script (4):

![results-zeroshot](https://github.com/user-attachments/assets/ed3a6c24-3c49-4d27-969b-7802fe17e35f)
