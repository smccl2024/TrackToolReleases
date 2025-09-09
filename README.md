# TrackTool Release notes

## v1.6.1 - LTS 

### New features
- New Tracks can be created from TrackFile Page directly without needing to select file
- New Danger Zones can be created from DangerZones Page directly without needing to select file

### Added 
- Added Edit Track button to DangerZone Page
- Added Edit DZones button to DangerZone Page
- Added View Track button to DangerZone Page
- Added View DZones button to DangerZone Page
- Added Clear/Erase button to DangerZone Page

### Technical Improvements

- Optional Original data prop created for DataGraph component
- Create Track Page feature combined with Trackfile and DangerZones page to for better usability 
- General Visualization Enhancement

## v1.6.0 - Stable LTS

### New features

- **CreateTracks Page**:  Paths (DZ) can be created from scratch anywhere on the map.
- **DangerZones Page**:  DangerZones can now be loaded and edited easily on the map.
- Search bar added to Map to navigate to a place using name, post codes, landmarks.

### Technical Improvements

- MapBox Component seperated from map container and div, only used for visualization
- Editing coordinated moved to parent comp of Mapbox to avoid mutating behind parent. 
- Save uses flag to distinguish track from DZ while save

### Enhancements
 
 - Map resizes to full when vertical seperater doublclicked
 - Pop up appears and stays on hover 
 - Speed Graph units changed to mph
 - Track Edit page Icon changed
 - Lane Change flag colour changed for better visibility

 ### Bug Fix

 - Added missing dll for C++ executable 
 - Fixed .csv extension for Filepath during saving in Linux
 - Fixed Speed and LAD data during Saving 
 - Flushed events column during saving to avoid data overflow after resampling.






# v1.5.XX
<details>

<summary><i>Click to see all <i></summary>

## v1.5.2
<details>
<summary>click to see changelog</summary>

### New features
- Visualization Page layout can be resized.
- Added markers for data3 and stop line on the track.
- New event types added for Visualization 

### Bug Fix
- Solved bug which prohibited opening event file with json format. 

### Technical Improvements
- Improved CSS and animation for Visualization
- Changed colour palette to distinguish overlapping event better
- Event index matched with EventJsonCreator
</details>

## v1.5.1
<details>
<summary>click to see changelog</summary>

### Bug Fix
- Solved bug which prohibited opening file which doesn't have danger and event file. Now throws an alert before continuing to open just track file by itselves 

### Technical Improvements
- Seperated Update feature as a component of itselves from Home page
- Improved CSS for Home page for different screen aspect
- Refactored code for macOS build 
</details>

## v1.5.0
<details>
<summary>click to see changelog</summary>

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
</details>
</details>

</br>

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
