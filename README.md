# Semantic FM Dataset

A dataset of interconnected FM synthesiser patches with comparative semantic tags, as well as rich metadata. This data was collected as part of a perceptual study on the semantic associations of FM synthesis [1]

Participants created FM synthesiser patches using a three operator architecture in response to semantic prompts. They also rated the magnitude of the difference between the created patch and the starting patch in terms of 27 semantic descriptors.

## Dataset contents

Audio files are presented in two folders: `audio_long` contains 4 second renderings of the synth patches with a 3-second gate followed by 1-second of release. `audio_short` contains 1.25 second renderings of the synth patches with a 1-second gate followed by 0.25-seconds of release. Audio is all presented in 16-bit 44.1kHz PCM WAV files.

```
audio_long/
  - 00c4b7cf43ca323183879f32e0d500d0.wav
  - 018bcee372474b8758dab4811651c055.wav
  - ...
audio_short/
  - 00c4b7cf43ca323183879f32e0d500d0.wav
  - 018bcee372474b8758dab4811651c055.wav
  - ...
metadata.csv
README.md
```

### Metadata Format

The following metadata is provided (presented in `metadata.csv` heading order):

* `synth_id` — Unique identifier of synthesiser patch
* `reference_synth_id` — Unique identifier of reference synthesiser patch (from which participants started the synthesis process)
* `participant_id` — Unique identifier of participant
* `prompt` — The semantic prompt given to the participant (e.g. tweak these parameters to make this sound _rougher_)
* `prompt_descriptor` — The root word of the semantic prompt given to the participant
* `prompt_direction` — The "direction" (positive or negative) of the prompt
* `delta_*` — The amount by which the relevant synthesiser parameter was changed from the starting reference position
* `param_*` — The final value of the relevant synthesiser parameter
* `ref_*` — The starting reference value of the relevant synthesiser parameter
* `bright` to `plucky` — A comparative semantic rating (on a scale of -10.0 to 10.0) between the starting reference patch and the final created patch
* `note` — The MIDI note at which both the reference and created patch were played
* `semantic_factor_*` — The patch's score along each of the 5 semantic factors (see [1] for more info)
* `msi_*` — The participant's response to Goldsmiths Musical Sophistication Index subscales (see [2] for more info)
* `age` — The participant's age
* `country_childhood` — The country in which the participant spent the formative years of their childhood
* `country_residence` — The country in which the participant resided at the time of participation
* `stft_mag_centroid_median` to `zero_crossing_rate` — A large number of acoustic features extracted on each sound
* `acoustic_component_*` — The patch's score along each of 4 principal components extracted from the acoustic features
* `delta_acoustic_component_*` — The difference between this patch's score and the reference patch's score on each of the principal components

## References

[1] B. Hayes and C. Saitis, ‘There’s more to timbre than musical instruments: semantic dimensions of FM sounds’, presented at the Timbre, Thessaloniki, Greece (Online), 2020, Advance online publication.

[2] D. Müllensiefen, B. Gingras, J. Musil, and L. Stewart, ‘The Musicality of Non-Musicians: An Index for Assessing Musical Sophistication in the General Population’, PLOS ONE, vol. 9, no. 2, p. e89642, Feb. 2014, doi: 10.1371/journal.pone.0089642.
