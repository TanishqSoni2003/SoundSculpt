

# Title: SoundSculpt
Emoji: 🎤🎸🥁🎹

colorFrom: yellow

colorTo: purple

sdk: docker

app_port: 7860

tags: ["audio", "music", "vocal-removal", "karaoke", "music-separation", "music-source-separation"]

pinned: true

---

## Setup
### Local environment
Create a new environment with Python 3.10 and install the requirements:
```bash
pip install -r requirements.txt
```
set the `PYTHONPATH` to the root folder:
```bash
export PYTHONPATH=path/to/SoundSclupt
```
download the vocal remover model:
```bash
wget --progress=bar:force:noscroll https://huggingface.co/tanishq02/baseline_vocal_remover/blob/main/baseline.pth
```
then run the app with:
```bash
streamlit run app/header.py
```
### Docker
You can also run the app with Docker:
```bash
docker build -tSoundSculpt .
docker run -it --rm -p 7860:7860 $(DOCKER_IMAGE_NAME)
```
or pull the image from Hugging Face Spaces:
```bash
docker run -it -p 7860:7860 --platform=linux/amd64 \
	registry.hf.space/fabiogra-moseca:latest
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

Welcome toSoundSculpt, your personal web application designed to redefine your music experience.
Whether you're a musician looking to remix your favorite songs, a karaoke
enthusiast, or a music lover wanting to dive deeper into your favorite tracks,
Moseca is for you.

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

Moseca utilizes state-of-the-art AI technology to extract voice or music from
your original songs accurately.

<br>

### Karaoke Fun

<img title="Karaoke Fun" src="https://i.imgur.com/nsn3JGV.png" width="250" ></img>

<br>

Engage with your favorite tunes in a whole new way!

Moseca offers an immersive online karaoke experience, allowing you to search
for any song on YouTube and remove the vocals online.

Enjoy singing along with high-quality instrumentals at the comfort of your home.

------

## FAQs

### What is SoundSculpt?

Moseca is an open-source web app that utilizes advanced AI technology to separate vocals and
instrumentals from music tracks. It also provides an online karaoke experience by allowing you
to search for any song on YouTube and remove the vocals.

### How do I use SoundSculpt?
1. Upload your file: choose your song and upload it to SoundSculpt. It supports
a wide range of music formats for your convenience.

2. Choose separation mode: opt for voice only, 4-stem or 6-stem separation
depending on your requirement.

3. Let AI do its magic:SoundSculpt’s advanced AI will work to separate vocals
from music in a matter of minutes, giving you high-quality, separated audio tracks.

4. Download and enjoy: preview and download your separated audio tracks.
Now you can enjoy them anytime, anywhere!

### Where can I find the code for SoundSculpt?

The code forSoundSculpt is readily available on
[GitHub](https://github.com/TanishqSoni2003/SoundSculpt) 

------
## Disclaimer

Moseca is designed to separate vocals and instruments from copyrighted music for
legally permissible purposes, such as learning, practicing, research, or other non-commercial
activities that fall within the scope of fair use or exceptions to copyright. As a user, you are
responsible for ensuring that your use of separated audio tracks complies with the legal
requirements in your jurisdiction.


