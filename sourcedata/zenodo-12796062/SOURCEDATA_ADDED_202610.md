# Original release files added to sourcedata/ (2026-10)

Added in the sourcedata completion pass of 2026-10: 2 files, 1.61 GB.

- code_figures.zip (figure scripts with their DATA.mat) and code_pipeline.zip (the authors' analysis pipeline neuroHammer with bundled third-party functions and MNI/colin27 template atlases, no participant imaging) of Zenodo record 12796062.

Changes for privacy:

- Both zips are REPACKED, not byte-identical to Zenodo: same members, names and order; member timestamps set to day 01; 20 members edited at fixed length: MAT header 'Created on' day -> 01, date strings in text/code -> day 01 (incl. one recording-session folder name YYYYMMDD_hhmm in loadCutData/getParadigmEvents.m), PDF/xlsx metadata dates -> day 01. All other member bytes unchanged.
- MAT 7.3 figure data (DATA.mat): every char dataset scanned, no dates or identifiers.

Before upload every added file passed the campaign privacy gate (file names, text, MAT headers and strings, zip member names and text members: no day-of-month other than 01, no names or identifiers). Third-party code keeps its authors' copyright/version dates and e-mail addresses (reviewed: not participant data).
