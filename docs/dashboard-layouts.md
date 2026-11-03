# Selectable dashboards

Settings > Appearance > Dashboard layout offers Horizon, Atlas, Eclipse, Aurora, Observatory and Zenith, plus Original Loop. Raw preference values remain compatible with the earlier custom builds.

The native implementation is patches/dashboard-layouts.patch. It reuses the existing glucose, Loop and pump HUD views, native chart renderer and data descriptions. Treatment settings, dosing logic, device managers, signing and stored device state are outside this patch.

Horizon uses a large glucose header, open glucose chart and a compact insulin/carbohydrate summary. Atlas puts more space into glucose history and prediction. Eclipse uses a large header and shorter supporting charts. Aurora splits glucose and device status. Observatory places device status first and emphasizes delivery charts. Zenith has the largest glucose font and chart. All preserve the detailed charts, native status colors and existing toolbar controls.

The app-bundled DashboardHorizon asset is decorative. Dark appearance uses the planetary artwork; light appearance uses a subtle native background. The summary strip repeats the same text as the active insulin and carb chart rows, with a dash for unavailable data. It appears only when the chart container has sufficient height. It does not estimate pod remaining time or create a new clinical data path.

Generated mockups are concepts, not screenshots or proof of pixel-perfect implementation. The native code retains stock navigation controls and device HUD behavior. Simulator artifacts show the implemented HUD at phone widths; a device review is needed for the full dashboard, landscape, chart gestures and real device alerts.

## Validation

The Display layout checks workflow builds plugins and shared frameworks before the simulator host, avoiding the stock plugin-copy race. Focused tests cover preference fallback, all seven selector entries, repeated switching, stale-reading preservation, retained HUD references and gestures, Original restoration, and fitting at 320, 390 and 430 points. These are presentation tests, not end-to-end insulin-delivery validation.

## Reverting

Select Original Loop to restore the native dashboard presentation. The unchanged main branch remains available for a stock rebuild. Starting stock commit: 5efba88348c868d27951b92f629b74282f5af5ad. Use the same developer account and app identifier and update over the existing app. Do not delete the app. TestFlight binaries expire; preserving source does not make an old binary available indefinitely.
