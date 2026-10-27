# SKYBOUND — Flight Simulator

Production static website, built on 2026-10-26.

Open https://waterlly.github.io/ to play.

## Publishing

Publish the root of the main branch through GitHub Pages. Keep `.nojekyll` so the `_next` directory is served unchanged. All asset paths are rooted at `/`; this package is intended for a user site or a custom domain root.

## Features

Guest single-player flight, aircraft, cockpits, cabins, liveries, missions, and replay run in the browser. Global imagery, elevation and OpenStreetMap airport facilities use external online services. Accounts, multiplayer and chat require a separate backend and are unavailable on this static-only site.

## Third-party assets

Keep all model, cockpit, cabin, livery, audio and library licenses and attribution files. They retain their respective original licenses.

## Mobile controls

In flight, use the Touch controls / 手游操控 button in the top bar to show or hide the joystick, throttle, rudder and brake controls. Enabled by default on touch devices. The choice is saved locally.

## Engine sound and Icelandair paint

Procedural engine audio follows actual engine power with separate propeller and jet sounds. Use the speaker icon to mute and the flight help panel to adjust volume. Pausing or leaving flight silences audio.

Boeing 757-200 now includes the Icelandair TF-FIZ livery, using original GPL-2.0 FlightGear PNG and XML with pinned provenance in liveries/manifest.json.

## Enhanced lighting mods

High quality uses N8AO 2.0.1 ambient occlusion and Postprocessing 6.39.5 bloom, AgX tone mapping and SMAA. Toggle enhanced lighting with the sparkle button or flight help checkbox. Low quality skips these effects to prioritize frame rate. Credits and original licenses are included in licenses/lighting-plugins.json.

## Sky, weather and reflections

Aircraft and globe share a local-solar clock. Sky reflections, weather haze and noise-shaded cumulus clouds improve high quality, with smaller reflection maps and fewer clouds in smooth mode. The atmosphere setting controls visible sky, clouds and fog. Weather is preset, not live; clouds are billboards and do not provide volumetric cloud occlusion against the separate aircraft canvas. Existing satellite imagery and terrain providers remain responsible for ground detail.

## Flight handling, ground towing and liveries

Banked lift now uses consistent force projections, turns follow actual lateral lift, and airborne controls respond to dynamic pressure. Existing aircraft and flight presets are retained.

Ground services include explicit pushback, stop and tow-to-stand actions. The visible capture range is 8 m for C182 and 12–35 m for jets according to aircraft length. Movement is gradual and follows known terrain; bridge/door interlocks, pause and parking brakes remain active.

A340-300 includes the original Air China B-2385 PNG from FlightGear fgdata with a separate UV adaptation; provenance and GPL attribution are retained in liveries/manifest.json. The 747-8i paint now binds to the actual exterior skin and full vertical tail rather than shared white/cockpit materials.

## Skymark blue Pikachu Jet BC2

The 737-800 now includes Skymark JA73NG blue Pikachu Jet BC2. The original 1024×1024 PNG by ChengyuWordle[Sino Wings Group] is retained byte-for-byte from GeoFS LiverySelector history, with MIT license and source credits. A separate UV2 adaptation fits the existing aircraft body, fin, engine covers and winglets. Native KLM, Ryanair and original paint still restore normally. Select the Skymark blue Pokemon option in the livery menu.

## Pikachu fuselage seam correction

The Skymark adaptation now follows the original model’s separate side, crown and belly UV islands. Nose and upper-fuselage triangles no longer interpolate across unrelated atlas rows; door artwork is aligned to the fuselage. The original PNG and all native geometry/UV/AO data are preserved.

## ArcGIS performance and Hekla Aurora

ArcGIS contact heights now interpolate cached native elevation grids instead of raycasting every terrain triangle for each physics query. At most 64 tiles are retained; provider changes discard the cache. High-quality ArcGIS rendering can adapt resolution under sustained GPU load while preserving lighting, shadows and texture detail. Boeing 757-200 gains the original 4096×4096 Icelandair Hekla Aurora TF-FIU PNG by Pilot2938 (GPL-2.0) with native UVs. The prior Skymark fuselage seam correction is included.

## Default AI performance and aircraft-specific stall audio

Airport and global AI retain their full simulation and model templates. Offscreen instances skip animation/GPU submission, offscreen terrain raycasts are omitted, and AI-only terrain visibility is reused for 120–200ms with bounded storage and immediate provider/camera-jump invalidation. Player collision and visibility queries stay exact. Disabling airport AI now also stops hidden-aircraft terrain scans. High quality adapts toward 52 FPS with a 0.5 resolution floor. If even that remains below45FPS for another complete window, automatic performance rendering reduces expensive lighting until the user switches quality again. Airbus stall audio uses an attributed arrangement of original A320-family cricket and STALL STALL voice samples; Boeing profiles share the original 737 simulator stick-shaker sample. Stall audio loops until clear/pause/mute; transport stall audio never uses browser speech synthesis. Original source WAVs and GPL licenses are included in audio/warnings/manifest.json.

## Compact flight planner and airborne landing-gear bogies

The planner uses a family-grouped native aircraft dropdown, a prominent launch action above the map, compact desktop settings and mobile setting sections. Runway and starting-state explanations expand on request. Multi-axle landing-gear trucks droop when airborne and independently level under load. Native tyres, beams and lower pistons retain their rigid geometry. Compact replay v2 retains truck pitch and accepts legacy v1 files. Terrain visibility queries now reject loaded terrain beyond the target finite segment. The previously drafted A321neo-based XLR adaptation is excluded from the active aircraft and paint catalog; no substitute is presented as an authentic XLR.

## Community A321XLR and two requested liveries

The user-selected community Iberia A321-253NY XLR exterior adds a 21st selectable aircraft. Original source triangles, UV coordinates and embedded image payloads are preserved with a uniform coordinate frame and semantic motion groups. The model retains shared A321 exterior details; animations and physical loads use simplified game calibration. Includes Aer Lingus traditional green and China Airlines Pokemon paint choices, original Iberia restoration, six-wheel contact, gear, flaps/slats, spoilers, fans, reverse sleeves, curved passenger door, boarding/bridge and tug integration, shared A321 interiors, touch input and replay. Creator/template attribution and upstream 3D Warehouse General Model License references are in models/licenses/A321XLR-3DWAREHOUSE-*. This exterior is a component of the complete simulator Combined Work, not a separately offered model download.

## Frame performance and recoverable bounced landings

Adds camera-height reuse of the existing ArcGIS native grid cache, with guarded fallback to Cesium picking. Expensive HUD snapshots are sampled at the existing 100 ms UI cadence; simulation, cameras, warning logic and displayed FPS retain their original clocks. Static aircraft source-local matrices are baked while dynamic controls and world propagation remain active. Aircraft framebuffers use bounded, refresh-aware resolution feedback, targeting the observed compositor cadence up to 100 fps. The globe retains its calibrated per-quality resolution and terrain LOD budget. Recoverable gear-down upright bounced landings and fairing scrapes no longer immediately explode; water, buildings and catastrophic impacts retain damage. This is forgiving gameplay calibration, not a structural certification model. Actual frame rate remains dependent on device, refresh rate, scenery and traffic load. High forward speed alone no longer destroys a gentle touchdown. Small coherent DEM refinements at the existing wheel locations rebase the aircraft/support datum without injecting a ground-impact velocity. Zero-instance AI batches skip GPU submission while all logical traffic remains active.
