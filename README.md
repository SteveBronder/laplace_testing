Collection of stan-dev repo branches needed to run pathfinder

Use the following commands to download and install this repo

```bash
git clone --recurse-submodules git@github.com:SteveBronder/pathfinder_testing.git
# if you don't have ssh enabled on your local git use the following
# git clone --recurse-submodules https://github.com/SteveBronder/pathfinder_testing.git
# make cmdstan
cd pathfinder_testing/cmdstan
echo "STAN_THREADS=true" > make/local
echo "O=3 -march=native -mtune=native" >> make/local
make -j24 build
cd ..
# Install branch of cmdstanr with the pathfinder in it
R -s -e "remotes::install_local(path = './cmdstanr', force = TRUE)"
```

If you have the necessary packages (listed below) the following script should run without error.

```R
library(posteriordb)
library(ggplot2)
library(ggExtra)
library(data.table)
```

```bash
Rscript ./examples/posterior_db/posterior_db_ex.R
```

Hopefully, that should be it and you can then run the examples in this folder!

To update the repo when submodules have been updated just run

```bash
git submodule update --remote --merge --recursive
```
