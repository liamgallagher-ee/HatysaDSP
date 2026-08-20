# HatysaDSP

A stereo hardware audio platform built around the Nucleo-G431RB evaluation board.

This platform is built off the TLV320AIC3104 stereo audio codec. This codec has I2S audio, capable of 48kHz or 96kHz, depending on the desired DSP load on the STM32G431RBTx. This also uses I2C control in order to give flexibility with the biquad filter, volume control, and flexible routing.

This hardware also has three analog potentiometers to provide user control for three parameters.

<img width="943" height="903" alt="image" src="https://github.com/user-attachments/assets/1eb83206-b77d-4f97-9939-d17c265892ac" />

---
## Usage

Using the stereo audio codec requires the Nucleo-G431RB to have some setup. The STM32G431 requires the SAI1 peripheral to be setup, as well as I2C_2, and GPIO setup for ADC inputs on pin PA0, PA15, and PB14.

For the clock tree, because of the lack of a dedicated audio PLL, this requires the PLL setup to output a integer multiple of the desired 256 x sampling rate (12.288MHz multiple.) This is a WIP.
