Noise Sensor Implementation
===========================

!!! warning "Work in progress"

## Firmware

### Audio I2S Library

**[Audio I2S](https://github.com/oscgonfer/AudioI2S)**
Base library, intented to be generic purpose audio analysis library for an I2S Microphone on the SAMD21 with:

- FFT Analysis
- FIR Analysis
- Custom window selection
- Custom weighting function selection
- Custom buffer size and custom fft bin size (in case of FFT analyser)
- Custom equalisation
- Octave auto generation of .h files for coefficients and so on

### Smart Citizen Audio Library

**[Smart Citizen Audio](https://github.com/fablabbcn/smartcitizen-kit-audio)**
Library intented for firmware implementation in the SmartCitizen kit 2.0, with a better usage of memory and SCK related functionalities:

- FFT analysis
- Selection of A or C weighting through LUT
- Two user cases:
    - General audio analysis (sensorRead) with fixed buffer size and fixed FFT bins size (fs = 44,1kHz)
    - Audio Communication with FSK - with information transfer via audio

## Source files

<a class="github-button" data-size="large" href="https://github.com/fablabbcn/smartcitizen-kit-audio/archive/master.zip" data-icon="octicon-cloud-download" aria-label="Download from GitHub">Download</a>

<a class="github-button" data-size="large" href="https://github.com/fablabbcn/smartcitizen-kit-audio" aria-label="Check the source code">Check the source code</a>
