# Theme Parks Project

This is a Meltano project for `tap-theme-parks` to sync data to `target-jsonl` or `target-postgres`.

For more information about some of the plugins in this project, check out these GitHub repos and their READMEs:
- [tap-theme-parks](https://github.com/DanielPDWalker/tap-theme-parks)
- [dbt-tap-theme-parks](https://github.com/DanielPDWalker/dbt-tap-theme-parks) (Only applicable if using `target-postgres``, find out more below)

## Setup

### Prerequisites

Have Python and Meltano installed.

- [Download Python](https://www.python.org/downloads/)
- [Install Meltano](https://docs.meltano.com/getting-started/installation)

---

### Running with `target-jsonl` - (No settings required)

1. Clone this repo, and open it in your terminal
1. `meltano install`
1. `meltano run tap-theme-parks target-jsonl`

Now you will see some `.json` files in the `output/` directory containing theme park data!

---

### Using other targets

If you want to persist you data a different target, you will need to have an instance of that target and provide the credentials for this project to connect to it. **See step 2 below.**

Its as easy a browsing the [MeltanoHub](https://hub.meltano.com/), finding the loader you want to use and then:

1. `meltano add loader <chosen-loader>`
1. [Provide your settings for the loader](https://docs.meltano.com/guide/configuration)
1. `meltano run tap-theme-parks <chosen-loader>`

### Using target-postgres

If you `target-postgres`, again by having a postgres database and the credentials to connect to it, you can then use the dbt project included in this project. 

The [dbt-tap-theme-parks]() project takes data from the raw tables created by [tap-theme-parks]() and build easy to use and query dimension and fact tables. It also includes a snapshot to keep track of the most recent live data that you sync.

There is a Meltano job already in this project to run with postgres and dbt:

`meltano run tap-theme-parks-to-target-postgres`
 