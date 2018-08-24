# Exploring Colorspaces

<style>
    .container {
        display: flex;
        justify-content: center;
        align-content: flex-start;
    }

    .item {
        flex: 0 1 auto;
        width: 100%;
    }

    .colourAnalysisView{
        padding-bottom: 56.25%;
        height: 0;
    }
</style>

## Introduction

This page is an interactive companion for the [Cinematic Color 2 publication]($UNDEFINED_LINK).
It illustrates various concept and workflow points from the document.

## CIE 1931 2° Standard Observer - Color Matching Functions

The *CIE 1931 2° Standard Observer* is a linear transformation of
*Wright & Guild 1931 2° RGB Color Matching Functions* (CMFs) designed by the
*CIE* to remove the negative lobe of the later.

The three functions can be assembled in space into a single continuous line
called the *Spectral Locus*.

<div class="container">
    <div id="gamutView1" class="colourAnalysisView item"></div>
</div>

_The Spectral Locus plotted in the CIE XYZ Colorspace._

## CIE XYZ Colorspace

The *Visible Gamut* represents all the colors a *Standard Observer* can see.
Colors are often represented as *xy* *Chromaticity Coordinates* on a
two-dimensional *Chromaticity Diagram* but they are actual three-dimensional
data.

<div class="container">
    <div id="gamutView2" class="colourAnalysisView item"></div>
</div>

_The Visible Gamut plotted in the CIE XYZ Colorspace._

It is surprising to observe that the *Visible Gamut* does not actually reach
the *Spectral Locus* but it is a direct consequence of the integration
of light with the *CIE 1931 2° Standard Observer*.

The *Visible Gamut* is constructed by converting a set of spectral pulses
to tristimulus values. Those spectral pulses are slices of
*CIE Standard Illuminant E*, generating all possible slices yields the outer
surface.

Assuming 5 bins, a first set of spectral pulses would be as follows:

```
1 0 0 0 0
0 1 0 0 0
0 0 1 0 0
0 0 0 1 0
0 0 0 0 1
```

The second one:

```
1 1 0 0 0
0 1 1 0 0
0 0 1 1 0
0 0 0 1 1
1 0 0 0 1
```

The third one:

```
1 1 1 0 0
0 1 1 1 0
0 0 1 1 1
1 0 0 1 1
1 1 0 0 1
```

And so forth until all the bins are equal to 1.

## CIE xyY Colorspace

The *CIE xyY colorspace* is the result of a projective transformation of the
*CIE XYZ colorspace* in order to separate *Luminance* from *Chroma*.

<div class="container">
    <div id="gamutView3" class="colourAnalysisView item"></div>
</div>

_The Spectral Locus and Visible Gamut plotted in the CIE xyY colorspace, note
how from the initial view angle the remarkable horseshoe shape starts to show._

<script src="https://cdn.rawgit.com/mrdoob/three.js/master/build/three.min.js"></script>
<script src="https://cdn.rawgit.com/mrdoob/three.js/master/examples/js/controls/OrbitControls.js"></script>
<script src="https://cdn.rawgit.com/mrdoob/three.js/master/examples/js/controls/TrackballControls.js"></script>
<script src="https://rawgit.com/colour-science/colour-analysis-three.js/master/dist/colour-analysis.js"></script>
<script type="text/javascript">
    window.colourAnalysisServer = 'https://www.colour-science.org:8020';

    var gamutViewSettings = {
            scene: {
                background: '#F5F5F5'
            },
            fog: {
                color: '#F5F5F5',
            },
            grid: {
                colorCenterLine: '#B5B5B5',
                colorGrid: '#D5D5D5'
            },
            camera: {
                position: { x: -1, y: 1, z: 1 },
            },
    }

    var primaryColourspace = 'sRGB';

    // CIE 1931 2° Standard Observer - Color Matching Functions
    var colourspaceModel = 'CIE XYZ';
    var gamutView1 = new ColourAnalysis.GamutView(
        document.getElementById('gamutView1'),
        {
            ...{
                primaryColourspace: primaryColourspace,
                colourspaceModel: colourspaceModel,
            },
            ...gamutViewSettings
        }
    );
    gamutView1.addViewAxesVisual();
    gamutView1.addSpectralLocusVisual();
    gamutView1.animate();

    // CIE XYZ Colorspace
    var gamutViewSettings = {
        ...gamutViewSettings,
        ...{
                camera: {
                    position: { x: -0.5, y: 1.0, z: 2.0 },
                }
        }
    }
    var gamutView2 = new ColourAnalysis.GamutView(
        document.getElementById('gamutView2'),
        {
            ...{
                primaryColourspace: primaryColourspace,
                colourspaceModel: colourspaceModel,
            },
            ...gamutViewSettings
        }
    );
    gamutView2.addViewAxesVisual();
    gamutView2.addSpectralLocusVisual();
    gamutView2.addVisibleSpectrumVisual();
    gamutView2.animate();

    // CIE xyY Colorspace
    var colourspaceModel = 'CIE xyY';
    var gamutViewSettings = {
        ...gamutViewSettings,
        ...{
                camera: {
                    fov: 27.5,
                    position: { x: 0.0, y: 3.5, z: 1 / 3 },
                }
        }
    }
    var gamutView3 = new ColourAnalysis.GamutView(
        document.getElementById('gamutView3'),
        {
            ...{
                primaryColourspace: primaryColourspace,
                colourspaceModel: colourspaceModel,
            },
            ...gamutViewSettings
        }
    );
    gamutView3.addViewAxesVisual();
    gamutView3.addSpectralLocusVisual();
    gamutView3.addVisibleSpectrumVisual();
    gamutView3.animate();
</script>
