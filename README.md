
<img src="https://raw.githubusercontent.com/huwb/crest-oceanrender/master/logo/crest-oceanrender-logotype1.png" width="214">

&nbsp;


# Intro

*Crest* is a technically advanced ocean renderer implemented in Unity3D 2018.3 and later. This version targets the **built-in render pipeline**, a link to the LWRP version on the Asset Store is below.

![Teaser](https://raw.githubusercontent.com/huwb/crest-oceanrender/master/img/teaser5.png)

**Discord for news/updates/discussions:** https://discord.gg/g7GpjDC

**Twitter:** [@crest_ocean](https://twitter.com/@crest_ocean)

**LWRP asset:** [Crest Ocean System LWRP](https://assetstore.unity.com/packages/tools/particles-effects/crest-ocean-system-lwrp-141674)

# Showcase Gallery

*Your game here! We're looking for projects to showcase - if you upload a video of your work to youtube and send us a link (or create a pull request) we'll put a thumbnail here and link to it.*

<a href="https://www.youtube.com/watch?feature=player_embedded&v=3i6VpdKw2Q0" target="_black"><img src="https://img.youtube.com/vi/3i6VpdKw2Q0/0.jpg" alt="Crest Ocean System - Pirate Cove Example Scene" width="240" height="180" /></a>
<a href="https://www.youtube.com/watch?feature=player_embedded&v=m2ZojyD4PZc" target="_blank"><img src="https://img.youtube.com/vi/m2ZojyD4PZc/0.jpg" alt="Critter Cove & Crest Trailer" width="240" height="180" /></a>
<a href="https://www.youtube.com/watch?feature=player_embedded&v=zCeK_Kdxqa0" target="_blank"><img src="https://img.youtube.com/vi/zCeK_Kdxqa0/0.jpg" alt="Of Ships & Scoundrels - Crest Demo" width="240" height="180" /></a>
<a href="https://www.youtube.com/watch?feature=player_embedded&v=HVlJa2J0wSc" target="_blank"><img src="https://img.youtube.com/vi/HVlJa2J0wSc/0.jpg" alt="Rogue Waves" width="240" height="180" /></a>

# Documentation

Refer to [USERGUIDE.md](https://github.com/huwb/crest-oceanrender/blob/master/USERGUIDE.md) for full documentation, including **Initial setup steps**.

There is also a getting started video here: https://www.youtube.com/watch?v=qsgeG4sSLFw&t=142s .

# Prerequisites

* Unity version:
  * Releases specify which version of Unity they were developed on.
  * The master branch generally moves forward with Unity releases to take advantage of improvements. It's rare that we take a hard dependency on a new feature in the core *Crest* code, so it is usually possible to stand *Crest* up in earlier versions of Unity.
  * One exception to the previous point is the async readback API used to read collisions and flow data back to the CPU. This code will need to be manually disabled on pre-2018 versions.
  * Another exception is prefabs which are used sparingly in *Crest* and generally do not change much between releases, but are moved forward with Unity versions and are have limited backwards compatibility.
* *Crest* example content:
  * The content requires a layer named *Terrain* which should be added to your project.
  * The post processing package is used (for aesthetic reasons), if this is not present in your project you will see an unassigned script warning which you can fix by removing the offending script.
* .NET 4.x runtime
* Direct X11 or Vulkan, other platforms targeting [shader compilation target](https://docs.unity3d.com/Manual/SL-ShaderCompileTargets.html) 4.5 or above may work but we cannot provide support for, or test on, other APIs ourselves.


# Releases

Releases are published semi-regularly and posted on the [Releases page](https://github.com/huwb/crest-oceanrender/releases). Unity packages are uploaded with each release.
Since development stability has historically been good, an option would be to grab the latest version from the master branch instead of waiting for releases.
Be aware though that we actively refactor/cleanup/change the code to pay technical debt and fight complexity so integrations may require some fixup.

*Crest* exercises [semantic versioning](https://semver.org/) and follows the branching strategy outlined [here](https://gist.github.com/stuartsaunders/448036/5ae4e961f02e441e98528927d071f51bf082662f), although there is no develop branch used yet - development occurs on feature branches that are merged directly into master.


# Issues

If you encounter an issue, please search the [Issues page](https://github.com/huwb/crest-oceanrender/issues) to see if there is already a resolution, and if you don't find one then please report it as a new issue.

There are a few issues worth calling out here:

* *Crest* does not yet support *HDRP*. If you would find such support useful, please feel free to comment in issue #201.
* Azure[Sky] requires some code to be added to the ocean shader for the fogging/scattering to work. This is a requirement of this product and apparently comes with instructions for what needs to be added. See issue #62.
* Issue with LWRP and VR - refraction appears broken due to what seems to be a bug in LWRP. See issue #206.
* Unity 2018.3 introduced significant changes to prefabs. We don't make extensive use of prefabs, but there are some for boats and others, and these may not work in earlier versions. These will need to be recreated manually.
