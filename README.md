# Experiments with Hunter remote fans

[FCC Info](https://fccid.io/IN2TX28)


## Protocol:

A 12-bit command is converted to a 3-symbol PCM encoding. A command 0 bit is encoded as LLH, and a command 1 bit is encoded as LHH. Each low or high symbol is sent by turning off or on the 350MHZ carrier wave. There is a single 0 (LLH) sent before the 12-bit command, which could be used as a clock sync. Each symbol is sent at 5280 baud (for ~190 microseconds each)

The DIP switches in the remote are labeled, left-to-right, 4321.

The first bit in the command is 0. Next are bits 1,2,3,4 of the DIP switch, as an address. Next are three 1 bits. The remaining four bits are the command:

- 1001 is Fan 0
- 0001 is Fan 1
- 0010 is Fan 2
- 0100 is Fan 3
- 1000 is Light Toggle

Hold the Light Toggle for at least a second to fade up one step.

