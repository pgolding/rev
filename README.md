# Rev

An experiment in building a multi-user spin-cycle choreography system.

**NOTE:** This was a hobby project that I started as an avid spin-cycle fan. I didn't have time to get a working prototype, but I am sharing this
repo in case my initial thoughts/research are of use to others inclined towards solving the "AI Spin Instructor problem."

My motivation was to create an app that would allow me to "join" a virtual spin class wherein the music was auto-curated (mostly from EDM recommendations) or self-curated.
Using AI, the goal was to create the instructor voice-over (along with motivational exhortations) from a pre-recorded voice-over library. My previous work in
various NLP projects (and automated product descriptions) would guide this part of the project.

Put briefly, I wanted to create an alternative to the ridiculously over-priced and poorly executed Peloton app (in the app store).

I wanted to have the ability to choose "better" music (with heavy EDM influence) and, eventually, create any visuals I wanted to motivate the ride.
For me, just watching an instructor in a remote studio lacks any kind of imagination. It is an example of "digitized" experience versus a native "digital" experience -- a
mistake made so often that I have become bored of explaining it. (If you search wide enough, you might find me talking/presenting about this.)

## Why Spin? Which Spin (Flavor)?

My love of spin began in the UK when I attended spin classes at a David Lloyd gym.
The official classes followed the RPM franchise, which is fairly high energy program with great choreography and music (mostly).

However, one of the instructors would perform her own classes that were more EDM oriented with big ("MASSIVE") tracks, esp. SHM.
Moreover, she, like most good RPM instructors, choreographed routines wherein the moves, especially the peddling, where **exactly matched to the tempo of the music.**

A **massive pet hate** of mine is any spin instructor who peddles off-beat.
WTF? It makes no sense whatsoever and causes a great deal of dissonance.

As a spin enthusiast in her classes, I frequently choreographed routines for inclusion in her library. As a glutton for punishment,
I often favored standing-sprint intervals that would transition via a big drop to a standing climb on huge gears.
This kind of move is really only possible using a Kaiser bike, or similar, with an instant-change gear paddle versus the retarded screw-tightener control (which I loathe).

I have since choreographed many such tracks and entire play lists for my own workouts.
Frankly, I wish I were a spin instructor, but that's for another time or life.

So, the objective with `Rev` is/was to replicate this kind of experience, but any time, any place (solo or class) using technology.

# General

Users will download a mobile app and use it to play the music whilst instructing a routine.

Users can monitor their stats and also join rides with others.

Joining rides with others need not be in "real time."

## Goals

- Construct a playlist dynamically
- Playlist should contain genre-specific music suitable for spinning (esp. EDM)
- Choreograph a routine of moves
- Map the moves to phases of the playlist/tracks consonant with the tempo, energy and move
- Build a motivational instructor script timed to the moves

## Breakdown of Parts

### Playlist

- We anticipate using music from a user's existing music library (or a streaming service with curated playlists).
- Music tracks should be selected that are "spin-appropriate"
- Playlist should span a certain user-defined interval (30, 45, 60) minutes

### Choreography

- A routine should be constructed from standard "spin moves" (e.g. sprint, rest, hill-climb, standing-sprint etc.)
- Moves should be matched to appropriate tempo/energy segments (see [Segmentation](segmentation.md))
- Moves should be phased to the appropriate musical phases per track including transitional phases

### Script Generation

- At a minimum, the script should instruct the user which move to adopt
- The script should prepare the user for a forthcoming move
- The script should count moves in (4,3,2,1 - Go)
- The script should contain motivational motifs ("exhortations")

## Technical Challenges

Nominally we imagine a machine that can select suitable tracks and dynamically
map routines to the playlist. A key technical challenge is identifying
tracks and mapping routines to phases in the track that are satisfying to
listeners/participants - i.e. the moves are highly correlated to the musical
passages of the tracks.

### Playlist

See [playlist](playlist.md)

### Choreography

See [choreography](choreography.md)

### Script Generation

See [script](script.md)