[`arXiv`](https://arxiv.org/abs/2407.14358): Stable Audio Open paper

[`HuggingFace`](https://huggingface.co/stabilityai/stable-audio-open-1.0): model weights

[`stable-audio-tools`](https://github.com/Stability-AI/stable-audio-tools): code to reproduce Stable Audio


Stable Audio Open generates variable-length (up to 47s) stereo audio at 44.1kHz from text prompts. It comprises three components: an autoencoder that compresses waveforms into a manageable sequence length, a T5-based text embedding for text conditioning, and a transformer-based diffusion (DiT) model that operates in the latent space of the autoencoder.

## Exercise: Which missing stem is AI generated?

|    | Song without a stem | The missing stem | Overlapped |
| -- | ----- | -------------| ---------- |
| 1  |  <audio controls preload=False><source src="audio/2_input_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/2_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/2_drums_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio>  |
| 2 | <audio controls preload=False><source src="audio/1_input_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1_piano.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1_piano_mix.wav" type="audio/mpeg">Audio not supported by your browser.</audio>  |
| | | |

<details>
    <summary>Answer: </summary>
    All of them are AI generated. 
</details>


## Generation examples

### 1. Drums

**Prompt**: "genre: rock, stem: drums"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

 Generated Stem | Overlapped | 
| --------- | -------------- | 
| <audio controls preload=False><source src="audio/song1_drums_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_drums_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song1_drums_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_drums_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song1_drums_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_drums_mix_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|

**Prompt**: "genre: electronic, stem: drums"

**Input song**: 

<audio controls preload=False><source src="audio/song2_no_drums.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| Generated Stem | Overlapped | 
| --------- | -------------- |
| <audio controls preload=False><source src="audio/song2_drums_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_drums_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song2_drums_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_drums_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song2_drums_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_drums_mix_3.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|


### 2. Piano

**Prompt**: "genre: rock, stem: piano"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_accompaniment.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

 Generated Stem | Overlapped | 
| --------- | -------------- | 
| <audio controls preload=False><source src="audio/song1_piano_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_piano_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song1_piano_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_piano_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|


**Prompt**: "genre: electronic, stem: piano"

**Input song**: 

<audio controls preload=False><source src="audio/song2_no_piano.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| Generated Stem | Overlapped | 
| --------- | -------------- |
| <audio controls preload=False><source src="audio/song2_piano_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_piano_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song2_piano_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_piano_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|




### 3. Guitar

**Prompt**: "genre: rock, stem: guitar"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_accompaniment.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

 Generated Stem | Overlapped | 
| --------- | -------------- | 
| <audio controls preload=False><source src="audio/song1_guitar_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_guitar_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song1_guitar_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_guitar_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|


### 4. Bass

**Prompt**: "genre: rock, stem: bass"

**Input song**:

<audio controls preload=False><source src="audio/song1_no_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

 Generated Stem | Overlapped | 
| --------- | -------------- | 
| <audio controls preload=False><source src="audio/song1_bass_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_bass_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song1_bass_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song1_bass_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|

**Prompt**: "genre: electronic, stem: bass"

**Input song**: 

<audio controls preload=False><source src="audio/song2_no_bass.wav" type="audio/mpeg">Audio not supported by your browser.</audio>

| Generated Stem | Overlapped | 
| --------- | -------------- |
| <audio controls preload=False><source src="audio/song2_bass_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_bass_mix_1.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/song2_bass_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/song2_bass_mix_2.wav" type="audio/mpeg">Audio not supported by your browser.</audio> |
|

### 5. Percussion