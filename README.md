# React Native Dimensions API Inconsistency on High Refresh Rate Devices

This repository demonstrates a bug and its solution related to the `Dimensions` API in React Native. On devices with high refresh rates, the API might return inaccurate dimensions immediately after the app starts. This leads to layout issues and inconsistent behavior.

## Bug Description

The `Dimensions.get('window')` or `Dimensions.get('screen')` methods sometimes return incorrect dimensions right after app launch on high refresh rate devices.  This inconsistency can cause elements to be rendered incorrectly or behave unexpectedly.

## Solution

The solution involves using the `Dimensions.addEventListener` to listen for changes in screen dimensions. This ensures that the dimensions are accurately retrieved once they have stabilized. The solution demonstrates using `useEffect` to register and unregister the listener during the component's lifecycle.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run the app on a device with a high refresh rate (e.g., 120Hz or higher).
4. Observe the initial layout. It might be incorrect.
5. After a brief moment, the layout should correct itself. 

## Files

- `DimensionsBug.js`: Demonstrates the bug.
- `DimensionsBugSolution.js`: Demonstrates the solution.