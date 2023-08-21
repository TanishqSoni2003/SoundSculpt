---
title: SoundSculpt
emoji: 🎤🎸🥁🎹
colorFrom: yellow
colorTo: purple
sdk: docker
app_port: 7860
models: ["https://huggingface.co/fabiogra/baseline_vocal_remover"]
tags: ["audio", "music", "vocal-removal", "karaoke", "music-separation", "music-source-separation"]
pinned: true
---

<p align="center">
  <img src="img/logo_moseca.png" alt="logo" width="70" />
</p>

<h2 align="center">SoundSculpt</h1>

<p align="center">Music Source Separation & Karaoke</p>

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ODoK3VXajprNbskqy7G8P1h-Zom92TMA?usp=sharing)

<a href="https://huggingface.co/spaces/fabiogra/SoundSculpt">
<img src="https://img.shields.io/badge/🤗%20Hugging%20Face-Spaces-blue"
alt="Hugging Face Spaces"></a>

<a href="https://huggingface.co/spaces/fabiogra/SoundSculpt/discussions?docker=true">
	
<img src="https://img.shields.io/badge/-Docker%20Image-blue?logo=docker&labelColor=white"
alt="Docker"></a><a href="https://www.buymeacoffee.com/fabiogra">

<img src="https://img.shields.io/badge/Buy%20me%20a%20coffee--yellow.svg?logo=buy-me-a-coffee&logoColor=orange&style=social"
alt="Buy me a coffee"></a>

---
<p align="center">
  <img src="https://i.imgur.com/QoSd3Fg.gif" alt="Demo SoundSculpt"/>
</p>


