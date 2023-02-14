## Background

Ubuntu came up with a packaging format called `snap`. 
Why?
It sounds like container.
Why not reuse container?

## Why Ubuntu created snap? Why not reuse Docker?

Docker abstracts few things too many for local workload.
Example: network.
Snap is targetted more toward "run here, but maintain the 'cleanliness' of the local system".
Thus, snap doesn't abstract the network.

This make sense as `snap` target edge computing where "create 5 instances of redis" doesn't make sense. But "run redis here" does.
Or, closer to home: "install 6 instances of git here" will make you scratch your head.
You just want git in your system, not 6 instances of it.

Having learned this, I am actually quite excited with the approach that this brings.

## Some points regarding snap

* With container-like packaging, e.g. bring-your-own-dependencies, snap package has notably bigger size.
* Each snap will be mounted, so it will clutter `mount`
* There are some debates regarding openness of snap store, to the point Linux Mint, a derivative of Ubuntu, flatly refuse to adopt snap, see Linux Mint [May 2020](https://blog.linuxmint.com/?p=3906),
[June 2019](https://blog.linuxmint.com/?p=3766).
The arguments boils down to the control of snap store [Linux Mint User Guide on snap](https://linuxmint-user-guide.readthedocs.io/en/latest/snap.html):
  * Snap can only works with ubuntu Store
  * Nobody else knows or can make Snap Store
  * Snap client is designed to work with only one source
  * Ubuntu Store cannot be audited nor patched openly
* Snap is auto-updating, and it is quite a no-no in Linux perspective.

## Ref

Talk by Mark Shuttleworth on snap [ref](https://www.youtube.com/watch?v=0z3yusiCOCk).