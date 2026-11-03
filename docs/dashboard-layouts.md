# One-screen dashboard cards

The six custom layouts are Everyday cards, Glucose focus, Simple cards, Compact cards, Insulin focus and Large numbers. Original Loop remains available. Each custom layout uses a compact glucose/device header and four graph cards without explanatory paragraphs or duplicate summary rows.

Custom row heights share one finite viewport budget, accounting for safe-area insets, the bottom toolbar, visible status/warning rows and padding. No per-card minimum is allowed to inflate the total beyond the available height. Six profiles vary the proportions; Original keeps its native height policy. At large accessibility text sizes, the HUD can stack for readability, while charts continue to use the remaining budget. All native warning rows and controls remain.

The values, units, native chart renderer, chart gestures and treatment code are unchanged. This is presentation code plus decorative app artwork. Focused tests check finite budget sums, phone viewport sizes including 430 by 932 sizing assumptions, compact standard-text HUD heights, stale-reading preservation, selection fallback, dark/light rendering, Original restoration and retention of the native chart without explanation labels.

Tests do not replace a full-device review of all graphs and active warnings. Select Original Loop to restore stock presentation. For a stock rebuild, use the unchanged main branch and the same account/app identifier. Update over the app; do not delete it. TestFlight builds expire.
