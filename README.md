# REM Microstates Seg

## Description
an example MATLAB function designed to analyze and segment REM sleep into microstages, distinguishing between Phasic and Tonic periods based on EOG (Electrooculography) data.
The signal quality may vary across different recording devices, and the parameters in the function usually need to be adjusted based on the expert's visual segmentation.

## Features
- Segment REM sleep into Phasic and Tonic stages.
- Calculate the duration of each segment.
- Provide visual output of the data segmentation when requested.

## Inputs
- `signalData`: A data matrix with aligned EEG, LFP, EOG, Staging... 
- `plotFlag`: Set to 1 to generate plots for examining the segmentation results; 0 otherwise.
- `movwind`: Window length in seconds used for moving variance calculation. example 1s
- `thresholdFactor`: Multiple of the standard deviation to set the threshold for defining high activity regions. example 0.75 
- `epochDuration`: Duration in seconds for mini-epoch segmentation. example: 2s
- `samplingRate`: Sampling rate of the data. example: 256Hz 
- `significantPercentage`: Percentage to define a significant epoch. example: 0.5（50%）
- `uvThreshold`: Threshold in microvolts for detecting significant deviations in EOG data，example: 85

## Outputs
- `completeDataset`: The complete dataset including mini epoch labels and Phasic/Tonic distribution.
- `phasicSegmentLengths`: lengths of Phasic segment.
- `tonicSegmentLengths`: lengths of Tonic segment.
- `totalSleepTime`: Total duration of sleep detected in the dataset.

![Example Image](/fig.jpg "fig")
