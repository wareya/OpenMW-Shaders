# Wareya's OpenMW Post-Processing Shaders

Follower AA: A very accurate AA shader that looks almost as good as MSAA on large objects. Does not blur the screen. Works by following edges and predicting how much aliasing there is. Can read from depth, normal map, or color when walking edges. Has an option to disable itself in places where it thinks MSAA is rendering; you can use it too smooth out jaggies on other post processing effects even with MSAA enabled. That option is subject to this OpenMW bug: https://gitlab.com/OpenMW/openmw/-/issues/7203

water: A post-processing water shader with screen-space reflections. Currently VERY experimental, and requires editing the built-in water shader. Subject to this OpenMW bug: https://gitlab.com/OpenMW/openmw/-/issues/7202

waterblur: A blur-based effect designed to hide specular fireflies on water.

war_adjustments: A contrast, brightness, saturation, color temperature, tint, gamma, etc. adjustments shader.

BadCRT: A really bad scanlines and chroma fringing effect.

zoom, zoom_smooth: Zoom in the center of the screen. Mainly for debugging, but if you're OK with the blurriness, you can use zoom_smooth to hide the screen-edge artifacts of screenspace reflections.

# Using the water shader

To use the water shader, open `water_fragment.glsl` and, below this line:

`gl_FragData[0] = applyFogAtDist(gl_FragData[0], radialDepth, linearDepth);`

Add this new line:

`gl_FragData[0].w = 0.0;`

Then, in the ingame video options for water, set the settings like this:

![image](https://user-images.githubusercontent.com/585488/216796967-c4014c85-9f7d-473e-9bd7-be6c31ac0998.png)

(The ripple density can be set to anything you want, but "Simple" ripples won't render.)

# License

    Copyright 2022-2023 wareya

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
