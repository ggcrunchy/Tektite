Tektite
=======

**Tektite** is intended to be a depot of sorts for framework-agnostic Lua modules, able to be added say as a submodule in other
projects. The name comes from the [lunar origin theory](http://en.wikipedia.org/wiki/Tektite#Nonterrestrial_source_theories)
of tektites.

This is rather a work in progress, as the modules to be incorporated are a bit scattered. Some, for instance, have both a 5.1 and
JIT version (I haven't yet had a chance / excuse to play with 5.2).

Basically, everything scraped from my [Corona SDK snippets](https://github.com/ggcrunchy/corona-sdk-snippets) repository is current
with respect to 5.1. Eventually, the plan there is to depend on **Tektite** and another submodule or two.

At the moment, any pertinent JIT things are either in my [UFO](https://github.com/ggcrunchy/ufo) fork or the [Little Green Men](https://github.com/ggcrunchy/LittleGreenMen)
project spun off from that, and have yet to be added (how to nicely do so eludes me, at the moment).

There's much in [TacoShell](https://github.com/XibalbaStudios/TacoShell), [Marabunta](https://github.com/XibalbaStudios/Marabunta), and
[Lua of Interest](https://bitbucket.org/ggcrunchy/luaofinterest) that could stand to be folded in, but generally anything that isn't in
the aforementioned repos already won't have been touched in some time, for various reasons, and would need a fair bit of modernization.

There's no specific unifying philosophy behind the modules, since I add things as the need arises, and now and then curiosities and / or
experiments. Generally the intent is to minimize external dependencies so the modules can just be dropped in. This is more or less a
framework, so not a lot of effort has been spared making individual modules stand-alone.