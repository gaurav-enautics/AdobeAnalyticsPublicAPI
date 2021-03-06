# CreateImport

Creates a classifications import job. This is an optional step to have a template for the first time but repetitive use is not advise unless there has beeen a change to the template.

## Classifications.CreateImport Parameters

To successfully submit a classifications Import, call Classifications.CreateImport to specify the parameters for the Import job and the header columns to be classified.

After submitting the job, you can iteratively populate row data by calling [PopulateImport](r_PopulateImport.md#).

After sending all data, call [CommitImport](r_CommitImport.md#) to finalize the Import job and submit it to the processing queue.

|Parameter|Type|Client specified|Description|
|---------|----|------------------|-----------|
| **rsid\_list** | `array(xsd:string)` | YES | The list of report suites to receive the import job. |
| **element** | `xsd:string` | YES | The report for which you want to perform a classifications import(relation_id).|
| **check\_divisions** | `xsd:int` | Specify as 1 | Specifies whether to check report suites for compatible divisions. Supported values include: `0`: Do not check report suite compatibility. `1`: \(Default\) Check report suite compatibility. Not to be used only one job in rsid list. It is recommended we create seperate jobs for each report suite. |
| **description** | `xsd:string` | Specify good description to indicate job | A description of the import job. |
| **email\_address** | `xsd:string` | YES | The email address to receive job notifications. |
| **export\_results** | `xsd:int` | Specify as 1 | Specifies whether to automatically perform an export when the import job finishes processing. Supported values include: `0`: \(Default\) Do not export. `1`: Export when the job completes. |
| **header** | `array(xsd:string)` | YES | An array of column values for classification. First column is required to be the `key`.|
| **overwrite\_conflicts** | `xsd:int` | Specify as 1 | Specifies whether to overwrite data when conflicts occur. Supported values include: `0`: \(Default\) Do not overwrite data on a conflict. `1`: Overwrite data on a conflict. |

## Classifications.CreateImport Response

|Name|Type|Description|
|----|----|-----------|
| **classifications\_create\_job\_response** | `xsd:int` | A unique job ID that identifies this classifications import job. If the job import is unsuccessful, an error code is returned instead of a job ID. |

**Parent topic:** [Methods](../methods/classifications_methods.md)

