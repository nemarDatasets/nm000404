# Internal-external attention switching: SEEG epochs from 25 epilepsy patients (derivative)

Stereo-EEG epochs released with:

> Hammer J, Kajsova M, Kalina A, Krysl D, Fabera P, Kudr M, Jezdik P, Janca R, Krsek P, Marusic P (2024).
> Antagonistic behavior of brain networks mediated by low-frequency oscillations: electrophysiological dynamics during
> internal-external attention switching. *Communications Biology* 7:1105. https://doi.org/10.1038/s42003-024-06732-2

Source record: Zenodo https://doi.org/10.5281/zenodo.12796062 (v3, CC-BY-4.0): `msSEI_exportTrials.zip`.

**This is a derivative dataset.** The release contains the authors' preprocessed epochs, not the continuous recordings.

## Participants and task (from the paper)

25 patients with drug-resistant epilepsy (15 female; age 34 +/- 12 years) in presurgical SEEG monitoring at Motol
University Hospital, Prague; implantation by clinical need only; approved by the hospital's ethics committee; written
informed consent. Per-subject age and sex are not in the release (`n/a`).

Subjects alternated between an external-attention task (visual search: find the T among 35 Ls on a 6x6 grid and report
whether it is in the upper or lower half) and an internal-attention task (yes/no answer to a statement about their own
past experiences), answering on a gamepad within 5 s, with no pause between trials and not switching on every trial.
Four sessions of several minutes (about 30 min). Each epoch is centred on a task switch: `E-I` (external to internal)
or `I-E` (internal to external).

## Recording and preprocessing (by the authors)

DIXI Medical depth electrodes, Quantum amplifiers / NeuroWorks, 2048 Hz (0.01-682 Hz), reference and ground in white
matter. The authors downsampled to 512 Hz, removed broken channels and channels in the seizure-onset or irritative zone
or in heterotopic cortex, built bipolar derivations along each shank, high-pass filtered at 0.1 Hz and notch filtered at
50 Hz and harmonics (Butterworth, 6th order, zero phase), cut epochs from -4 to +4 s around each switch, and kept only
channels assigned to the default mode network (DMN) or dorsal attention network (DAN) by the Yeo-7 atlas.

## Files

- `sub-P<k>/ieeg/*_ieeg.vhdr|.eeg|.vmrk`: the epochs written back to back (4097 samples = 8.002 s each), BrainVision
  IEEE float32. Values are the release's float64 values rounded to float32; no other change. The release does not
  state the physical unit; the channels are labelled µV because amplitudes of a few to tens of units match µV-scaled
  iEEG, but this is our assumption, not a statement of the authors.
- `*_events.tsv`: one row per epoch at the switch time, with `trial_type` (E-I / I-E), epoch number, epoch start and the
  fraction of samples marked rejected in the release.
- `*_channels.tsv`: bipolar channel names as released, with the `network` label (DMN / DAN).
- `*_space-Other_electrodes.tsv`: the release's MNI coordinates per bipolar channel.
- `sourcedata/zenodo-12796062/`: the original `trials_P<k>.mat` files (including the per-sample rejection masks) and the
  release read-me, unchanged.

The figure source data (`code_figures.zip`) and analysis code (`code_pipeline.zip`) of the record are not copied; they
are available from the source record and GitHub.

## Licence

CC-BY-4.0, as the source record. Please cite the paper and the Zenodo record.
