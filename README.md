Collection of stan-dev repo branches needed to run pathfinder

Use the following commands to download and install this repo

```bash
git clone --recurse-submodules https://github.com/SteveBronder/laplace_testing
# make cmdstan
cd laplace_testing/cmdstan
echo "STAN_THREADS=true" > make/local
echo "O=3 -march=native -mtune=native" >> make/local
make -j4 build
cd ..
```

Hopefully, that should be it and you can then run the examples in this folder!

To update the repo when submodules have been updated just run

```bash
git submodule update --remote --merge --recursive
```
