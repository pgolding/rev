# Rev

An experiment in building a multi-user spin-cycle choreography system.

# General

Users will download a mobile app and use it to play the music whilst instructing a routine.

Users can monitor their stats and also join rides with others.

Joining rides with others need not be in "real time."

## Goals

- Construct a playlist dynamically
- Playlist should contain genre-specific music suitable for spinning
- Choreograph a routine of moves
- Map the moves to phases of the playlist consonant with the tempo
- Build a motivational instructor script time to the moves

## Breakdown of Parts

### Playlist

- We anticipate using music from a user's existing music library.
- Music tracks should be selected that are spin-appropriate
- Playlist should span a certain interval (30, 45, 60) minutes

### Choreography

- A routine should be constructed from standard spin moves (e.g. sprint, rest, hill-climb)
- Moves should matched to the tempo
- Moves should be phased to the appropriate musical phases per track

### Script Generation

- At a minimum, the script should instruct the user which move to adopt
- The script should prepare the user for a forthcoming move
- The script should count moves in (4,3,2,1 - Go)
- The script should contain motivational motifs

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