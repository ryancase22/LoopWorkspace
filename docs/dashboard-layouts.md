# Clean one-screen dashboard cards

The six custom layouts are Everyday cards, Glucose focus, Simple cards, Compact cards, Insulin focus and Large numbers. Original Loop remains available. Each custom layout uses a compact glucose/device header and four graph cards without explanatory paragraphs or duplicate summary rows. The November refresh removes space artwork, adds subdued card borders, increases the normal-width glucose value to 34 points, and gives chart values and axes stronger contrast. Everyday cards uses teal accents matching the loop/drop icon. Native glucose, insulin and carbohydrate colors remain unchanged; gridlines are subdued without changing chart scales, target ranges or predictions.

Custom row heights share one finite viewport budget, accounting for safe-area insets, the bottom toolbar, visible status/warning rows and padding. No per-card minimum is allowed to inflate the total beyond the available height. Six profiles vary the proportions; Original keeps its native height policy. At large accessibility text sizes, the HUD can stack for readability, while charts continue to use the remaining budget. All native warning rows and controls remain.

The values, units, native chart renderer, chart gestures and treatment code are unchanged. This is presentation code plus decorative app artwork. Focused tests check restoration of the stock chart palette and retention of semantic chart colors, finite budget sums, phone viewport sizes including 430 by 932 sizing assumptions, compact standard-text HUD heights, stale-reading preservation, selection fallback, dark/light rendering, Original restoration and retention of the native chart without explanation labels.

Tests do not replace a full-device review of all graphs and active warnings. Select Original Loop to restore stock presentation. For a stock rebuild, use the unchanged main branch and the same account/app identifier. Update over the app; do not delete it. TestFlight builds expire.

## Card arrangement, pod expiry and compact Live Activity

Settings > Appearance > Dashboard cards lets the user reorder all four cards, hide the three secondary graphs, reset the arrangement, and toggle the pod countdown. Glucose cannot be hidden. Original Loop ignores these display preferences and keeps its stock order and visibility. Visible cards share the existing finite viewport budget, normalized to the selected cards while retaining their original chart and tap destinations.

The pod expiry line reads only the current active Omni pod's stored expiresAt date. It is hidden for missing data, other pumps, setup in progress, a fault or stopped delivery. A past nominal expiry is labeled as passed and does not claim that delivery stopped. The native pump indicators, insulin reservoir display and alerts are retained. It does not add notifications or alter pod expiration or insulin delivery.

The small Live Activity, shared by CarPlay and the Apple Watch Smart Stack, displays a larger glucose/trend, reading time and IOB. It suppresses readings older than ten minutes, ended activities, system-stale content and implausibly future timestamps. IOB is an optional backward-compatible payload field sourced from the existing dose store; there are no remote treatment controls. iOS controls refresh and CarPlay placement. Live Activities must be enabled by the user on the phone. CarPlay has not been verified in a physical car.

Additional tests cover corrupted card preferences, all visible-card budget combinations, native row meaning after reordering, Original order restoration, pod-state gating/countdown boundaries, header height with and without expiry, and decoding older Live Activity payloads.
