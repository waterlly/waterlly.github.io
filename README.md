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
