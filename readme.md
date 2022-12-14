# Python & Great Expectations [GE]

https://docs.greatexpectations.io/docs/tutorials/getting_started/tutorial_review

### install great expectations
```shell
# install & verify version
# https://docs.greatexpectations.io/docs/deployment_patterns/

pip install great_expectations
great_expectations --version
```

### add data context
```shell
# data context = manages project configs
# https://docs.greatexpectations.io/docs/terms/data_context/

great_expectations init
```

### add data source
```shell
# data source = standard api fo access data [file, filesystem or sql db]
# https://docs.greatexpectations.io/docs/terms/datasource/

# filesystem, pandas, notebook
# https://docs.greatexpectations.io/docs/terms/execution_engine/
great_expectations datasource new
/Users/luanmorenomaciel/GitHub/ge-data-quality-workflow/data
```

### verify yaml config file
```shell
# great_expectations.yml
# data source = ds_files_yellow_tripdata
/great_expectations/great_expectations.yml

# execution engine = [backend-specific] computing resource
PandasExecutionEngine
SparkDFExecutionEngine
SqlAlchemyExecutionEngine

# data connectors = access external data stores
InferredAssetFilesystemDataConnector
RuntimeDataConnector
```

### add expectations [data docs]
```shell
# declarative asserts to create a [expectation suite]
/Users/luanmorenomaciel/GitHub/ge-data-quality-workflow

# build suite
# use of assistant = [3]
# request batch data to analyze
great_expectations suite new

# yellow_tripdata_sample_2019 = profiling
# yellow_tripdata_sample_2019 = new

# name = [ge_suite_yellow_tripdata]
# "passenger_count" = comment
```

### validate data [checkpoint]
```shell
# checkpoint = runs a expectation suite against a batch or batch request = validation results
# perform actions = run()
great_expectations checkpoint new checkpoint_01_ge_suite_yellow_tripdata

# data_asset_name: yellow_tripdata_sample_2019-02.csv
# february = data quality issues
```