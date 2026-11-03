# Selectable dashboard layouts

Settings > Appearance > Dashboard layout offers Original Loop (default), Glance, Graph first, and Compact. These native layouts reuse existing views rather than reproducing the earlier design concepts pixel for pixel.

The customization is patches/dashboard-layouts.patch. It changes presentation files and adds focused tests. It does not change therapy settings, dosing logic, device managers, app identity, signing configuration, or stored pump/CGM state. The display preference is com.ryancase.loop.dashboardLayout.v1.

Glance rearranges existing glucose, Loop, and pump status views and enlarges the glucose label. Existing warning and stale-reading handling, tap targets, four charts, status rows, and toolbar controls remain. Graph first and Compact adjust chart heights.

## Verification

Display layout checks builds for an iPhone simulator and checks preference fallback, repeated switching, retained HUD views and stale glucose text, and Glance at 320, 390, and 430 point widths. Its artifact includes a build log and xcresult bundle with HUD screenshots. Device review is still needed for warnings, large text, landscape, chart gestures, and returning from Settings.

## Returning to stock

Select Original Loop in Appearance. For a stock rebuild use the unchanged main branch. Starting stock commit: 5efba88348c868d27951b92f629b74282f5af5ad. Install over the existing app using the same app identity and developer account. Do not delete the app. Old TestFlight binaries expire; retaining source does not guarantee indefinite availability of an old binary.

This branch manual workflow syncs from upstream main. Main branch workflows remain unchanged. Future upstream updates may require rebasing the patch and repeating verification.
