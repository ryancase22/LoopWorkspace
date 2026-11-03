# Selectable dashboard layouts

Settings > Appearance > Dashboard layout offers Original Loop (default), Orbit, Mission Control, and Eclipse. These native layouts reuse existing views rather than reproducing the earlier design concepts pixel for pixel.

The customization is patches/dashboard-layouts.patch. It changes presentation files and adds focused tests. It does not change therapy settings, dosing logic, device managers, app identity, signing configuration, or stored pump/CGM state. The display preference is com.ryancase.loop.dashboardLayout.v1.

Orbit uses a prominent glucose header and blue rounded chart cards. Mission Control keeps a compact HUD and gives glucose history/prediction the largest chart, with teal outlined cards. Eclipse uses compact charts and neutral graphite cards. All follow system light/dark appearance. Original removes the card styling and restores native HUD constraints. Existing warning and stale-reading handling, tap targets, four charts, status rows, and toolbar controls remain. Decorative accents do not replace clinical status colors. Raw preference values remain unchanged so existing selections migrate without touching therapy settings.

## Verification

Display layout checks builds for an iPhone simulator and checks preference fallback, repeated switching, retained HUD views and stale glucose text, and all presentations at 320, 390, and 430 point widths, light/dark appearance and accessibility text traits. Its artifact includes a build log and xcresult bundle with HUD screenshots. Device review is still needed for actual device warnings, landscape, chart gestures, and returning from Settings. The tests do not establish end-to-end insulin-delivery safety.

## Returning to stock

Select Original Loop in Appearance. For a stock rebuild use the unchanged main branch. Starting stock commit: 5efba88348c868d27951b92f629b74282f5af5ad. Install over the existing app using the same app identity and developer account. Do not delete the app. Old TestFlight binaries expire; retaining source does not guarantee indefinite availability of an old binary.

This branch manual workflow syncs from upstream main. Main branch workflows remain unchanged. Future upstream updates may require rebasing the patch and repeating verification.
