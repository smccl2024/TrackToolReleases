# TrackTool Release notes

# v1.9.1

<!-- <details>
<summary>click to see changelog</summary> -->


### Technical Improvements

- **MD5 Full Validation** – Improved TrackFile integrity checks by validating the full MD5 checksum against the associated TrackFile.

- **macOS & POSIX Compatibility** – Improved cross-platform compatibility by adding POSIX-compliant file and process handling for macOS and other POSIX-based systems.

### Bug Fixes

- Fixed potential loss of existing JSON data when overwriting combined JSON files.
- Improved cross-platform compatibility for POSIX-based environments.

<!-- </details> -->

</br>

# v1.9.0

<!-- <details>
<summary>click to see changelog</summary> -->

### New Features

- **FlagFile & SpeedFile Table Redesign** – Redesigned the FlagFile and SpeedFile editing tables to support the new JSON format. The updated layout provides a more concise and intuitive interface, improving readability and usability when editing event and speed parameters.

- **Dynamic Event Parameter Editor** – Replaced the JSON column in the FlagFile table with a dedicated **Parameter** column. Parameters are now dynamically generated using `eventDefinition.json`, providing event-specific dropdown menus, editable values, and options to add or remove parameters without manually editing JSON structures.

- **Vehicle Safety Margin Visualization** – Visualization for the `reduceObstacleMargin` event, displaying the actual shuttle geometry and its surrounding safety margins. Colour-coded margin changes provide a visual representation of how the configured safety margins would appear in real-world scenarios.

- **DangerZone Multi-Selection And Zones Table** – Select and Manage multiple DangerZones together, including loading zones directly from a FlagFile and managing them through a dedicated Zones table Section.

- **MD5-based JSON Flag Transfer** – MD5 checksum mismatch detection when opening JSON FlagFiles, with options to transfer flags or continue opening the file. Flag transfer can automatically retrieve curated flag data.

### Added

- **JSON Metadata Validation** – Added metadata checks during JSON file loading to ensure compatibility and data integrity.
- **DangerZone Editing Improvements** – Added right-click functionality to enter DangerZone editing mode, with dedicated Done and Exit buttons for improved editing control.
- **Clear all** - Unified Clead All button functionality to clear all entries from the table

### Enhancements

- Improved DangerZone editing workflow with automatic exit from editing mode when creating a new DangerZone with unsaved changes.
- Improved FileChooser dialogs with descriptive titles.
- Improved File load button naming accross all pages to maintain symmetry and simplicity of intended behaviour.

### Technical Improvements

- Refactored File handling to support the new JSON document structure and metadata with backwards compatability.
- Updated SpeedFile loading to retrieve base document information and metadata from `TrackEditJsonCreator`.
- General code cleanup and refactoring across TrackFile, SpeedFile, FlagFile and DangerZone components.
- Unified Kinematics JSON inputs between Save and Apply operations, eliminating the need to generate an intermediate `track.json` file.

### Bug Fixes

- Fixed latitude and longitude recovery during JSON creation.
- General Bug Fixes

<!-- </details> -->

</br>

# v1.8.XX

<details>
<summary><i>Click to see all </i></summary>

## v1.8.1

<details>
<summary>click to see changelog</summary>

### Bug Fixes

- Fixed Overtake Line display direction opposite to input
- Cleared div ref when clicked outside the solve for accidental input

</details>

## v1.8.0

<details>
<summary>click to see changelog</summary>

### New Features

- **Undo & Redo** – Added undo and redo functionality for Track coordinate editing, including editing context such as local sampling ranges and offset points.

- **Local Resampling** – Added the ability to select and resample a local section of a Track without affecting the entire Track. Local range boundaries are preserved during editing and Waypoint deletion.

- **Interactive Speed Profile** – Added draggable speed graph functionality, allowing the speed profile to be modified interactively. Includes FlatRange support for Min/Max values and a toggle to enable or disable graph interaction.

- **Speed Heatmap** – Added a speed heatmap layer to visualize speed variation along the Track.

- **DangerZone Extend Start/End** – Added functionality to extend the start and end of DangerZones.

### Added

- **Enhanced Track Statistics** – Improved Visualize page statistics with user-defined dwell times, event counts and additional Track metrics.

- Added configuration inputs for `spread_heading_calculation` and `spread_speed_floor` to the Kinematics JSON generation workflow.

### Enhancements

- Improved rendering performance to provide smoother visual feedback while editing Track coordinates.

- Updated Map visualization opacity and layer ordering for improved visibility.

- Speed and Flag file table input element covers entire width, so clicking anywhere should allow editing.

- Flag file waypooint fields can now be populated by focusing the desired field and clicking a waypoint marker on the map.

### Technical Improvements

- Added a dedicated `History.ts` module for managing coordinate and editing-context history.

- Removed Bezier interpolation from local Track sampling.

- EventJsonCreator updated with faster processing built

### Bug Fixes

- Fixed **Mapbox layer initialization** when map layers are created for the first time.

- Fixed **Overtake Event** visualization.

</details>
</details>

</br>

# v1.7.XX

<details>
<summary><i>Click to see all </i></summary>

## v1.7.7

<details>
<summary>click to see changelog</summary>

### Bug Fixes

- **Profile Curving**: Northing Easting Projection mismatch rectified with WGS84 projection for closesness with Old tool
- General UI bug fixe

### Technical Improvements

- Step changed for User Input
</details>

## v1.7.6

<details>
<summary>click to see changelog</summary>

### Added

- **SplineResolution**: User Input Block added to TrackFile page to change Bezeir spline resolution and generate smooth track

### Bug Fixes

