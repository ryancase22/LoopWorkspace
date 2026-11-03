# Readable dashboard cards

Settings > Appearance > Dashboard layout offers Everyday cards (recommended), Glucose focus, Simple cards, Compact cards, Insulin focus, Large numbers and Original Loop. Existing raw preference values remain compatible with earlier custom builds.

Everyday cards balances a large glucose reading and spacious graphs. Glucose focus devotes the most space to glucose history and prediction. Simple cards uses a simpler header and shorter supporting graphs. Compact cards places glucose and device status side by side. Insulin focus places device status first and expands insulin graphs. Large numbers uses the largest glucose font. All custom layouts use separate rounded graph cards and short explanations; all detailed charts and stock navigation controls remain.

The glucose explanation identifies CGM dots, prediction lines and the target band when shown. Other explanations describe estimated insulin still active, insulin delivery over time and estimated carbs still being absorbed. The native chart renderer, units and chart values are retained. 'Predicted' is a label change to the native eventual-glucose subtitle, not a different forecast.

Chart cards have additional height for the explanations. When a container is too short, the unwrapped native chart is retained. Large accessibility text uses stacked headers; the duplicate insulin/carb summary is omitted at accessibility sizes so native detailed rows remain readable. Decorative planetary artwork is subdued and does not encode clinical information.

## Scope and verification

The implementation is patches/dashboard-layouts.patch, plus the app-bundled DashboardHorizon artwork. Treatment settings, dosing logic, device managers, signing and stored device state are outside this change. Generated concept images are illustrative; simulator output and device review establish actual presentation.

Display layout checks prebuilds plugins before the simulator host. Focused tests cover selection fallback, all seven entries, HUD identity and gestures, stale-reading preservation, Original restoration, light/dark window traits, artwork availability, phone widths, accessibility headers, and card text containment/original chart geometry. These are display checks, not end-to-end insulin-delivery tests. Device review is still needed for complete graphs, chart gestures and actual device warnings.

## Reverting

Select Original Loop to restore the standard dashboard. The unchanged main branch remains available for a stock rebuild. Starting stock commit: 5efba88348c868d27951b92f629b74282f5af5ad. Use the same account/app identifier and update over the existing app. Do not delete the app. TestFlight builds expire, so old binaries are not available indefinitely.
