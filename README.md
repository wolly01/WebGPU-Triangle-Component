# WebGPU-Triangle-Component
A single page repo giving an example test integration of a webgpu basic triangle wrapped in a web-component

---

This small repo is designed to test the difficulties that arrise when combining a webgpu render loop with a custom web-components lifecycle. The perceived difficulty of this project lay in anticipating overlap with the state/lifecyle of the component with the state management of a webgpu device, the aliasing of which possibly requiring very strong coupling and thus resulting in having a hard to genrelize code and tusly tricky to maintain codebase.

However, preliminary results of this test indicate completely the opposite with the only real overlap between the two can be seen in a boolean valued `Guard()` function that keeps tabs on when (gpu) resources need to be freed due to the disconnection or destruction of the custom element weapper.
This `Guard` function is barly even coupled with the render-code it acts to guard resources for, as it can be wrapped up into a combinator argument keeping it away from the render code. As it stands there is still a small amount of alizing in the code, but there are many ways that can be weakened also.

---

The component itself is basic, spinning rgb triangle. Nothing fancy.

---
We do not include licensing as this code is intended to serve as an example proof of concept to be looked at by learners to gain insight, not as a basis for any further work, at least without some amount of refactoring. For me to know *how* to properly refactor this code I need to be somewhere further ahead in my webgpu journy, so aany cleenup of this project I do weill happen not in the short-term.
---
Should the github-page be live, the example is avaliable [here](https://wolly01.github.io/WebGPU-Triangle-Component/). Note that in order for this example to run WebGPU needs to be supported and enabled on your browser.
