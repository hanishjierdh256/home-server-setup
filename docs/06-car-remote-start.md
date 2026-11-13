# Car remote start

[← Back to the overview](../README.md)

A retrofit remote starter costs a lot, so I built a start button for the car out of a SwitchBot and a setting change.

## How it works

1. A **SwitchBot Bot** is mounted next to the car's push-to-start button and physically presses it.
2. The Bot runs a two-step **Action Combo** in the SwitchBot app: press, a short pause, press again.
3. A **SwitchBot Hub Mini** connects the Bot to the home network and bridges it into the Apple Home app, where it shows up as a switch.
4. The car's own settings were changed with BimmerLink so the engine can start without the brake pedal pressed.

From the Home app (including when I'm away, via the HomePod hub) it is one tap.

## Keeping the on/off state working

I had trouble with the switch's on and off states. Home treats the Bot as an on/off switch, but all it really does is press a button, so the state shown in Home doesn't follow what the car is doing.

The fix was a shortcut in the iOS Shortcuts app that gets the switch's current state and flips it: if it is on, turn it off; if it is off, turn it on. Each run then sends a fresh press, whatever state Home currently shows.

## Safety

- It is only used with the car in Park.
- Never run the engine in a closed garage. The garage door must be open, because of carbon monoxide.
- Changing car settings can have side effects and may affect your warranty. I'm deliberately not documenting the coding steps. This page describes my setup and isn't a how-to.