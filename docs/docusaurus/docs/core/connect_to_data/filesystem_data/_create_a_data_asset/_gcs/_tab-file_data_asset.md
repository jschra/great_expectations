import TabItem from '@theme/TabItem';
import Tabs from '@theme/Tabs';

import PrereqPythonInstall from '../../../../_core_components/prerequisites/_python_installation.md'
import PrereqGxInstall from '../../../../_core_components/prerequisites/_gx_installation_with_gcs_dependencies.md'
import PrereqDataContext from '../../../../_core_components/prerequisites/_preconfigured_data_context.md'

### Prerequisites
- <PrereqPythonInstall/>.
- <PrereqGxInstall/>.
- <PrereqDataContext/>.
- Access to data files in Google Cloud Storage.
- [A pandas](/core/connect_to_data/filesystem_data/filesystem_data.md?data_source_type=pandas&environment=gcs#create-a-data-source) or [Spark Filesystem Data Source configured for Google Cloud Storage data files](/core/connect_to_data/filesystem_data/filesystem_data.md?data_source_type=spark&environment=gcs#create-a-data-source).

### Procedure

<Tabs 
   queryString="procedure"
   defaultValue="instructions"
   values={[
      {value: 'instructions', label: 'Instructions'},
      {value: 'sample_code', label: 'Sample code'}
   ]}
>

<TabItem value="instructions" label="Instructions">

1. Retrieve your Data Source.

   Replace the value of `data_source_name` in the following code with the name of your Data Source and execute it to retrieve your Data Source from the Data Context:

   ```python title="Python" name="docs/docusaurus/docs/core/connect_to_data/filesystem_data/_create_a_data_asset/_gcs/_file_asset.py - retrieve Data Source"
   ```

2. Define your Data Asset's parameters.

   To define a File Data Asset for Google Cloud Storage you provide the following elements:

   - `name`: A name by which you can reference the Data Asset in the future.  This should be unique among Data Assets on the same Data Source.
   - `gcs_prefix`: The beginning of the object key name.
   - `gcs_delimiter`: Optional. A character used to define the hierarchical structure of object keys within a bucket (default is "/").
   - `gcs_recursive_file_discovery`: Optional. A boolean indicating if files should be searched recursively from subfolders (default is False).
   - `gcs_max_results`: Optional. The maximum number of keys in a single response (default is 1000).

   This example uses taxi trip data stored in `.csv` files in the `data/taxi_yellow_tripdata_samples/` folder within the Google Cloud Storage Data Source:

   ```python title="Python" name="docs/docusaurus/docs/core/connect_to_data/filesystem_data/_create_a_data_asset/_gcs/_file_asset.py - define Data Asset parameters"
   ```

3. Add the Data Asset to your Data Source.

   A new Data Asset is created and added to a Data Source simultaneously.  The file format that the Data Asset can read is determined by the method used when the Data Asset is added to the Data Source.

   - To see the file formats supported by a pandas File Data Source, reference the `.add_*_asset(...)` methods in [the API documentation for a `PandasFilesystemDatasource`](/reference/api/datasource/fluent/PandasFilesystemDatasource_class.mdx).
   - To see the file formats supported by a Spark File Data Source, reference the `.add_*_asset(...)` methods in [the API documentation for a `SparkFilesystemDatasource`](/reference/api/datasource/fluent/SparkFilesystemDatasource_class.mdx).

   The following example creates a Data Asset that can read `.csv` file data:

   ```python title="Python" name="docs/docusaurus/docs/core/connect_to_data/filesystem_data/_create_a_data_asset/_gcs/_file_asset.py - add Data Asset"
   ```

</TabItem>

<TabItem value="sample_code" label="Sample code">

   ```python title="Python" name="docs/docusaurus/docs/core/connect_to_data/filesystem_data/_create_a_data_asset/_gcs/_file_asset.py - full example"
   ```

</TabItem>

</Tabs>