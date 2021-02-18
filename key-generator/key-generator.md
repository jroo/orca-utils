# Orca Key Generator

Given a root and a key, create eight variables to hold each note in the key.

## Usage

In [example.orca](./key-generator.orca), use the code between `# set key #` and `# end #` to generate the variables that store the notes in a key.

#### Setting the key

The `r` variable holds the value to the root note that will be generated. Assigning a value of `0` to this variable will generate a `C` key. Values for all keys below:

| `r` | note |
| --- | ---  |
|  0  |  A   |
|  1  |  a   |
|  2  |  B   |
|  3  |  C   |
|  4  |  c   |
|  5  |  D   |
|  6  |  d   |
|  7  |  E   |
|  8  |  F   |
|  9  |  f   |
|  a  |  G   |
|  b  |  g   |

The value set in the `k` variable will determine if the key is major or minor. `1` sets the key to major and `0` sets it to minor. 

| `k` | key   |
| --- | ---   |
| 0   | minor |
| 1   | major |

The code below will set the key to E minor.

```
rV7.#.root.#
kV0.#.key..#
```
#### Using the variables created

Eight variables are created with the names `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`. Each of these holds a value that is a **"universal position"**, or the number of half steps 
the note is above C. 

|Position|0|1|2|3|4|5|6|7|8|9|a|b|c|d|e|f|g|h|i|j|k|l|m|n|
|---     |-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Note    |A|a|B|C|c|D|d|E|F|f|G|g|A|a|B|C|c|D|d|E|F|f|G|g|

#### Playing a scale

The following block of code will set the key to G major and play a scale of all of the notes generated.
```
rVa.#.root.#.............................................
kV1.#.key.#................Vk..............Vk....Vk......
........................Vr.1............Vr.1..Vr.1.......
...............Vr...Vr..5A3J...Vr...Vr..5A8J..5AaJ...Vr..
...............5A0..5A2..8A1...5A5..5A7..dA1...fA1...5Ac.
..............0V5..1V7..2V9...3Va..4Vc..5Ve...6Vg...7Vh..
.........................................................
#.generate.scale.positions.#.............................
.........................................................
.4C8.#.scale.#...........................................
pV4......................................................
.........................................................
#.convert.universal.values.to.notes.and.octaves.#........
.........................................................
..Vp...........................Vp........................
.V4...........................V4.........................
.coTCcDdEFfGgAaBCcDdEFfGgAaB..coT222222222222333333333333
.nVC..........................oV3........................
.........................................................
#.send.note.to.midi.channel.2.#..........................
.........................................................
5K...on..................................................
.....3C..................................................
..D43JJ..................................................
...%13C8f................................................
```
