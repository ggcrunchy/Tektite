Tektite
=======

Intended to be a fairly up-to-date version of TacoShell, now more or less modulized. The name comes from the
[lunar origin theory](http://en.wikipedia.org/wiki/Tektite#Nonterrestrial_source_theories) of tektites.

At the moment, this is just a TODO list, since everything is a bit scattered, some modules have both a 5.1 and JIT
version, and I haven't had a chance / excuse to play with 5.2 at all.

Basically, everything in my [Corona SDK snippets](https://github.com/ggcrunchy/corona-sdk-snippets) repository is up
to date with respect to 5.1.

At the moment, most of the JIT stuff is in my [UFO](https://github.com/ggcrunchy/ufo) fork.

There's a lot of stuff in [TacoShell](https://github.com/ggcrunchy/TacoShell) and [Marabunta](https://github.com/ggcrunchy/Marabunta)
that could stand to be folded in, but generally anything that isn't in the previously mentioned repos in updated form hasn't been
touched, since lately I've either been trying to cooperate with another framework or not able to use Lua at all. :cry:

So, at some point I'll try to bring this and that together.

There's no specific unifying philosophy behind the modules, since I add a lot of curosities and experimental stuff.
But the ideal goal would be to limit the dependencies so modules could be grabbed on-demand.

========

In no particular order:

- "class" module: Classes inject themselves into a namespace and stay there; ephemeral classes are a no-go.

- Moreover, the means of instantiating them, `class.New()`, differs from most libraries out there (LuaJIT's `ffi.new()` being perhaps
the closest) and makes including classes cumbersome and at odds with how most modules are brought in, viz. it involves a `require("class")`,
then `require("MY_CLASS")`, then `class.New("MY_CLASS")`.

- Some ideas for interface support. (In notes somewhere.)

- Take a stab at incorporating [Dylan-style multiple inheritance](http://192.220.96.201/dylan/linearization-oopsla96.html)? (A suggestion long
ago from Rici Lake on the Lua mailing list.)

- Editbox class never got any real scroll support.

- ScrollBar class was never written.

- Some of the sequence classes have some pretty weird code and might be amenable to ephemerons.

- Likewise, some of the subscribe code in WidgetGroup class.

- Some of Dropdown class's namesake logic seemed to break, perhaps owing to said WidgetGroup meddling.

- The Signalable class implementation is pretty cumbersome to use in practice for all but the most trivial slots. Perhaps just assimilate
a common code base with Delegate class?

- Investigate some of the [Self literature](http://www.cs.ucsb.edu/~urs/oocsb/self/papers/papers.html) and see if ideas can be employed in Multimethod class.

- Add more functionality to TaskQueue class. (In notes somewhere.)

- Try out [ladder queues](http://dl.acm.org/citation.cfm?id=1103324) in Timeline class. Add improvements to reflection.

- See about pulling some logic out of the Interpolator class into functions.

- For that matter, do a review of classes to see if this can be done more widely.

- Some ring buffer code is sitting around orphaned somewhere.

- Do a cleanup of Tasks and Transitions (and derivatives), and make easier to use in the common cases. (Take a page from Corona SDK's `transition.to()` and `timer.performWithDelay()`, say.)

- Put unit tests (when they exist) somewhere, add some more.

- Put together / refine some templates targeted at different SDK's, e.g. Löve2D, Corona, Moai, Native SDK, etc.

- Finally add rotations into the WidgetGroup pipeline.

- Some of the latter WidgetGroup message logic may have been a regression.

- Make UI touch- and multitouch-compatible.

- Implement some type of [relaxed weak queue](http://www.diku.dk/~jyrki/Myris/EEK2011cS.html) and one of [Takaoka's queues](http://www.cosc.canterbury.ac.nz/tad.takaoka/tri2.pdf).
(Not really urgent, but these have been stuck in my head. :smile:)

- Something with with Phi*, [Theta*](http://aigamedev.com/open/tutorials/theta-star-any-angle-paths/), etc. pathing techniques. (Maybe this is too kitchen sink-ish here.)

- Bring VarFamily class, "metacompiler", and associated logic to completion (or at least finish what was started). Bring C++ logic from [Marabunta](https://github.com/ggcrunchy/Marabunta)
over to Lua; port multi-condition nodes' parser to [LPEG](www.inf.puc-rio.br/~roberto/lpeg/).

- On that note, try to tease out assumptions, e.g. code generation in metacompiler, and make API usable in more general situations.

- Other stuff to take another look at some day: dialogue games and / or inference engines, ontology-based information systems.