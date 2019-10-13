---
description: >-
  Call wandb.init each time you start a new run, before your training loop where
  you are logging model metrics.
---

# wandb.init

### Overview

Calling `wandb.init()` returns a **run** object. You can also access the **run** object anywhere in your code by importing wandb and calling `wandb.run` _\(as long as wandb.init\(\) has already been called\)_.

You should generally call `wandb.init()` once at the start of your training script.

In a Jupyter Notebook, calling `wandb.init()` will create a new run.

`wandb.init()` accepts a few keyword arguments:

* **name** — A display name for this run
* **notes** — A multiline string description associated with the run
* **config** — a dictionary-like object to set as initial config
* **project** — the name of the project to which this run will belong
* **tags** — a list of strings to associate with this run as tags
* **dir** — the path to a directory where artifacts will be written \(_default: ./wandb_\)
* **entity** — the team posting this run \(_default: your username or your default team_\)
* **job\_type** — the type of job you are logging, e.g. eval, worker, ps \(_default: training_\)
* **group** — a string by which to group other runs; see [Grouping](../advanced-features/grouping.md)
* **reinit** — whether to allow multiple calls to wandb.init in the same process \(_default: False_\)
* **id** — A unique id for this run primarily used for resuming see; [Resuming](../advanced-features/resuming.md), **must be globally unique within a project**
* **resume** — if set to True, the run auto resumes; can also be a unique string for manual resuming; see [Resuming](../advanced-features/resuming.md) \(_default: False_\)
* **anonymous** — can be "allow", "never", or "must". This enables or explicitly disables anonymous logging. \(_default: None_\)
* **force** — whether to force a user to be logged into wandb when running a script \(_default: False_\)
* **magic** — \(bool, dict, or str, optional\): magic configuration as bool, dict, json string, yaml filename. If set to True will attempt to auto-instrument your script. \(_default: None_\)
* **sync\_tensorboard** — A boolean indicating whether or not copy all tensorboard logs wandb; see [Tensorboard](../integrations/tensorboard.md) \(_default: False_\)
* **monitor\_gym** — A boolean indicating whether or not to log videos generated by OpenAI Gym; see [Ray Tune](../integrations/ray-tune.md) \(_default: False_\)
* **allow\_val\_change** — whether to allow wandb.config values to change, by default we throw an exception if config values are overwritten. \(_default: False_\)

Most of these settings can also be set with [Environment Variables](../advanced-features/environment-variables.md). This is often useful when you're running jobs on a cluster.
