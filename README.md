# REM Microstates Seg

## Description
an example MATLAB function designed to analyze and segment REM sleep into microstages, distinguishing between Phasic and Tonic periods based on EOG (Electrooculography) data.
The signal quality may vary across different recording devices, and the parameters in the function usually need to be adjusted based on the expert's visual segmentation.

## Features
- Segment REM sleep into Phasic and Tonic stages.
- Calculate the duration of each segment.
- Provide visual output of the data segmentation when requested.

## Inputs
- `Data`: A data matrix with aligned EEG, LFP, EOG, Staging... 
- `exam`: Set to 1 to generate plots for examining the segmentation results; 0 otherwise.
- `moved`: Window length in seconds used for moving variance calculation. example 1s
- `nvar`: Multiple of the standard deviation to set the threshold for defining high activity regions. example 0.75 
- `Mini_Epoch`: Duration in seconds for mini-epoch segmentation. example: 2s
- `fs`: Sampling rate of the data. example: 256Hz 
- `percen`: Percentage to define a significant epoch. example: 0.5（50%）
- `numUV`: Threshold in microvolts for detecting significant deviations in EOG data，example: 85

## Outputs
- `Whole`: The complete dataset including mini epoch labels and Phasic/Tonic distribution.
- `epoch_lengths_phasic`: lengths of Phasic segment.
- `epoch_lengths_tonic`: lengths of Tonic segment.
- `total_sleep_duration`: Total duration of sleep detected in the dataset.

![Example Image](/fig.jpg "fig")
