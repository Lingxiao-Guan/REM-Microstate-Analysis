# Function_REM_SubStages_WithEpoch

## Description
`Function_REM_SubStages_WithEpoch` is a MATLAB function designed to analyze and segment REM sleep into microstages, distinguishing between Phasic and Tonic periods based on EOG (Electrooculography) data. The function also labels data with mini epoch labels and calculates the distribution of these sleep stages.

## Features
- Segment REM sleep into Phasic and Tonic stages.
- Calculate the duration of each segment.
- Provide visual output of the data segmentation when requested.

## Inputs
- `Data`: A matrix where rows correspond to channels and columns to data points. The 12th row should contain sleep stage labels.
- `exam`: Set to 1 to generate plots for examining the segmentation results; 0 otherwise.
- `moved`: Window length in seconds used for moving variance calculation.
- `nstd`: Multiple of the standard deviation to set the threshold for defining high activity regions.
- `Mini_Epoch`: Duration in seconds for mini-epoch segmentation.
- `fs`: Sampling rate of the data.
- `percen`: Percentage to define a significant epoch.
- `numUV`: Threshold in microvolts for detecting significant deviations in EOG data.
- `numUV2`: Additional UV threshold for more refined activity detection.

## Outputs
- `Whole`: The complete dataset including mini epoch labels and Phasic/Tonic distribution.
- `epoch_lengths_phasic`: Array containing the lengths of each detected Phasic segment.
- `epoch_lengths_tonic`: Array containing the lengths of each detected Tonic segment.
- `total_sleep_duration`: Total duration of sleep detected in the dataset.

## How to Use
1. Prepare your data matrix according to the expected format.
2. Ensure the 12th row of your data matrix contains the appropriate labels for sleep stages.
3. Call the function with the required parameters. For example:
   ```matlab
   [Whole, epoch_lengths_phasic, epoch_lengths_tonic, total_sleep_duration] = Function_REM_SubStages_WithEpoch(Data, 1, 10, 3, 2, 256, 0.5, 50, 75);
