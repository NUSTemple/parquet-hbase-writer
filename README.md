# Spark HBase Ingestion

### Goal:
- Load data from hdfs path `/data/wafer_map_wm811k/wm811k.parquet`
- Ingest data into hbase table `wafer_map_811k:wm811k`
- column `rowkey` will be the row key of table
- column family is `cf`
- other columns will be column qualifier

### Dataset
- The data is converted from pkl from [Kaggle WM811K](https://www.kaggle.com/qingyi/wm811k-wafer-map)
- The data has been ETL for ease to ingest into HBase
- Python array for wafer map has been transformed into base64 string
- Final data has below columns

| rowkey        | lot_name   | wafer_index | failure_type | wafer_map            | map_width | map_heigth | die_size |
|:--------------|:-----------|:------------|:-------------|:---------------------|:----------|:-----------|:---------|
| lot0000001_02 | lot0000001 | 2           | none         | QIBAQIBAAAAAAAAAA... | 45        | 48         | 1683     |
| lot0000001_01 | lot0000001 | 1           | none         | gEBAQEBAAAAAAAAAA... | 45        | 48         | 1683     |
