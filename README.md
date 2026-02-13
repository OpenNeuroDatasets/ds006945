README

Neuroimaging Data Collected During Kinesthetic Motor Imagery of Walking vs. Rest
-------------------------------------------------------------------------------
This dataset includes multimodal neuroimaging recordings from five participants performing kinesthetic motor imagery (KI) while viewing themselves walking in an exoskeleton. The dataset includes synchronized MRI (structural and functional) and EEG recordings organized according to the BIDS specification. Functional MRI data were acquired in two runs while participants viewed a 10-minute video, along with a separate baseline scan during which participants simulated a resting state for approximately 5 minutes.

MRI sessions were conducted after participants completed nine sessions of EEG‑controlled exoskeleton walking and standing experiments. doi:10.18112/openneuro.ds006940.v1.0.0

MRI Acquisition:
- Scanner: Philips Ingenia 3.0T (Koninklijke Philips N.V., The Netherlands)
- Structural scans: T1‑weighted anatomical images
- Functional scans (fMRI): Participants viewed a 10‑minute video of themselves walking in the exoskeleton, filmed from a first‑person perspective. The video contained 11 Stop‑Walk‑Stop (SWS) cycles. During viewing, participants were instructed to evoke KI in synchrony with the exoskeleton movements.
- Baseline condition: Participants mentally simulated resting state for approximately 5 minutes while fMRI data was recorded.

EEG Acquisition:
- MR‑compatible EEG cap (Brain Products GmbH, Gilching, Germany)
- Electrode locations are provided in EEGLAB format.
- 59 scalp channels + 4 EOG channels + 1 ECG channel

Stimuli:
- A video stimulus (`stimuli/walking_exoskeleton_S1.mp4`) was presented during walking tasks.

Participants:
Five healthy adults out of seven participated in the EEG‑controlled exoskeleton experiments.
Participants S6 and S7 did not undergo MRI scanning due to a pause in data collection during the COVID‑19 pandemic.

<b>Folder Structure (Example: Subject 01)</b><br>
--------------------------------------<br>
├── dataset_description.json<br>
├── README<br>
├── derivatives<br>
&nbsp;└── sub-01<br>
&emsp;&emsp;└── ses-01<br>
&emsp;&emsp;&emsp;├── anat<br>
&emsp;&emsp;&emsp;│&emsp;└── sub-01_ses-01_T1w.nii<br>
&emsp;&emsp;&emsp;├── dwi<br>
&emsp;&emsp;&emsp;│&emsp;├── sub-01_ses-01_run-001_dwi.json<br>
&emsp;&emsp;&emsp;│&emsp;├── sub-01_ses-01_run-001_dwi.bval<br>
&emsp;&emsp;&emsp;│&emsp;├── sub-01_ses-01_run-001_dwi.bvec<br>
&emsp;&emsp;&emsp;│&emsp;└── sub-01_ses-01_run-001_dwi.nii.gz<br>
&emsp;&emsp;&emsp;└── spm<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_beta_0001.nii<br>
&emsp;&emsp;&emsp;&emsp;├── ...<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_beta_0008.nii<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_con_0001.nii<br>
&emsp;&emsp;&emsp;&emsp;├── ...<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_con_0004.nii<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_smpt_0001.nii<br>
&emsp;&emsp;&emsp;&emsp;├── ...<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_smpt_0004.nii<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_mask.mat<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_resms.mat<br>
&emsp;&emsp;&emsp;&emsp;├── sub-01_ses-01_rpv.mat<br>
&emsp;&emsp;&emsp;&emsp;└── sub-01_ses-01_spm.mat<br>
<br>
├── stimuli<br>
&emsp;└── walking_exoskeleton_S1.mp4<br>
<br>
├── sub-01<br>
&emsp;└── ses-01<br>
&emsp;&emsp;├── anat<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_T1w.json<br>
&emsp;&emsp;│&emsp;└── sub-01_ses-01_T1w.nii<br>
&emsp;&emsp;├── eeg<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_coordsystem.json<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_electrodes.json<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_electrodes.tsv<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_task-baseline_eeg.eeg<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_task-baseline_eeg.json<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_task-baseline_eeg.vhdr<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_task-baseline_eeg.vmrk<br>
&emsp;&emsp;│&emsp;├── sub-01_ses-01_task-walking1_eeg.eeg<br>
&emsp;&emsp;│&emsp;├── ...<br>
&emsp;&emsp;│&emsp;└── sub-01_ses-01_task-walking2_eeg.vmrk<br>
&emsp;&emsp;└── func<br>
&emsp;&emsp;&emsp;├── sub-01_ses-01_task-baseline_run-001_bold.json<br>
&emsp;&emsp;&emsp;├── sub-01_ses-01_task-baseline_run-001_bold.nii.gz<br>
&emsp;&emsp;&emsp;├── sub-01_ses-01_task-walking1_run-001_bold.json<br>
&emsp;&emsp;&emsp;├── sub-01_ses-01_task-walking1_run-001_bold.nii.gz<br>
&emsp;&emsp;&emsp;├── sub-01_ses-01_task-walking2_run-001_bold.json<br>
&emsp;&emsp;&emsp;└── sub-01_ses-01_task-walking2_run-001_bold.nii.gz<br>


Validation Data
---------------
A validation file (`derivatives/MRI_DataValidation.xls`) is provided to summarize dataset completeness and quality checks.

- **Sheet: Files**  
  Lists presence/absence of EEG, MRI, and SPM outputs across subjects (S1–S5).  
  Includes counts for beta, con, spmT maps, and DTI volumes.

- **Sheet: VMRK-R128**  
  Reports event marker counts (R128 triggers) for baseline, walking1, and walking2 tasks.

- **Sheet: EEG-Duration**  
  Provides task durations (minutes) for baseline, walking1, and walking2 EEG recordings.

Notes on Organization
---------------------
* Raw data (anat, func, eeg) are stored under each subject directory (sub-XX/ses-YY).

* Derivatives: Preprocessed outputs are stored separately under derivatives/sub-XX/ses-YY, including:
- Statistical Parametric Mapping (SPM) outputs
- SPM-normalized (warped) anatomical scans
- Diffusion Tensor Imaging (DTI) derivatives
- Validation Excel file

* Stimuli are stored in the top-level stimuli/ folder and referenced in the corresponding JSON sidecars.

* Naming conventions follow BIDS entities:
- sub-<label>  : subject identifier
- ses-<label>  : session identifier
- task-<label> : task name (baseline, walking1, walking2)
- run-<index>  : run number

Citation
--------
If you use this dataset, please cite the associated study and acknowledge the contributors.
