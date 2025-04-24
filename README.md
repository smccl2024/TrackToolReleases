# TrackEdit Production Release

# v1.5.0

### New features

- **Visualizer Page**:  Tracks along with events and danger data can now be visualized easily on the map, with individual lengend to toggle visibility.
- **Auto Update**: Updates are now rolled over the air which allows downloading and installation of new app versions if available

### Added 

- Added Event and Danger component with unified GeoJSON source for efficient rendering
- Added Legend component that can be reused 
- Added map fly and slow zoom when Visualizer loads
- Danger zones highlights with pop up showing zone id when clicked 
- Event are classified by different colour and width to show overlap if any
- File parser added to allow auto selection of .danger and .event file when corresponding track file is loaded into Visualizer

### Enhancement 

- Min-Max slider value changed for resampling and speed curve smoothing
- README.md changed to show app versions on top level
- Removed bezier spline source for visualization to  reduce computation load

### Technical Improvements
- App zoom scale fixed to 100% and is independant from default settings
- App id changed 
- Cleanup on Component unmount
- File chooser component takes icon and proceedto as additional inputs increasing reusability

---



# v1.4.XX

<details>

<summary><i>Click to see all <i></summary>

## v1.4.7

<details>
<summary>click to see changelog</summary>

### Technical Improvements

- Refactored Code for track parameter inputs, new UserInput Component added for resuability and abstraction
- Set app user model id for Windows (process related improvement)
- Dev options removed after app packaged

### Bug Fix
- Solved csv recreation issue after hitting save. Uses state variable to set lad, speed and flag 1 column

</details>

## v1.4.6

<details>
<summary>click to see changelog</summary>

#### Bug Fix

- Resolved an issue with the win-x64 application where myapp.exe was not properly linked to the standard C++ Runtime Library. Added the necessary DLL dependencies to ensure correct functionality.

#### Technical Improvements

- Improved input handling by specifying input types as numbers, preventing the occurrence of NaN (Not a Number) errors.

</details>

## v1.4.5

<details>
<summary>click to see changelog</summary>

#### New Feature

- A progress bar feature has been integrated into the application. This enhancement improves user experience by providing real-time feedback on the status of resampling.

#### Bug Fix

- An issue affecting the application's compliance with Linux systems has been resolved.

</details>

## v1.4.4

<details>
<summary>click to see changelog</summary>

#### New Feature

- Added a output verification mechanism to ensure that saved coordinates reflect the correct track requirements even if generate is not pressed prior , addressing issues where handleSave would always save Coordinates in current state.

#### Bug Fix

- Fixed various minor bugs related to track data handling and display.

#### Technical Improvements

- Added Compatibility with Linux for distribution

</details>

## v1.4.3

<details>
<summary>click to see changelog</summary>

#### Bug Fix

- Fixed issue caused by Coordinates precision being more than 8 decimals

</details>

## v1.4.1

<details>
<summary>click to see changelog</summary>

### Bug Fixes

- Fixed various minor bugs related to track data handling and display.

</details>

## v1.4.0

<details>
<summary>click to see changelog</summary>

### New Features

- **Display Track on Map**: Tracks are now displayed on the map with markers at each recorded point.
- **Join Points with Straight Line**: Connected all track points with straight lines for better visualization.
- **Interpolated Smooth Curve**: Added functionality to interpolate and create a smooth curve between track points for a more accurate representation.
- **Resample Points**: Introduced a resampling feature to ensure track points are evenly spaced for better analysis and processing.
- **Calculate Speed**: Implemented speed calculation based on track point data to provide insights on movement dynamics.
- **Calculate Look Ahead**: Added look-ahead calculation to predict future positions based on current trajectory and speed.
- **Save Track with Correct Checksum**: Tracks are now saved with a correct checksum to ensure data integrity and prevent corruption.

### Enhancements

- Improved the accuracy and performance of the track rendering on the map.
- Enhanced the user interface for better usability and visualization of track data.

### Bug Fixes

- Fixed various minor bugs related to track data handling and display.

### Technical Improvements

- Refactored codebase to improve maintainability and performance.
- Optimized algorithms for better efficiency in handling and processing track data.

</details>

</details>
