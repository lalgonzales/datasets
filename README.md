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

## Web layers
`vector/web/` holds light copies of the department and municipality boundaries for web maps (WGS 84, about 110 KB and 480 KB). They keep only the code and name fields and are simplified with shared borders preserved:

```sh
ogr2ogr -t_srs EPSG:4326 departamentos_hn.geojson departamentos_hn.gpkg
npx mapshaper departamentos_hn.geojson -filter-fields cod,depto,dep -simplify 0.6% keep-shapes -clean -o vector/web/departamentos_hn_web.geojson precision=0.0001

ogr2ogr -t_srs EPSG:4326 municipios_hn.geojson municipios_hn.gpkg
npx mapshaper municipios_hn.geojson -filter-fields cod_muni,nombre,dep -simplify 1% keep-shapes -clean -o vector/web/municipios_hn_web.geojson precision=0.0001
```

They can be loaded from a browser through jsDelivr, for example `https://cdn.jsdelivr.net/gh/lalgonzales/datasets@main/vector/web/departamentos_hn_web.geojson`.
