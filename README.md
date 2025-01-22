# Datasets
Repository with Honduras datasets

## Data Source
The data is sourced from the 🔗[National Institute of Forest Development, Protected Areas, and Wildlife (ICF)](https://icf.gob.hn/) of Honduras through the 🌐[WFS service](https://geoportal.icf.gob.hn/).

**Note:** In case the Geoportal returns an HTTP 500 error, please refresh the page.

## Usage Instructions
To use the files, you can copy the link of the dataset and append `?raw=true` at the end of the URL. This link can be used to load the data for example into a Python notebook using libraries such as `geopandas`.

### Example
```python
import geopandas as gpd

url = "https://github.com/your-repo/datasets/path/to/yourfile.geojson?raw=true"
data = gpd.read_file(url)
print(data.head())
```

Additionally, the datasets are available in `gpkg` format and `shapefile` compressed in `.zip` files, which can be downloaded and used in GIS software.

You can explore this 🧾[Notebook](notebooks/download_wfs.ipynb) to see how the data was obtained from the Geoportal of the ICF.

I hope this repository is useful for your projects and research.
