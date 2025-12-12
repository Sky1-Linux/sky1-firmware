# sky1-firmware

Firmware files for CIX Sky1 SoC (Radxa Orion O6 and compatible boards).

## Contents

| Firmware | Description | Driver |
|----------|-------------|--------|
| `mali_csffw.bin` | Mali-G720 CSF firmware | Panthor (GPU) |
| `dsp_fw.bin` | Tensilica HiFi5 audio DSP firmware (rpMSG-lite) | CIX DSP rproc |
| `*.fwb` | Video codec firmware | VPU (V4L2) |

## Audio DSP

The Sky1 audio DSP is a Cadence Tensilica HiFi5 core communicating via rpMSG-lite protocol.
Used for audio processing and offload.

## Video Codecs Supported

| Codec | Decode | Encode |
|-------|--------|--------|
| AV1 | av1dec.fwb | - |
| HEVC/H.265 | hevcdec.fwb | hevcenc.fwb |
| H.264/AVC | h264dec.fwb | h264enc.fwb |
| VP9 | vp9dec.fwb | vp9enc.fwb |
| VP8 | vp8dec.fwb | vp8enc.fwb |
| JPEG | jpegdec.fwb | jpegenc.fwb |
| MPEG-2 | mpeg2dec.fwb | - |
| MPEG-4 | mpeg4dec.fwb | - |
| VC-1 | vc1dec.fwb | - |
| AVS/AVS2 | avsdec.fwb, avs2dec.fwb | - |

## Installation

```bash
# From Sky1 Linux repository
sudo apt install sky1-firmware

# Or build locally
dpkg-buildpackage -us -uc -b
sudo dpkg -i ../sky1-firmware_*.deb
```

## License

These firmware files are proprietary and redistributable under their respective licenses:
- Mali firmware: ARM Ltd.
- VPU/DSP firmware: CIX Technology

## Links

- [Sky1 Linux](https://sky1-linux.org)
- [linux-sky1 kernel](https://github.com/sky1-linux/linux-sky1)
