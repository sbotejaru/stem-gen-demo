# Conditional Stem Generation Demo
### Dissertation project, Transilvania University of Brasov
### Author: Botejaru Stefan-Andrei 

---
[`arXiv`](https://arxiv.org/abs/2407.14358): Stable Audio Open paper

[`HuggingFace`](https://huggingface.co/stabilityai/stable-audio-open-1.0): model weights

[`stable-audio-tools`](https://github.com/Stability-AI/stable-audio-tools): code to reproduce Stable Audio


Stable Audio Open was fine-tuned for Stem Reproduction with the help of the ControlNet architecture and generates variable-length (up to 47s) stereo audio at 44.1kHz from a text prompt and an input song. It comprises five components: 
* an autoencoder (VAE) that compresses waveforms into a manageable sequence length
* a T5-based text embedding for text conditioning
* a CLAP-based audio embedding for global audio conditioning
* a ControlNet conditioning module for rythm and song phase
* a transformer-based diffusion (DiT) model that operates in the latent space of the autoencoder.

The model can generate with high fidelity the following stems for an input song: **drums, guitar, piano, bass and percussion**.


## Exercise: Which missing stem is AI generated?

|    | Song without a stem | The missing stem | Overlapped |
| -- | ----- | -------------| ---------- |
| 1. drums  |  <audio controls preload=False><source src="audio/2_input_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/2_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/2_drums_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio>  |
| 2. piano | <audio controls preload=False><source src="audio/1_input_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1_piano.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1_piano_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio>  |
| 3. guitar | <audio controls preload=False><source src="audio/pop_guitar_input_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/pop_guitar_output_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/pop_guitar_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---

<details>
    <summary>Answer: </summary>
    All of them are AI generated. 
</details>


## Generation examples

### 1. Drums

**Prompt**: "genre: rock, stem: drums"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| --- | --------- | -------------- | 
| 1 | <audio controls preload=False><source src="audio/song1_drums_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_drums_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song1_drums_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_drums_mix_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


**Prompt**: "genre: electronic, stem: drums"

**Input song**: 

<audio controls preload=False><source src="audio/song2_no_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| -- | --------- | -------------- |
| 1 | <audio controls preload=False><source src="audio/song2_drums_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_drums_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song2_drums_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_drums_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 3 | <audio controls preload=False><source src="audio/song2_drums_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_drums_mix_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


**Prompt**: "genre: pop, stem: drums"

| | Input Song | Generated Stem | Overlapped | 
| --- | --------- | -------------- | ---- |
| 1 | <audio controls preload=False><source src="audio/33_input_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/33_output_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/33_mix_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


### 2. Piano

**Prompt**: "genre: rock, stem: piano"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_accompaniment.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| --- | --------- | -------------- | 
| 1 | <audio controls preload=False><source src="audio/song1_piano_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_piano_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song1_piano_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_piano_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


**Prompt**: "genre: electronic, stem: piano"

**Input song**: 

<audio controls preload=False><source src="audio/song2_no_piano.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| --- | --------- | -------------- |
| 1 | <audio controls preload=False><source src="audio/song2_piano_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_piano_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song2_piano_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_piano_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

----


### 3. Guitar

**Prompt**: "genre: rock, stem: guitar"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_accompaniment.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| --- | --------- | -------------- | 
| 1 | <audio controls preload=False><source src="audio/song1_guitar_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_guitar_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song1_guitar_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_guitar_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---

**Prompt**: "genre: pop, stem: guitar"

| | Input Song | Generated Stem | Overlapped | 
| --- | --------- | -------------- | ---- |
| 1 | <audio controls preload=False><source src="audio/8_input.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/8_output.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/8_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


### 4. Bass

**Prompt**: "genre: rock, stem: bass"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| ---| --------- | -------------- | 
| 1 | <audio controls preload=False><source src="audio/song1_bass_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_bass_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song1_bass_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_bass_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


**Prompt**: "genre: electronic, stem: bass"

**Input song**: 

<audio controls preload=False><source src="audio/song2_no_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| | Generated Stem | Overlapped | 
| --- | --------- | -------------- |
| 1 | <audio controls preload=False><source src="audio/song2_bass_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_bass_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/song2_bass_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_bass_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


**Prompt**: "genre: pop, stem: bass"

| | Input Song | Generated Stem | Overlapped | 
| --- | --------- | -------------- | ---- |
| 1 | <audio controls preload=False><source src="audio/18_input_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/18_output_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/18_mix_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


### 5. Percussion

| | Input song | Generated Stem | Overlapped | 
| --- | --------- | -------------- | ------ |
| 1 | <audio controls preload=False><source src="audio/0_input_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/0_output_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/0_mix_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/4_input_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/4_output_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/4_mix_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 3 | <audio controls preload=False><source src="audio/5_input_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/5_output_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/5_mix_perc.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |

---


## Temporal awareness examples

The following examples have bad audio quality, but good temporal awareness for the input song's phase. 

**Volume warning!**

Stem: guitar

| | Input song | Generated Stem | Overlapped | 
| --- | --------- | -------------- | ------ |
| 1 | <audio controls preload=False><source src="audio/12_input.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/12_output.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/12_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 2 | <audio controls preload=False><source src="audio/11_input.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/11_output.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/11_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| 3 | <audio controls preload=False><source src="audio/17_input.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/17_output.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/17_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |