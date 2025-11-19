Neuroimaging Data Collected During Kinesthetic Motor Imagery of Walking vs. Rest
-------------------------------------------------------------------------------
This dataset includes multimodal neuroimaging recordings from five participants performing kinesthetic motor imagery (KI) while viewing themselves walking in an exoskeleton. The recordings combine MRI (structural and functional) and EEG data, organized according to the BIDS specification.

MRI sessions were conducted after participants completed nine sessions of EEG‑controlled exoskeleton walking and standing experiments. doi:10.18112/openneuro.ds006940.v1.0.0

MRI Acquisition:
- Scanner: Philips Ingenia 3.0T (Koninklijke Philips N.V., The Netherlands)
- Structural scans: T1‑weighted anatomical images
- Functional scans (fMRI): Participants viewed a 10‑minute video of themselves walking in the exoskeleton, filmed from a first‑person perspective. The video contained 11 Stop‑Walk‑Stop (SWS) cycles. During viewing, participants were instructed to evoke KI in synchrony with the exoskeleton movements.
- Baseline condition: Participants mentally simulated resting state for approximately 5 minutes while fMRI data was recorded.

EEG Acquisition:
- MR‑compatible EEG cap (Brain Products GmbH, Gilching, Germany)
- Electrode locations are provided in EEGLAB format, with the actual digitized positions captured using the FASTRAK® system (Polhemus, Colchester, VT, USA).
- 59 scalp channels + 4 EOG channels + 1 ECG channel

Stimuli:
- A video stimulus (`stimuli/walking_exoskeleton_video.mp4`) was presented during walking tasks.
- The video is referenced in the respective JSON sidecars for both fMRI and EEG tasks.

Participants:
Five healthy adults out of seven participated in the EEG‑controlled exoskeleton experiments.
Participants S6 and S7 did not undergo MRI scanning due to a pause in data collection during the COVID‑19 pandemic.

Folder Structure (Example: Subject 01)
--------------------------------------
├── dataset_description.json
├── derivatives
│          └── validation
│           |              └── MRI_DataValidation.xls
 |            |
│          └── sub-01
│                       └── ses-01
│                                     ├── anat
│                                     │          └── sub-01_ses-01_T1w.nii
│                                     ├── dwi
│                                     │          ├── sub-01_ses-01_run-001_dwi.json
│                                     │          └── sub-01_ses-01_run-001_dwi.nii.gz (weighted)
│                                     └── spm
│                                                   ├── sub-01_ses-01_beta_0001.nii
│                                                   ├── sub-01_ses-01_beta_0002.nii
│                                                   ├── ...
│                                                   ├── sub-01_ses-01_con_0001.nii
│                                                   ├── ...
│                                                   ├── sub-01_ses-01_spm.mat
│                                                   └── sub-01_ses-01_spmt_0004.nii
├── stimuli
│           └── walking_exoskeleton_video.mp4
├── sub-01
│   └── ses-01
│       ├── anat
│       │   ├── sub-01_ses-01_T1w.json
│       │   └── sub-01_ses-01_T1w.nii
│       ├── eeg
│       │   ├── sub-01_ses-01_coordsystem.json
│       │   ├── sub-01_ses-01_electrodes.json
│       │   ├── sub-01_ses-01_electrodes.tsv
│       │   ├── sub-01_ses-01_task-baseline_eeg.eeg
│       │   ├── sub-01_ses-01_task-baseline_eeg.json
│       │   ├── sub-01_ses-01_task-baseline_eeg.vhdr
│       │   ├── sub-01_ses-01_task-baseline_eeg.vmrk
│       │   ├── sub-01_ses-01_task-walking1_eeg.eeg
│       │   ├── ...
│       │   └── sub-01_ses-01_task-walking2_eeg.vmrk
│       └── func
│           ├── sub-01_ses-01_task-baseline_run-001_bold.json
│           ├── sub-01_ses-01_task-baseline_run-001_bold.nii.gz
│           ├── sub-01_ses-01_task-walking1_run-001_bold.json
│           ├── sub-01_ses-01_task-walking1_run-001_bold.nii.gz
│           ├── sub-01_ses-01_task-walking2_run-001_bold.json
│           └── sub-01_ses-01_task-walking2_run-001_bold.nii.gz

Notes on Organization
---------------------
- Raw data (anat, func, eeg, dwi) are stored under each subject (sub-XX/ses-YY).
- Derivatives (SPM statistical maps, preprocessed outputs) are stored separately under derivatives/sub-XX/ses-YY.
- Naming conventions follow BIDS entities:
  - sub-<label> : subject identifier
  - ses-<label> : session identifier
  - task-<label> : task name (baseline, walking1, walking2)
  - run-<index> : run number
  - <suffix> : modality (T1w, dwi, bold, eeg)

Citation
--------
If you use this dataset, please cite the associated study and acknowledge the contributors.
