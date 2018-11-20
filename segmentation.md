# Musical Structure Analysis (Segmentation)

We want to find segments of self-similar musical structure. Or, more broadly, we want to know the structure of the music.

Our concern here is mostly for EDM or pop music as the two prominent genres for spin cycling.

# Musical Background

We should obviously know the inherent hierarchies in the target genres.

[This tutorial](https://subaqueousmusic.com/dubstep-and-electronic-music-song-structure/) about EDM (and pop) song structure is a good start.
The author also provides a [composition toolkit for Ableton](https://subaqueousmusic.com/quick-and-easy-composition-tricks/) that has a variety of song structure breakdowns.

We should be able to use this to provide some sequence structure probabilities, inc. section lengths etc.

Typical structure is:

- **Intro**: The intro is pretty much anything you want it to be. Many songs start with just the melody that is rising up. You can even create a melodic question that is answered by the rest of the song or something of the sort. The important thing is to not stay too long at the intro, and make it tie in quickly.
- **Verse**: The Verse is the first main part of your melody and story of your arrangement. It repeats a few times before moving on to the chorus. Verses are usually used in music with lyrics. Music with a verse, or verse like aspects, can do really well by ending the melodic and harmonic line with tension. Either with an I chord or a V chord and then resolve it in the chorus.
- **Chorus**: This is the main part of the song. It is the hook, the thing you want people to remember and has most of the power of the song. This part should have energy and be no longer than the verse. It will usually repeat like: Verse, Chorus, Verse, and chorus.
- **Solo**: This can be used anytime, preferably after a round or two of chorus and verse, to add a little jam feel. Used a lot in jazz and can really create cool sections in music. When you are thinking of live performance Solo parts are always fantastic, even if it’s not in your released track.
- **Break** or sometime Bridge: This is used to break up what the listener has paid attention to. In electronic music you usually take out the drums and add a rising sound to the next part. A bridge / break can be more powerful by adding new instruments or changing the key. Try to keep this at 8 measures or less.
- **Riser**: A Riser is just like a break except that it is arpeggiating or having some sort of buildup that is released with the next section coming in. Usually no beat and last 8 measures or 16. When the next part comes in, it will have a lot more energy and should be the climax of the piece.
- **Outro**: This is used to resolve the song and come in for a smooth landing. Some son’s don’t have an outro and others have a long outro. You can also add a final sense by adding a Coda, or strong cadence at the end of your track.

[This article](https://www.edmprod.com/beatport-analysis/) is an analysis of 100 top tracks on Beatport.

He claims there are 17 structures overall and the breakdown of most common is shown below using the folded segments:

For the sake of simplicity I settled on three categories of song sections:

- A: Can mean verse, alternative section, break, or common build-up
- B: Can mean drop or chorus – main section
- C: Bridge, main breakdown, or section of song that differs musically

A common pop structure, for instance, would be something like ABABCB (verse, chorus, verse, chorus, bridge, chorus).

![](https://ysb9sqrtp8-flywheel.netdna-ssl.com/wp-content/uploads/2015/07/8structures-e1438142959121.png)

Of other note:

- The average BPM of all 100 tracks is 124.56.
- More minor key than major key with A-Minor the most popular

[This article](https://www.soundontime.com/song-structure/) explains more about structure and typical bars/phrase structure.
Dance music typically follows 8-bar, 16-bar and 32-bar sequencing.

# Technical Approaches

## State of the Art & Background Etc.

[This paper](docs/structure_sofart.pdf) provides a good state-of-art background to music structure analysis.

A summary of ideas is presented next.

### Summary of State of Art (Music Analysis)

#### General Approach

Per the intro: _"In particular, one can identify three conceptually different approaches, which we refer to as repetition-based, novelty-based, and homogeneity-based approaches."_

_"Firstly, repetition-based methods are employed to identify recurring patterns. From a technical point of view, these methods are also often referred to as sequence approaches, see also Sec. 5. Secondly, novelty- based methods are used to detect transitions between con- trasting parts. Thirdly, homogeneity-based methods are used to determine passages that are consistent with respect to some musical property. Note that novelty-based and homogeneity-based approaches are two sides of a coin: novelty detection is based on observing some surprising event or change after a more homogenous segment."_

#### Features

Any analysis obviously requires feature extraction, but what features?
Features will be computed in a block-based (window) fashion - i.e. sequences of sound samples.

Timbre (i.e. "musical quality") structure analysis is common and entails mel-frequency cepstral co- efficients (MFCCs).

MFCCs are from Discrete Cosine Transform (DCT) of log-power spectrum on the mel-frequency scale.

![screenshot 2018-11-18 12 33 37](https://user-images.githubusercontent.com/28526/48677755-5f053580-eb2e-11e8-86ac-75491e6caf74.png)

where the subbands b are uniformly distributed on the mel- frequency scale and E(b) is the energy of band b. A generally accepted observation is that the lower MFCCs are closely related to the aspect of timbre.

Alternative methods include [constant-Q spectrograms](docs/constant-Q.pdf).







## Analysis of Papers/Ideas

### McFee Spectral Clustering Approach

We dedicate a section to this paper due to the substantial background techniques - e.g. spectral clustering - that also need elaborating.

A method by Brian McFee as used in [Librosa](http://librosa.github.io/librosa/) - see [Laplacian Segmentation](http://librosa.github.io/librosa/auto_examples/plot_segmentation.html#sphx-glr-auto-examples-plot-segmentation-py)
uses [Spectral Clustering]() - see [McFee's paper here](/docs/ismir2014_spectral_segmentation.pdf)

Some technical background resources:

- [Video explaining spectral clustering](https://www.youtube.com/watch?v=P-LEH-AFovE) in general
- [Video explanation of Laplacian](https://www.youtube.com/watch?v=zkgm0i77jQ8)
- [Another video for spectral clustering](https://www.youtube.com/watch?v=jgsJZYGeAz4)
With a seminal video [here](https://www.youtube.com/watch?v=9BqbktGo2Vs&index=10&list=PLdk2fd27CQzT7opzoGHvqDuDbltozWn7O)

We want to analyze the [approach of McFee](/docs/ismir2014_spectral_segmentation.pdf)

