# Motion-Picture Color Management

This paper presents an introduction to the color pipelines behind modern
feature-film visual-effects and animation:

Authored by Jeremy Selan, and reviewed by the members of the VES
Technology Committee including Rob Bredow, Dan Candela, Nick Cannon,
Paul Debevec, Ray Feeney, Andy Hendrickson, Gautham Krishnamurti, Sam
Richards, Jordan Soles, and Sebastian Sylwan.

The VES Technology Committee has assembled an expert panel that can be
reached at
[ves-tech-color@googlegroups.com](mailto:ves-tech-color@googlegroups.com)
with questions, comments and errata related to this document.

## Topic Listing

- Color Science Basics
- Color Encoding, Color Space, Image States
- Display-Referred Imagery
- Scene-Referred Imagery
- Color Correction, Color Space, "Log"
- Motion-Picture Color Management
- Digital Intermediate, Mastering, Delivery
- Lighting, Rendering, Shading
- Compositing
- Texture and Matte Painting
- Critical Inspection of Imagery
- ACES
- OpenColorIO
- Lookup Tables (LUTs)
- ASC-CDL
- File Formats
- DCI P3 and X'Y'Z'

## External Links

- [OpenColorIO](http://opencolorio.org)
    ([Github](http://github.com/imageworks/OpenColorIO)) - Color
    framework for visual effects and animation
- [Academy Color Encoding System (ACES)](http://www.oscars.org/aces) -
    Future motion-picture colorimetry standard
- [ACES 1.0.1 OpenColorIO
    config](https://github.com/hpd/OpenColorIO-Configs/tree/master/aces_1.0.1) -
    OpenColorIO implementation of the ACES 1.0.1 release
- [Bruce Lindbloom](http://brucelindbloom.com/) - Online resource for
    color conversion math
- [Open-Source VFX](http://opensourcevfx.org/) - A directory of
    Open-Source projects for the VFX community
- [Poynton](http://www.poynton.com/) - Information on video standards
    and gamma
- [Visualizing the XYZ Color
    Space](http://www.youtube.com/watch?v=x0-qoXOCOow) - Visual
    exploration of CIE XYZ
- [DCraw](http://www.cybercom.net/~dcoffin/dcraw/) - Free, high
    quality, camera raw conversion
- [DCI Specification](http://www.dcimovies.com/) - Theatrical digital
    distribution and colorimetry standard
- [Academy Color Encoding System
    (ACES)](http://www.oscars.org/science-technology/council/projects/aces.html) -
    Future motion-picture colorimetry standard
- [Real-Time Rendering](http://www.realtimerendering.com/)
    ([Blog](http://www.realtimerendering.com/blog/)) - A great online CG
    resource, often with a color theme.
- [Sony Pictures Imageworks](http://imageworks.com/)
    ([Open-Source](http://opensource.imageworks.com))
    ([Github](http://github.com/imageworks)) - VFX / Animation Studio

## Siggraph 2012 Course

This document originated as a companion to the [Siggraph 2012
Course](http://s2012.siggraph.org/attendees/sessions/cinematic-color-your-monitor-big-screen),
_Cinematic Color: From Your Monitor to the Big Screen_. Original course
notes available for download: [(pdf, 6.4
MB)](http://github.com/jeremyselan/cinematiccolor/raw/master/siggraph2012/cinematic_color.pdf)
