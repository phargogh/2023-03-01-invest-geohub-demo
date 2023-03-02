# 2023-03-01-invest-geohub-demo
A demonstration of running InVEST on the GeoHub through Jupyter Notebooks

## Installation

Open a terminal shell and execute the following:

```
curl -Ls https://micro.mamba.pm/api/micromamba/linux-64/latest | tar -xvj bin/micromamba
./bin/micromamba create -y -c conda-forge -p ./env310 python=3.10 natcap.invest ipykernel geopandas rasterio folium matplotlib mapclassify
INVEST_VERSION=$(./env310/bin/python -c "import natcap.invest; print(natcap.invest.__version__)")
./env310/bin/ipython kernel install --user --name="InVEST-$INVEST_VERSION"
```

And then, open up a new notebook using the kernel!

# Cleanup

```
jupyter kernelspec uninstall invest-$INVEST_VERSION
cd ~
rm -r micromamba env310 SDR bin/micromamba sdr_workspace_gura
```
