# Wareya's OpenMW Post-Processing Shaders

Follower AA: A very accurate AA shader that looks almost as good as MSAA on large objects. Does not blur the screen. Works by following edges and predicting how much aliasing there is. Can read from depth, normal map, or color when walking edges. Has an option to disable itself in places where it thinks MSAA is rendering; you can use it too smooth out jaggies on other post processing effects even with MSAA enabled. That option is subject to this OpenMW bug: https://gitlab.com/OpenMW/openmw/-/issues/7203

water: A post-processing water shader with screen-space reflections. Subject to this OpenMW bug: https://gitlab.com/OpenMW/openmw/-/issues/7202

waterblur: A blur-based effect designed to hide specular fireflies on water.

war_adjustments: A contrast, brightness, saturation, color temperature, tint, gamma, etc. adjustments shader.

BadCRT: A really bad scanlines and chroma fringing effect.

zoom, zoom_smooth: Zoom in the center of the screen. Mainly for debugging, but if you're OK with the blurriness, you can use zoom_smooth to hide the screen-edge artifacts of screenspace reflections.

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
