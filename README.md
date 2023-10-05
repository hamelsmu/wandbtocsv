# wandbtocsv

<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

## Background

`wandbtocsv` allows you to quickly export a flat csv file of the top
level metrics, config, etc. from your [Weights &
Biases](https://wandb.ai/) runs in an easy to use CLI interface.

## Install

``` sh
pip install wandbtocsv
```

## How to use

``` python
!wandbtocsv -h
```

    usage: wandbtocsv [-h] [--entity ENTITY] [--project PROJECT]
                      [--output_file OUTPUT_FILE]

    options:
      -h, --help                 show this help message and exit
      --entity ENTITY            Entity for the WANDB runs. If not provided,
                                 attempts to fetch from environment variable
                                 'WANDB_ENTITY'.
      --project PROJECT          Project for the WANDB runs. If not provided,
                                 attempts to fetch from environment variable
                                 'WANDB_PROJECT'.
      --output_file OUTPUT_FILE  Path to save the output CSV. Default name format:
                                 {entity}-{project}-{mmddyy}.csv

``` python
!wandbtocsv --entity hamelsmu --project deepspeed-data
```

    Fetching runs... ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:00
    Saved 231 runs to hamelsmu-deepspeed-data-100523.csv

## Bonus, explore your wandb runs in [Datasette](https://datasette.io/)

``` bash
csvs-to-sqlite hamelsmu-deepspeed-data-100523.csv hamelsmu-deepspeed-data-100523.db
datasette hamelsmu-deepspeed-data-100523.db -o
```