- Spline resolution increased for resampling snaping error
- Run EventJsonCreator progress check removed, Modal closes on process completion

### Enhancements

- DataGraph Zoom modes allows Ctrl + drag for non sqaure zoom type
- Sampling button named changed for better understanding

### Technical Improvements

- npm package list updated
- Update KinematicsJsonCreator
</details>

## v1.7.5

<details>
<summary>click to see changelog</summary>

### Added

- **Acceleration LookAhead**: User Input Block added to TrackFile and SpeedFile page and KinematicsJsonCreator Updated to ingest this input on change

### Technical Improvements

- Flag File warning display time lowered by 2s
- Electron package including V8 engine, node and npm packages upated to LTS stable for security and known vulnerabilitis
- File Chooser button refactored, with IPC based file loader over renderer touching the user system for security
- Improved the divide function for both Track and DangerZone, to be much faster

### Bug Fixes

- Flag Transfer artificate replaced for json parsing bug
- Heading Calculation shifted to original waypoint sample based
- Fix React JS Focus back on editable cell when background runs
- Lat Lng swap when reversing the event file

### Enhancements

- Offset point gets cleared when a third point is selected or when track is resampled or processed
- Current File path updates in the display when saved
</details>

## v1.7.4

<details>
<summary>click to see changelog</summary>

### New Features

- **SpeedFile Page** – Added a dedicated page for loading, editing and managing speed limit files.
- **Kinematics JSON Creator** – Added support for generating kinematics JSON along with integrated speed calculation.
- **Track Straightening & Curving** – Introduced algorithms for creating straight and curved track sections with improved geometry generation.
- **Configuration Parameter Loading** – Parameters can now be loaded directly from configuration files.

### Added

- **Management Only Flag** – Added support for management-only flags in the event list.
- **Track Location Information** – Visualize page now displays additional track statistics and location information.

### Technical Improvements

- Refactored IPC communication by changing the `AskFlagTransfer` IPC call from `invoke` to `send/on`.
- Removed speed limit functionality from the TrackFile page following the introduction of the dedicated SpeedFile page.
- Replaced buffer generation with **JSTS** to produce flat end caps for more accurate DangerZone geometry.
- Overtake event offset visualization now matches the configured **MaxAllowed** distance.
- Improved handling of reversed offset selections by automatically swapping offset points internally.
- General code cleanup and refactoring.

### Bug Fixes

- Fixed overlapping extended straight segments during track generation.
- Added correct tail-end generation after circular sections.
- Fixed Event layer loading when opening a new track.
- Updated **EventJsonCreator** with stability and validation fixes.
- Fixed various issues related to EventJsonCreator distance calculations and general application stability.

</details>

## v1.7.3

<details>
<summary>click to see changelog</summary>

### New Features

- **DangerZones Translation and Rotation** - Zones can be translated along rhumb line to north, south, east and west with respect to geopgraphical north, Zones can also be rotated along its centroid

### Added

- **Track Stats** - Visualize page display track length, avg. speed and time of travel

### Techincal Improvements

- Updated **flag_transfer** binary with JSON parsing for speed file
- Updated **EventJsonCreator** binary with validation for action point location
- DangerZone location validation while flagfile editing

### Bug Fixes

- Action point location validation bounds to start and end of an event
- Relative flag for Busstop event now accepeted
- Flag File progress bar bug in opening modal
- DangerZones prediction and actual offset matching
- Waypoint Creation/Editing hidden if file not loaded
- Progress bar display on re running EventJsonCreator over same flag file

</details>

## v1.7.2

<details>
<summary>click to see changelog</summary>

### New Features

- **Flag Transfer on Save** – Flags, speed limits, and related data can now be transferred directly from the TrackFile page when editing is completed and saved.
- **Predicted Offset Preview** – Introduced a predicted offset layer to visually preview offset changes before applying them permanently to track coordinates.
- **Speed Limit Computation** – Recalculate global speed profile based on min and max speed limits.
- **Local Speed Limits** – Speed can be recomputed over local region using JSON params (a_lat_max, a_long_max and a_dec_max) for fine grained control.

### Added

- **Regenerate Flag Data** – Added the ability to recreate flag file data using existing track, `.event`, and `.danger` files.
- **Event Row Visibility Toggle** – Added show/hide functionality for individual event rows in the FlagFile editor with a sticky header for better navigation.
- **Speed Limit Editing Table** – Editable speed limit table with Saving support directly from the UI.
- **TrackFile Location Display** – TrackFile location is now shown at the top of the map, with current paths for DangerZones and Flag files displayed in the right panel.

### Technical Improvements

- Minor **speed profile corrections** near the end of the curve.
- Refactored **heading calculation** and applied smoothing to Look Ahead Distance (LAD) to reduce noise from bearing values.
- Separated Offset transition **easing logic from Vmax calculations** to improve maintainability and correctness.
- Refactored for local speed calculation logic and resolved rounding errors in bearing return.
- Restored **original track parameter inputs** for improved editing flexibility.
- Corrected **danger file extension handling**.
- General code refactoring and clean-up across offset and speed-related logic.
- Downgrade update feature (dev mode only) for alpha and beta channels testing

### Enhancements

- UI improvements with refined layout structure.
- Applied **resizable layouts across all pages** using flex-based and relative positioning.
- Allowed controlled overflow for right-hand side panels.
- Added **Globe Spinner** component for improved loading feedback.

</details>

## v1.7.1

<details>
<summary>click to see changelog</summary>

### Bug Fixes

- Fixed CSV headers cheker when laoding track
- Fixed FlagFile DZ selector

</details>

## v1.7.0

<details>
<summary>click to see changelog</summary>

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
