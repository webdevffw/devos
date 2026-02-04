## A layered developer environment

An opinionated, reproducible “developer OS” mean to run on any given developer machine.

Every meaningful choice (tools, preferences, visuals, behavior) is:

* Centralized
* Versioned
* Reproducible

The setup is:
* Idempotent (safe to re-run, always converges to the same state)
* Portable (new laptop, VM, container, remote box → same experience)
* Device-independent (no hidden state or manual tweaking)

Configuration is:
* Mostly declarative
* Script-driven with a single entry point
* Capable of fully overwriting existing configs when desired

Research is treated as a first-class artifact:
* Maintian a durable decision record
* A future lookup resource
* A way to compare alternatives at each functional layer before committing
