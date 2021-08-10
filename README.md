
<!-- README.md is generated from README.Rmd. Please edit that file -->

# aurum

<!-- badges: start -->

<!-- badges: end -->

The goal of aurum is to …

## Installation

You can install the released version of aurum from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("aurum")
```

And the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("drkgyoung/CPRD_Aurum")
```

## Example

## Configruation

### Querying

`~/.aurum.yaml`

``` yaml
default:
  user: <mysql username>
  password: <sql password>
  server: "localhost"
  port: 3306

analysis:
  dataDatabase: cprd_data
  analysisDatabase: cprd_analysis

test-analysis:
  dataDatabase: cprd_data
  analysisDatabase: cprd_analysis_dev

test-remote:
  dataDatabase: cprd_data
  analysisDatabase: cprd_analysis_dev
  server: 127.0.0.1
  port: 3307
```

### Database loading configuration

During the database load phase some additional configuration was
required to setup the data directories This is `~/.aurum.load.yaml`

``` yaml
default:
  user: <mysql username>
  password: <sql password>
  server: "localhost"
  port: 3306
  lookupSourceDirectory: "/slade/DBs/mysql-files/CPRD/reference-data/202005_Lookups_CPRDAurum"
  dataSourceDirectories:
    - /slade/DBs/mysql-files/CPRD/master_males
    - /slade/DBs/mysql-files/CPRD/master_females

dev:
  dataDatabase: cprd_data_dev
  analysisDatabase: cprd_analysis_dev
  buildDirectory: /slade/DBs/mysql-files/CPRD/staging-dev
  loadLimit: 10

prod:
  dataDatabase: cprd_data
  analysisDatabase: cprd_analysis
  buildDirectory: /slade/DBs/mysql-files/CPRD/staging
  loadLimit: 100000

test-analysis:
  dataDatabase: cprd_data
  analysisDatabase: cprd_analysis_dev
  buildDirectory: /slade/DBs/mysql-files/CPRD/staging
  loadLimit: 10

```

## Connection and querying

This is a basic example which shows you how to solve a common problem:

``` r
library(aurum)
## basic example code
```
