
 follow me for more: https://linktr.ee/az1fr3



# AudioCraft
![docs badge](https://github.com/facebookresearch/audiocraft/workflows/audiocraft_docs/badge.svg)
![linter badge](https://github.com/facebookresearch/audiocraft/workflows/audiocraft_linter/badge.svg)
![tests badge](https://github.com/facebookresearch/audiocraft/workflows/audiocraft_tests/badge.svg)

AudioCraft es una biblioteca de PyTorch para la investigación en aprendizaje profundo sobre generación de audio. AudioCraft contiene código de inferencia y entrenamiento para dos modelos generativos de IA de última generación que producen audio de alta calidad: AudioGen y MusicGen.

# Instalación

AudioCraft requiere Python 3.9 y PyTorch 2.0.0. Para instalar AudioCraft, puedes ejecutar lo siguiente

```shell
# Best to make sure you have torch installed first, in particular before installing xformers.
# Don't run this if you already have PyTorch installed.
pip install 'torch>=2.0'
# Then proceed to one of the following
pip install -U audiocraft  # stable release
pip install -U git+https://git@github.com/facebookresearch/audiocraft#egg=audiocraft  # bleeding edge
pip install -e .  # or if you cloned the repo locally (mandatory if you want to train).
```

We also recommend having `ffmpeg` installed, either through your system or Anaconda:
```bash
sudo apt-get install ffmpeg
# Or if you are using Anaconda or Miniconda
conda install 'ffmpeg<5' -c  conda-forge
```

## Modelos

En este momento, AudioCraft contiene el código de entrenamiento y el código de inferencia para:
* [MusicGen](./docs/MUSICGEN.md): A state-of-the-art controllable text-to-music model.
  
* [AudioGen](./docs/AUDIOGEN.md): A state-of-the-art text-to-sound model.  <a target="_blank" href="https://colab.research.google.com/github/az1fr3/audiocraftbyAz1fr3/blob/main/Audigen_Az1fr3_V1S.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

* [EnCodec](./docs/ENCODEC.md): A state-of-the-art high fidelity neural audio codec.
  
* [Multi Band Diffusion](./docs/MBD.md): An EnCodec compatible decoder using diffusion.

## Codigo de entrenamiento: 

AudioCraft contiene componentes de PyTorch para la investigación en aprendizaje profundo en audio y tuberías de entrenamiento para los modelos desarrollados.
Para una introducción general a los principios de diseño de AudioCraft e instrucciones para desarrollar tu propia tubería de entrenamiento, consulta el
[AudioCraft training documentation](./docs/TRAINING.md).

Para reproducir trabajos existentes y utilizar las tuberías de entrenamiento desarrolladas, 
consulta las instrucciones para cada modelo específico que proporciona indicaciones para la configuración, ejemplos de mallas y información específica del modelo/tarea, así como preguntas frecuentes (FAQ).


## API documentation

We provide some [API documentation](https://facebookresearch.github.io/audiocraft/api_docs/audiocraft/index.html) for AudioCraft.


## FAQ

#### Is the training code available?

Yes! We provide the training code for [EnCodec](./docs/ENCODEC.md), [MusicGen](./docs/MUSICGEN.md) and [Multi Band Diffusion](./docs/MBD.md).

#### Where are the models stored?

Hugging Face stored the model in a specific location, which can be overriden by setting the `AUDIOCRAFT_CACHE_DIR` environment variable.


## License
* The code in this repository is released under the MIT license as found in the [LICENSE file](LICENSE).
* The models weights in this repository are released under the CC-BY-NC 4.0 license as found in the [LICENSE_weights file](LICENSE_weights).


## Citation

For the general framework of AudioCraft, please cite the following.
```
@article{copet2023simple,
    title={Simple and Controllable Music Generation},
    author={Jade Copet and Felix Kreuk and Itai Gat and Tal Remez and David Kant and Gabriel Synnaeve and Yossi Adi and Alexandre Défossez},
    year={2023},
    journal={arXiv preprint arXiv:2306.05284},
}
```

When referring to a specific model, please cite as mentioned in the model specific README, e.g
[./docs/MUSICGEN.md](./docs/MUSICGEN.md), [./docs/AUDIOGEN.md](./docs/AUDIOGEN.md), etc.
