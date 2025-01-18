# datasets
Repository with Honduras datasets

## Description
This repository contains datasets for Honduras. The data can be downloaded and used with Python, for example with the `geopandas` library.

## Download
You can download the dataset from the following URL:
[Download Dataset](http://example.com/dataset.zip)

## Usage
To use the dataset with Python and `geopandas`, you can follow the example below:

```python
import geopandas as gpd

# Replace 'path_to_dataset' with the path to the downloaded dataset
gdf = gpd.read_file('path_to_dataset')
print(gdf.head())
```
