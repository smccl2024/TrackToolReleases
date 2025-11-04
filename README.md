# TrackTool Release notes

# v1.7.0


### New Features

- **Track & DangerZone Offset Mode** – Added the ability to offset both track and danger zones with full transition control. Users can visualize offset adjustments interactively on the map.  
- **FlagFile Save As & Relative Path** – Introduced “Save As” functionality for flag files, allowing saving with **relative paths** for better reproducibility when running `EventJsonCreator`.  
- **FlagFile Page Update (Obs v12.9)** – The FlagFile Editor page now supports **Obstacle Software version 12.9**, providing compatibility with the latest json event formats.  
- **DangerZone JSON Popup** – Each DangerZone now includes a **popup display** that reveals JSON details for quick inspection.  
- **TTC Highlighting** – DangerZones with **TTC (Time To Collision)** enabled are now automatically highlighted for better visibility on the map.  

### Technical Improvements

- Re-implemented **offset tracker** for profile calculations with improved accuracy.  
- Added **loop safety** and edge condition checks for offset computations.  
- Refactored **DangerZone ApplyOffset** and offset functions for better usability and maintainability.  
- Added **non-blocking toast notifications** to replace blocking alert messages, improving workflow smoothness.  
- Added **inline cell editing** in the FlagFile table to prevent unnecessary re-renders during edits.  
- Added **log file relocation** to the track directory after batch runs for consistent output management.  

### Bug Fixes

- Fixed boundary detection in **event start/end limit detector** and flag file validity checks.  
- Fixed **flag file start and end bound limits** to prevent incorrect indexing during offset operations.  
- Removed **layer legend duplication** after resampling.  
- Fixed edge case handling when track start or end points matched boundary conditions.  
- Fixed Progress bar Modal vissibility when re-running EventCreator  

</details>

</br>


# v1.6.XX

<details>

<summary><i>Click to see all </i></summary>

## v1.6.2

<details>
<summary>click to see changelog</summary>

### New features

- **FlagFile Page** : This page allows the user to make and or edit flag file and run the EventJsonCreator to create the .danger and .event file. Events and dangerzones can be dynamically loaded and visualized on the map.

### Technical Improvements

- Removed Prop drilling for file selection and csvData.
- Speed Algorithm Changed to match original speed calculation of track tool.
- Refactored resampling/divide function to increase performance.
- Progress value IPC event emitter and listener added.
- Moved Track opening for Visualize within the Component.
- file ref cleared after selection
- Speed, heading and LAD calculation on resample over coordinates to improve performace
- EventJsonCreator.txt copied and moved to trackfile directory after batch file run completes

### Enhancement

- Scaled window with DPI factor
- Speed up Fly to when opening track and dz on map.
- Progress bar animates with actual value when running resampling/Event Creation and EventJsonCreator log on Hide/Show button
- Danger Zones now have a default thickness of 2.18m when shown on the map for realistic view

### Added

- Added Layer Legends with Visibility toggle on Track and DangerZones Page
- Added Original Track and Generated Track layers to Map

</details>

## v1.6.1

<details>
<summary>click to see changelog</summary>

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

</details>

## v1.6.0

<details>
<summary>click to see changelog</summary>

### New features

- **CreateTracks Page**: Paths (DZ) can be created from scratch anywhere on the map.
- **DangerZones Page**: DangerZones can now be loaded and edited easily on the map.
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

</details>
</details>

</br>

# v1.5.XX

<details>

<summary><i>Click to see all </i></summary>

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

- **Visualizer Page**: Tracks along with events and danger data can now be visualized easily on the map, with individual lengend to toggle visibility.
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
- Removed bezier spline source for visualization to reduce computation load

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

<summary><i>Click to see all </i></summary>

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
