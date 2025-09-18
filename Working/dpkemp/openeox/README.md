# OpenEoX Schema Examples

## OpenEoX TC core schema (Sep 14, 2025):
https://github.com/oasis-tcs/openeox/tree/main/eox-core-v-1-0/schema

### Initial Information model translated from JSON Schema:
```json
{
  "meta": {
    "package": "https://docs.oasis-open.org/openeox/v1.0/schema/core/",
    "jadn_version": "http://oasis-open.org/openc2/jadn/v2.0/schema/",
    "title": "EoX Information - Core",
    "description": "The schema for representing End-of-Life (EoL), End-of-Security-Support (EoSSec) and other End-of information in OpenEoX.",
    "roots": ["Root"]
  },

  "types": [
    ["Root", "Record", [], "The schema for representing End-of-Life (EoL), End-of-Security-Support (EoSSec) and other End-of information in OpenEoX.", [
      [1, "$schema", "String", [], "Specifies the schema the JSON object must be valid against."],
      [2, "end_of_life", "eox_timestamp_t", [], "Indicates the last day when the particular product is officially supported in any way by the vendor."],
      [3, "end_of_sales", "eox_timestamp_t", ["[0"], "Indicates the last day when a particular product may be ordered by customers from vendor sales channels."],
      [4, "end_of_security_support", "eox_timestamp_t", [], "Indicates the last day when the vendor has committed to providing security remediations for the particular product."],
      [5, "last_updated", "String", [], "Contains the RFC 3339 timestamp when the record was last updated."]
    ]],

    ["eox_timestamp_t", "String", [], "Contains the timestamp at which the product reaches the specified stage or the indicator that this is still 'to be announced'."]
  ]
}
```
* Note that JSON Schema does not define a name for the EoX type, so IM translater assigns it the name "Root".
JSON Schema should define the "EoX" object in `$defs` so that it has a name.

* The schema identifier is an arbitrary string. Although it is defined as a constant value, it would be informative
to add a `uri` format keyword, as documentation and as a check if the constant value is updated.
It refers to the [JSON Schema](https://json-schema.org/draft/2020-12/draft-bhutton-json-schema-01#name-the-id-keyword)
`$id` "https://docs.oasis-open.org/openeox/v1.0/schema/core.json".

* The information model uses a `package` namespace (URI): "https://docs.oasis-open.org/openeox/v1.0/schema/core/",
not a URL of a file, because the identical IM can be defined in multiple file formats.

* The JSON Schema eox_timestamp_t type is `oneOf` /date-time format or the fixed string "tba".  The IM translator did
not process the `oneOf` directive and the examples will be edited to include it in the recommended IM. 

* The use of "_t" or "_type" suffixes to denote types is awkward and hard to read. A naming convention that uses lower-case
for properties and upper-case names for types is more standard and more readable.  In this example, `eox_timestamp_t`
would be named something like `EoxTimestamp` or `EoX_Timestamp`, and if there were a separate `end_of_life` type
it could be named `End_Of_Life` or `EndOfLife`.

## EoX Core Schema Alternate Formats:

### IDL
```
       title: "EoX Information - Core"
     package: "https://docs.oasis-open.org/openeox/v1.0/schema/core/"
 description: "The schema for representing End-of-Life (EoL), End-of-Security-Support (EoSSec) and other End-of information in OpenEoX."
       roots: ["Root"]
jadn_version: "http://oasis-open.org/openc2/jadn/v2.0/schema/"

Root = Record                                    // The schema for representing End-of-Life (EoL), End-of-Security-Support (EoSSec) and other End-of information in OpenEoX.
   1 $schema          String                     // Specifies the schema the JSON object must be valid against.
   2 end_of_life      eox_timestamp_t            // Indicates the last day when the particular product is officially supported in any way by the vendor.
   3 end_of_sales     eox_timestamp_t optional   // Indicates the last day when a particular product may be ordered by customers from vendor sales channels.
   4 end_of_security_support eox_timestamp_t     // Indicates the last day when the vendor has committed to providing security remediations for the particular product.
   5 last_updated     String                     // Contains the RFC 3339 timestamp when the record was last updated.

eox_timestamp_t = String                         // Contains the timestamp at which the product reaches the specified stage or the indicator that this is still 'to be announced'.
```

### Markdown Property Tables:

The schema for representing End-of-Life (EoL), End-of-Security-Support (EoSSec) and other End-of information in OpenEoX.

**Type: Root (Record)**

| ID | Name                        | Type            | \#   | Description                                                                                                         |
|----|-----------------------------|-----------------|------|---------------------------------------------------------------------------------------------------------------------|
| 1  | **$schema**                 | String          | 1    | Specifies the schema the JSON object must be valid against.                                                         |
| 2  | **end_of_life**             | eox_timestamp_t | 1    | Indicates the last day when the particular product is officially supported in any way by the vendor.                |
| 3  | **end_of_sales**            | eox_timestamp_t | 0..1 | Indicates the last day when a particular product may be ordered by customers from vendor sales channels.            |
| 4  | **end_of_security_support** | eox_timestamp_t | 1    | Indicates the last day when the vendor has committed to providing security remediations for the particular product. |
| 5  | **last_updated**            | String          | 1    | Contains the RFC 3339 timestamp when the record was last updated.                                                   |

**********

| Type Name           | Type Definition | Description                                                                                                                    |
|---------------------|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
| **eox_timestamp_t** | String          | Contains the timestamp at which the product reaches the specified stage or the indicator that this is still 'to be announced'. |

**********

### Entity Relationship Diagram:

<img src="information-model/eox-core-ia.jpg" width="360">

## Updated Information Model and JSON Schema:

Incorporates updates to the initial IM recommended above.

TBSL