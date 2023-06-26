# Theme Parks Project

This is a Meltano project for `tap-theme-parks` to sync data to `target-jsonl` or `target-postgres`.

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

If you want to persist you data to a postgres (or any other database/destination), you will need to provide the credentials for this project to connect to it. **See step 2 below.**

Its as easy a browsing the [MeltanoHub](https://hub.meltano.com/), finding the loader you want to use and then:

1. `meltano add loader <chosen-loader>`
1. [Provide your settings for the loader](https://docs.meltano.com/guide/configuration)
1. `meltano run tap-theme-parks <chosen-loader>`
