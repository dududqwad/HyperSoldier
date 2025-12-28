[![HyperSoldier: A Mixed-Reality concept for headset-enhanced combat forces](https://img.youtube.com/vi/ccBjphH0B2k/maxresdefault.jpg)](https://youtu.be/ccBjphH0B2k)

## Introduction

HyperSoldier was born from the thesis that today's off-the-shelf commercial hardware and software can already be used to prototype high impact, multi input, custom hardware dependent, human enhancing services.

This prototype focuses on enhancing a soldier's combat capabilities by delivering real-time, non-invasive technological support through the use of the latest Meta Quest headset, a standard Android smartphone and a WearOS-compatible fitness band, all integrated and provided as a unified experience.
The learnings and technological achievements here included can be transfered to a variety of other contexts, from industrial or high-risk job tasks to multi-sensorial gaming experiences.

When equipped with the required gear, users can track their location, get assisted threat detection, be aware of their surroundings and more. All hardware components can be integrated into standard military gear (helmet, uniform, etc.). All software runs offline, with devices communicating with each other over their own local network.

The presented features are not ready for field deployments due to a variety of constraints (such as insufficient passthrough screen resolution, imprecise location tracking, or experimental threat detection algorithm), but this is outside the scope and purpose of the initiative, as it focuses on the prototyping and validation prior to higher commitment R&D initiatives.

The video recordings used to produce the experience's teaser video and demo content were done in a safe and controlled environment, adopting airsoft gear and simulated combat situations.

## Inspiration

Inspired by Anduril's [EagleEye](https://www.anduril.com/article/anduril-s-eagleeye-puts-mission-command-and-ai-directly-into-the-warfighter-s-helmet/) ([video showcase](https://www.youtube.com/watch?v=x9B02pFKpJo)), Palantir's collaboration with Meta on [IC2](https://www.palantir.com/platforms/gotham/) ([video showcase](https://www.youtube.com/watch?v=UiiqiaUBAL8), [presentation](https://www.palantir.com/assets/xrfr7uokpv1b/1jgsB2RjIL29TYOTF8R1BU/302fdc9ae97ce158853c0c688aa9e2f2/Mixed_Reality_Applications.pdf) and [more](https://www.palantir.com/offerings/mixed-reality/)), and Rivet's [Hard Spec](www.rivet.us/rivet-hard-spec).

Quentin Valembois' recreation of Meta's new AI glasses on Quest (original post [here](https://www.linkedin.com/posts/quentinvalembois_i-recreated-metas-new-ai-glasses-on-my-quest-activity-7381349076271022080-tvFJ)) was what made me believe something similar to his work could be pulled off to prove that today's off-the-shelf commercial hardware and software can already be used to prototype high impact, multi-input human enhancing services.

## How to try it

> [!NOTE]
> If you are a judge of [Meta Horizon Start Developer Competition](https://start-developer-competition.devpost.com/), please follow the steps below to install v1.0.0 of HyperSoldier and HyperCompanion, as that is the one released prior to the competition deadline:
> - Download HyperCompanion APK v1.0.0 from this repo's [release channel](https://github.com/FilipeLopesPires/HyperSoldier/releases/tag/v1.0.0) and install it on an Android device
> - Install HyperSoldier on your Meta Quest 3/3S using this [Alpha channel invite link](https://www.meta.com/s/7wxYQbsf9)

Download latest HyperSoldier APK from the release section (check latest [here](https://github.com/FilipeLopesPires/HyperSoldier/releases/latest)) and install it on your Meta Quest 3/3S using **adb** or, alternatively, install it using this [Beta channel invite link](https://www.meta.com/s/1UYDedR2KT).

After installing the app on your headset, you need to also install the companion app, HyperCompanion, on an Android mobile device. APK available also in release section. 

Once installed, provide location and camera access, enable your GPS and start broadcasting. Make sure both your Android device and your Meta Quest are connected to the same network. HyperSoldier assumes that the Android device will be placed behind your head, pointing back, this ensures proper compass and rear camera view behavior. It is recommended that you first start HyperSoldier on your Quest and only then start HyperCompanion on your mobile device.

When inside HyperSoldier, toggle the rear camera view in the HUD by nodding your head vertically. Similarly, toggle the map as well as threat detection by nodding your head horizontally. 

Note that world maps for tile mapping do not exist for free at a good enough resolution and the resources that are publicly accessible end up taking significant space (in the order of tens of GB and more). So, for this release, only Portugal (my home country) has map coverage - all other locations will show up blank in the HUD's map.

## How I built it

The main application is built with Unity, targeting Meta Quest 3/3S. The companion application is built with Kotlin, targeting Android. The wearable band application is built with Kotlin, targeting WearOS (under development, not included yet).

These apps involve the use of the following technologies: Unity Inference, Meta SDK, Meta Camera Access API, OpenXR, WebSocket, WebRTC, UDP, and more.

## Challenges I ran into

There are multiple challenges when aiming at achieving the full potential of what is here proposed.

The main challenges faced so far were:
- Optimizing speed and accuracy of threat detection in real-time, given that it's fully running locally in headset.
- Achieving adequate visual location display, given that open-source world maps have too low resolution and online services were not an option.
- Designing UI and interactions for a context where controllers are unavailable, hands are busy with other tasks, voice might put the user at risk and eye gazing is not hardware-supported.

## Future Work

Oh there's so much more that can be done for HyperSoldier... Here's just a few from the long list:
- non-simulated health tracking
- ammo tracking (through shot audio detection or other reliable approach)
- silent gesture-to-command translation
- scene understanding for danger evaluation / path risk heatmap
- scene understanding for cover / concealment object identification
- drone control (with aerial view, similar to rear view)
- integrated radio communications
- digital laser designator and danger area pinpoint sharing
- battlefield alerts (checkpoint arrival, enemy down, etc.)
- squad members location tracking
- squad members 6dof (through-wall) tracking

## Credits

Created by Filipe Lopes Pires.

