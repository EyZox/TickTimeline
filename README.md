# TickTimeline

A queue of (tick :int, elements :Collection<E>)

Theses sources are originally developed for a Minecraft mod [ForgeCreeperHeal](https://github.com/EyZox/ForgeCreeperHeal) in order to contains scheduled block for a replacement in a right order.

License : [MIT](https://opensource.org/licenses/MIT)

## Basic overview

### Input :

{(1,{A}), (1,{B}), (3,{C,D}), (2,E)}

### Output :

     * A -> after tick() called once
     * B -> after tick() called twice (A ticks + B ticks)
     * {C,D} -> after tick() called 5 times (A ticks + B ticks + (C,D) ticks)
     * E -> after tick() called 7 times (A ticks + B ticks + (C,D) ticks + E ticks)
     
## Insertion

### Initial State :

{(1,{A}), (1,{B}), (3,{C,D}), (2,E)}

### Input :

(3, {Z})

### Output :

{(1,{A}), (1,{B}), (1,{Z}), (2,{C,D}), (2,E)}