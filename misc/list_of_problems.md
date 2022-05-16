## Background

Reading about `snap` packaging, booting OS, protocol design, language design, jet engine engineering, and other stuff, I spot a recurring disturbing thought in me:

>  "What problems need solving?"

This writing attempt to get it out of my system.

### Example: Differential Gears

One example of what I considered a good "incremental explanation" is this video:
[How Differential Steering Works](https://www.youtube.com/watch?v=yYAw79386WI).

The video explains gradually on how we arrive at differential gear.
It started with the problem of two wheels that needs to have different speed when turning a corner,
then it gradually solves the problem by introducing spokes and built the solution toward differential gears.

Each step of the partial solution is clearly linked with the sub-problem it tries to solve.

---

List of points to be elaborated:

* Package distribution:
  * format
  * discoverability
  * storage
  * maintenance
  * patch
  * compatibility

* OS:
  * finding hardware
  * control of resources / scheduling
  * interation with hardware

* protocol design:
  * reliability (e.g. TCP/UDP)
  * congestion control
  * security
  * routing
  * discoverability

* language design:
  * atomic unit
  * means of combination
  * means of abstraction