- [Setup](#setup)
  - [Local environment](#local-environment)
  - [Docker](#docker)
  - [(Optional) Preprocess samples](#optional-preprocess-samples)
- [About](#about)
  - [High-Quality Stem Separation](#high-quality-stem-separation)
  - [Advanced AI Algorithms](#advanced-ai-algorithms)
  - [Karaoke Fun](#karaoke-fun)
  - [Easy Deployment](#easy-deployment)
  - [Open-Source and Free](#open-source-and-free)
  - [Support](#support)
- [FAQs](#faqs)
  - [What is SoundSculpt?](#what-is-SoundSculpt)
  - [Are there any limitations?](#are-there-any-limitations)
  - [How does SoundSculpt work?](#how-does-SoundSculpt-work)
  - [How do I use SoundSculpt?](#how-do-i-use-SoundSculpt)
  - [Where can I find the code for SoundSculpt?](#where-can-i-find-the-code-for-SoundSculpt)
  - [How can I get in touch with you?](#how-can-i-get-in-touch-with-you)
- [Disclaimer](#disclaimer)

---


## Setup
### Local environment
Create a new environment with Python 3.10 and install the requirements:
```bash
pip install -r requirements.txt
```
set the `PYTHONPATH` to the root folder:
```bash
export PYTHONPATH=path/to/SoundSculpt
```
download the vocal remover model:
```bash
wget --progress=bar:force:noscroll https://huggingface.co/fabiogra/baseline_vocal_remover/resolve/main/baseline.pth
```
then run the app with:
```bash
streamlit run app/header.py
```
### Docker
You can also run the app with Docker:
```bash
docker build -t SoundSculpt .
docker run -it --rm -p 7860:7860 $(DOCKER_IMAGE_NAME)
```
or pull the image from Hugging Face Spaces:
```bash
docker run -it -p 7860:7860 --platform=linux/amd64 \
	registry.hf.space/fabiogra-SoundSculpt:latest
```

You can set the following environment variables to limit the resources used by the app:
- ENV_LIMITATION=true
- LIMIT_CPU=true

### (Optional) Preprocess samples
If you want to preprocess the samples used in the demo, you need to set the env variable `PREPARE_SAMPLES=true` as a secret (create the file `run/secrets/PREPARE_SAMPLES` with `true` value inside).

If you run locally you also need to move the files inside `scripts` to the root folder and run `prepare_samples.sh`.
```
cp scripts/ .
chmod +x prepare_samples.sh
python prepare_samples.sh
```

---
## About

Welcome to SoundSculpt, your personal web application designed to redefine your music experience.
Whether you're a musician looking to remix your favorite songs, a karaoke
enthusiast, or a music lover wanting to dive deeper into your favorite tracks,
SoundSculpt is for you.

<br>

### High-Quality Stem Separation

<img title="High-Quality Stem Separation" src="https://i.imgur.com/l7H8YWL.png" width="250" ></img>


<br>

Separate up to 6 stems including 🗣voice, 🥁drums, 🔉bass, 🎸guitar,
🎹piano (beta), and 🎶 others.

<br>

### Advanced AI Algorithms

<img title="Advanced AI Algorithms" src="https://i.imgur.com/I8Pvdav.png" width="250" ></img>

<br>

SoundSculpt utilizes state-of-the-art AI technology to extract voice or music from
your original songs accurately.

<br>

### Karaoke Fun

<img title="Karaoke Fun" src="https://i.imgur.com/nsn3JGV.png" width="250" ></img>

<br>

Engage with your favorite tunes in a whole new way!

SoundSculpt offers an immersive online karaoke experience, allowing you to search
for any song on YouTube and remove the vocals online.

Enjoy singing along with high-quality instrumentals at the comfort of your home.


<br>

### Easy Deployment


With SoundSculpt, you can deploy your personal SoundSculpt app in the
<a href="https://huggingface.co/spaces/fabiogra/SoundSculpt?duplicate=true">
<img src="https://img.shields.io/badge/🤗%20Hugging%20Face-Spaces-blue"
alt="Hugging Face Spaces"></a> or locally with
[![Docker Call](https://img.shields.io/badge/-Docker%20Image-blue?logo=docker&labelColor=white)](https://huggingface.co/spaces/fabiogra/SoundSculpt/discussions?docker=true)
in just one click.

You can also speed up the music separation process by [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ODoK3VXajprNbskqy7G8P1h-Zom92TMA?usp=sharing) with GPU support.

<br>

### Open-Source and Free

SoundSculpt is the free and open-source alternative to lalal.ai, splitter.ai or media.io vocal remover.

You can modify, distribute, and use it free of charge. I believe in the power of community
collaboration and encourage users to contribute to our source code, making SoundSculpt better with
each update.


<br>

### Support

- Show your support by giving a star to the GitHub repository [![GitHub stars](https://img.shields.io/github/stars/fabiogra/SoundSculpt.svg?style=social&label=Star)](https://github.com/fabiogra/SoundSculpt).
- If you have found an issue or have a suggestion to improve SoundSculpt, you can open an [![GitHub issues](https://img.shields.io/github/issues/fabiogra/SoundSculpt.svg)](https://github.com/fabiogra/SoundSculpt/issues/new)
- Enjoy SoundSculpt? [![Buymeacoffee](https://img.shields.io/badge/Buy%20me%20a%20coffee--yellow.svg?logo=buy-me-a-coffee&logoColor=orange&style=social)](https://www.buymeacoffee.com/fabiogra)

------

## FAQs

### What is SoundSculpt?

SoundSculpt is an open-source web app that utilizes advanced AI technology to separate vocals and
instrumentals from music tracks. It also provides an online karaoke experience by allowing you
to search for any song on YouTube and remove the vocals.

### Are there any limitations?
Yes, in this environment there are some limitations regarding lenght processing
and CPU usage to allow a smooth experience for all users.

<b>If you want to <u>remove these limitations</u> you can deploy a SoundSculpt app in your personal
environment like in the <a href="https://huggingface.co/spaces/fabiogra/SoundSculpt?duplicate=true"><img src="https://img.shields.io/badge/🤗%20Hugging%20Face-Spaces-blue" alt="Hugging Face Spaces"></a> or locally with [![Docker Call](https://img.shields.io/badge/-Docker%20Image-blue?logo=docker&labelColor=white)](https://huggingface.co/spaces/fabiogra/SoundSculpt/discussions?docker=true)</b>

### How does SoundSculpt work?
SoundSculpt utilizes the Hybrid Spectrogram and Waveform Source Separation ([DEMUCS](https://github.com/facebookresearch/demucs)) model from Facebook. For fast karaoke vocal removal, SoundSculpt uses the AI vocal remover developed by [tsurumeso](https://github.com/tsurumeso/vocal-remover).

### How do I use SoundSculpt?
1. Upload your file: choose your song and upload it to SoundSculpt. It supports
a wide range of music formats for your convenience.

2. Choose separation mode: opt for voice only, 4-stem or 6-stem separation
depending on your requirement.

3. Let AI do its magic: SoundSculpt’s advanced AI will work to separate vocals
from music in a matter of minutes, giving you high-quality, separated audio tracks.

4. Download and enjoy: preview and download your separated audio tracks.
Now you can enjoy them anytime, anywhere!


### Where can I find the code for SoundSculpt?

The code for SoundSculpt is readily available on
[GitHub](https://github.com/fabiogra/SoundSculpt) and
[Hugging Face](https://huggingface.co/spaces/fabiogra/SoundSculpt).


### How can I get in touch with you?

For any questions or feedback, feel free to contact me on
[![Twitter](https://badgen.net/badge/icon/twitter?icon=twitter&label)](https://twitter.com/grsFabio)
or [LinkedIn](https://www.linkedin.com/in/fabio-grasso/en).

------
## Disclaimer

SoundSculpt is designed to separate vocals and instruments from copyrighted music for
legally permissible purposes, such as learning, practicing, research, or other non-commercial
activities that fall within the scope of fair use or exceptions to copyright. As a user, you are
responsible for ensuring that your use of separated audio tracks complies with the legal
requirements in your jurisdiction.

 
 
