# GGIS 407 – Lab 5: PostgreSQL and PostGIS

Two Jupyter notebooks for GGIS 407 (University of Illinois Urbana-Champaign), set up to run on the
[I-GUIDE JupyterHub](https://jupyter.i-guide.io) with the `iguide` kernel.

| Notebook | Covers |
| --- | --- |
| `Lab5_PostgreSQL.ipynb` | Databases and SQL: creating tables, inserting, updating, deleting, sorting and aggregating data, CSV import/export, natural, inner and outer joins |
| `Lab5_PostGIS.ipynb` | Spatial databases: the PostGIS extension, geometry columns and metadata, importing a shapefile with `shp2pgsql`, spatial queries, reprojection, areas, centroids and distance queries |

## How the database works

Each notebook starts with two setup cells. The first installs, once per account, the PostgreSQL 16 server and
PostGIS from conda-forge into `~/pgenv`, plus the `jupysql` (`%sql` magic) and `psycopg2` Python packages.
The second creates a database cluster in `~/pgdata` the first time and starts the server on `localhost:5432`
if it isn't running. Both notebooks share the same server. Nothing is installed system-wide.

## Data

- `data/IL_Municipalities_2022.shp`: boundaries of the 1,296 incorporated cities, villages and towns in Illinois,
  from the U.S. Census Bureau 2022 cartographic boundary file `cb_2022_17_place_500k` (census-designated places
  removed), in NAD83 (EPSG:4269). Columns: GEOID, NAME, NAMELSAD, TYPE (city/village/town), ALAND, AWATER (m²).

Adapted by Anand Padmanabhan from earlier CyberGISX course notebooks.
