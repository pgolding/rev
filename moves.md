# Move Mapper

We have the following entities:

Workout **W** has the following properties:

- Duration **D**
- Style **S** is the type of workout - e.g. HIIT, endurance etc.
- Genre **G**
- Playlist **P** - a list of tracks in order of play
- Moves **M** - a list of choreographic sequences
- Instruction **I** - a verbal narrative for the track

A playlist **P** consists of a list of tracks **t**, each with

- song **s**
- beat (tempo) **b**
- length **l**
- pattern (structure) **P**

A choreographic sequence **C**:

- consists of activities **A**

For now, we will ignore dialog (verbal instruction).

**And so the problem statement is:**

Given **S** and **G** our goal is to generate a workout **W**.

We would assume the following to be available:

- A library (**L**) of tracks suitable for spinning
- A fixed set of possible styles
- A set of rules for what constitutes a viable sequence **C**



