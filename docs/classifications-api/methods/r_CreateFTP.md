# CreateFTP

Creates a classifications Import FTP account.

## Classifications.CreateFTP Parameters

|Name|Type|Get from Client|Description|
|----|----|------------------------------|-----------|
| **element** | `xsd:int` | YES | `relation_id` that you want to import or export \(e.g. 101=evar1, 51=product, etc\) . Using Get Elements developer will have to ask for which dimension (evar or a prop) requires classification|
| **rsid\_list** | `tns:string_array` | YES | report suites to which data is imported. Using get report suites as from the customer|
| **description** | `xsd:string` | YES | a textual description for the FTP account. What will it be used for  |
| **email\_address** | `xsd:string` | YES | the email account to notify when imports are finished. |
| **overwrite** | `xsd:boolean` | Mark as True | if true, keys that already exists will always be overwritten by new keys. |
| **export** | `xsd:boolean` | Set to false | if true, the import will be automatically exported after import. |

## Classifications.CreateFTP Response

| Type | Description |
|--------|---------------|
| [classifications\_ftp\_info](../data_types/r_classifications_ftp_info.md#) | Contains connection details for the created FTP account. |

**Parent topic:** [Methods](../methods/classifications_methods.md)

