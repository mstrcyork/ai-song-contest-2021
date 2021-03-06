# ai-song-contest-2021
The paper trail of ideas and code in support of our submission to the 2021 AI Song Contest.

![](https://github.com/mstrcyork/ai-song-contest-2021/blob/main/audio_clips/draft_chorus_sm.mp3)

<audio controls>
  <source type="audio/mpeg" src="./audio_clips/draft_chorus_sm.mp3">
</audio>

## Sax riffs/solos
All the sax riffs and solos were assembled from samples generated using Chris Donahue's WaveGAN model, an audio-domain adaptation of the DCGAN architecture. An audio dataset of ~2hrs' length was created by Mark Hanslip, who recorded himself playing tenor saxophone in the intended key and tempo of the eventual song, applied some audio pre-processing (data augmentation, concatenation, silence truncation, resampling, chunking), and trained a WaveGAN on a single Titan RTX for ~4 days on the resulting dataset. 

## Lyrics

### Using instrumental audio for training
The lyrics generator was built based on a sequence to sequence model, where a user can input a line "Nothing's gonna change my love for you", and the model will probably output the next line "You oughta know by now how much I love you". Thus, a whole set of song lyrics can be generated by iteratively inputing the previous output. Addition to that, to make the generated lyrics contextually fit with the audio tracks, the input side also requires the audio features to that line. See [here](https://github.com/mstrcyork/ai-song-contest-2021/blob/main/conversations/agenda_and_convo_20210422.md) for dataset construction.

### theselyricsdonotexist.com
This [lyrics generator](https://theselyricsdonotexist.com/) was used to provide a series of song lyrics around input themes following specific genre (country, metal, rock, pop, dance, rap) and mood (very happy to very sad) conventions. This website's output can be used in combination with AI generated melodies to curate a song. It is up to the musician/songwriter to pick and select lyrics that'd match melodies or vice versa. 

## Ideas for melodies, chord sequences, basslines, and drum tracks
Came from the MAIA Markov algorithm. The seeds used can be found [here](https://github.com/mstrcyork/ai-song-contest-2021/tree/main/algorithms/run_maia_markov) in the four scripts with "generate" in their name. To replicate a generated result, one can go to [MAIA Suggest 2021](https://maia-suggest-2021.glitch.me), select the appropriate "gospel/pop" model, enter the seed (case-sensitive), and hit play. One should get exactly the same output as if one were to run the generate script from command line with Node.js. The state transition matrices and initial distributions are available at https://maia-suggest-2021.glitch.me/src/stm_etc/.

## Video
[Lynette, Mark, Jem to add some remarks as appropriate.]


## Music production
Unlike other phases of the song creation process, the production aspects are primarily concerned with curation, editing and presentation. Collaboratively the team experimented with and selected the core melodies, chords, basslines and drum patterns MIDI files generated in the earlier phases to create the skeleton of the piece. These musical elements were then assigned various timbres (primarily informed by the genre conventions one would associate with such drum patterns and chords). Some elements and files were edited (some atonality, velocity inconsistency, assymetric phrase lengths etc. were removed manually from the MIDI), but no patterns were expanded or otherwise added to. Vocals were recorded as audio. The piece was mixed and mastered manually.
