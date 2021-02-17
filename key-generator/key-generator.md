# Orca Key Generator

Given a key and a relative, create eight variables to hold each note in the key.

## Usage

In [example.orca](./key-generator.orca), use the code between `# set key #` and `# end #` to generate the variables that store the notes in a key.

#### Setting the key

The `k` variable holds the value to the key that will be generated. Assigning a value of `0` to this variable will generate a `C` key. Values for all keys below:

| `k` | key |
| --- | --- |
|  0  |  C  |
|  1  |  c  |
|  2  |  D  |
|  3  |  d  |
|  4  |  E  |
|  5  |  F  |
|  6  |  f  |
|  7  |  G  |
|  8  |  g  |
|  9  |  A  |
|  a  |  a  |
|  b  |  B  |
|  c  |  C  |

The value set in the `r` variable will determine if the key is major or minor. `1` sets the key to major and `0` sets it to minor. 

| `r` | relative |
| --- | ---      |
| 0   | minor    |
| 1   | major    |

The code above will set the key to E minor.

```
kV4.#.key #.....
rV0.#.relative.#
```
#### Using the variables created

Eight variables are created with the names `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`. Each of these holds a value that is a **"universal position"**, or the number of half steps 
the note is above C. 

|Position|0|1|2|3|4|5|6|7|8|9|a|b|c|d|e|f|g|h|i|j|k|l|m|n|o|
|---     |-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Note    |C|c|D|d|E|F|f|G|g|A|a|B|C|c|D|d|E|F|f|G|g|A|a|B|C|


#### Playing a scale

The following block of code will loop through and play a scale of all of the notes generated.
```
kV5.#.key......#.........................................
rV1.#.relative.#...........Vr..............Vr....Vr......
........................Vk.1............Vk.1..Vk.1.......
...............Vk...Vk..5A3J...Vk...Vk..5A8J..5AaJ...Vk..
...............5A0..5A2..8A1...5A5..5A7..dA1...fA1...5Ac.
..............0V5..1V7..2V9...3Va..4Vc..5Ve...6Vg...7Vh..
.........................................................
#.generate.scale.positions.#.............................
.........................................................
.4C8.#.scale.#...........................................
pV7..#.......#...........................................
.........................................................
#.convert.universal.values.to.notes.and.octaves.#........
.........................................................
..Vp...........................Vp........................
.V7...........................V7.........................
.hoTCcDdEFfGgAaBCcDdEFfGgAaB..hoT222222222222333333333333
.nVF..........................oV3........................
.........................................................
#.send.note.to.midi.channel.2.#..........................
.........................................................
5K...on..................................................
.....3F..................................................
..D43JJ..................................................
...%13F8f................................................
```


