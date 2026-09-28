# SlideScope

**Desktop digital pathology and microscopy viewer for Windows and macOS.**

SlideScope opens whole slide images from the major slide scanners and research microscopy
files in one window, on your own computer, with no image server. It reads the image pyramid
the scanner already wrote, so a multi-gigabyte slide opens in seconds on an ordinary laptop.

- Website: https://slidescope.science/
- Download: https://slidescope.science/en/downloads/
- Release notes: https://slidescope.science/en/release-notes/
- Supported formats: https://slidescope.science/en/supported-file-formats/
- Format compatibility details: https://slidescope.science/microscopy-file-compatibility/
- Format benchmark (792 real files, raw results as JSON): https://slidescope.science/microscopy-format-benchmark/

## Formats

| Source | Formats |
|---|---|
| Aperio / Leica Biosystems | SVS, SVSLIDE |
| Hamamatsu NanoZoomer | NDPI, VMS, VMU |
| 3DHISTECH Pannoramic | MRXS |
| Leica SCN400 / GT450 | SCN |
| Ventana / Roche | BIF |
| Akoya / PerkinElmer Vectra | QPTIFF |
| Agilent | AVS |
| Vendor-neutral | DICOM (including whole-slide DICOM), pyramidal TIFF, OME-TIFF |
| Research microscopes | ZEISS CZI, Nikon ND2, Leica LIF, Imaris IMS |

MRXS, VMS and VMU keep their pixels in a companion folder, so open them from local storage.

**Not supported:** Philips iSyntax, Olympus VSI, OIB and OIF, ZEISS LSM and ZVI, and OME-Zarr.
Export those to OME-TIFF or pyramidal TIFF in the acquisition software or at the scanner, then
open the export in SlideScope.

## What it does

- **Viewing.** Smooth pan and zoom across gigapixel slides. The zoom controls sit on the slide,
  with Fit, actual pixels (1:1) and preset levels. The status bar shows the position and pixel
  value under the pointer. Z-stacks, time series, channels and multi-scene files each have
  their own navigation.
- **Colour and channels.** Channel colours, display ranges and channel names are read from ZEN,
  NIS-Elements, LAS X, Imaris, Fiji, Micro-Manager and Vectra files. Brightness, contrast,
  gamma and a composite view are adjusted for display only; the pixels are never changed.
- **Calibrated measurement.** Lengths, perimeters and areas in micrometres, from the pixel size
  the scanner or microscope recorded.
- **Annotations.** Notes, numbered markers and regions stay attached to the slide in your
  account. Export them as GeoJSON (see [`examples/`](examples/)) and export measurements as CSV.
- **Side-by-side comparison** of two slides at matched physical scale.
- **Shared views.** A link that reopens an exact field of view: the slide, position, zoom and
  plane.
- **Export.** Standard OME-TIFF with pixel size, channel names and colours, which Fiji,
  QuPath and OMERO open at the right scale.
- **Local Quantification.** Nuclei, cell and particle counts computed on your own computer.
- **AI Analysis (optional).** A plain-language description of the current view, in 14
  languages. It is off unless you choose to use it.

## Platforms and price

- Windows 10 and later, macOS 14 and later (Apple Silicon and Intel).
- Windows builds are code-signed; macOS builds are signed and notarised by Apple.
- Also available from the [Microsoft Store](https://apps.microsoft.com/detail/xpdlmkv6zm2prt)
  and the [Mac App Store](https://apps.apple.com/us/app/slidescope-microscopy-viewer/id6803618767).
- A 3-day full-access trial, then a monthly or annual subscription. Plans for individuals and
  labs: https://slidescope.science/plans/

## Scope

SlideScope is for research, education and review. It is not a medical device and is not
cleared for primary diagnosis.

## This repository

This repository holds public reference material for SlideScope:

- [`examples/annotations.geojson`](examples/annotations.geojson): a GeoJSON export written by
  SlideScope's own exporter, with notes on its fields in [`examples/README.md`](examples/README.md).
- [`CITATION.cff`](CITATION.cff): how to cite SlideScope in a paper. GitHub shows it under
  "Cite this repository".

The application itself is proprietary. It is distributed only from
[slidescope.science](https://slidescope.science/) and the app stores, never from this
repository.

## Help

Questions, bug reports and format requests: **support@slidescope.science**, or the Support button
inside the app. See [SUPPORT.md](SUPPORT.md). Please never send patient-identifiable images or data.
