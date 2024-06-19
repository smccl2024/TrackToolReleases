# TrackToolReleases
Production Releases for Track Tool Application


# Release notes uptill v1.4.4
## Changelog v1.4.4
#### New Feature
- Added a output verification mechanism to ensure that saved coordinates reflect the correct track requirements even if generate is not pressed prior , addressing issues where handleSave would always save Coordinates in current state.

#### Bug Fix
- Fixed various minor bugs related to track data handling and display.

#### Technical Improvements
- Added Compatibility with Linux for distribution

## Changelog v1.4.1
#### New Features
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

