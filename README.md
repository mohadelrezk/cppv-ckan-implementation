Core Public Policy Vocabulary CKAN Implementation
===========================

cppv ckan implementation (schema customization according to cppv standards)

A- documentation: 
http://vmogi01.deri.ie/egovcppv/ 

B- examble:
http://vmrtpa05.deri.ie:8080/dataset
C- publications:
[1] http://dl.acm.org/citation.cfm?id=3047366
[2] in press


Installation [CKAN Scheming]
-------------
[1] Clone and Install:
```
$cd /git
$git clone https://github.com/ckan/ckanext-scheming.git scheming
$cd git/scheming
$python setup.py develop
$. /usr/lib/ckan/default/bin/activate
```
[2] Edit CKAN schema:

```
$cd /git/scheming/ckanext/scheming
$nano to Create new schema for examble public_policy_schema.json or edit existing one
$nano preset.jsom for complex schema operations
```
[3] Adding schema location to ckan:
```
$cd /usr/lib/ckan/default/src/ckan
$nano to edit {development.ini or production.ini} according to the following ..
```
part of .ini file to edit
```
{
ckan.plugins = scheming_datasets

#   module-path:file to schemas being used
scheming.dataset_schemas = ckanext.spatialx:spatialx_schema.json
                           ckanext.spatialx:spatialxy_schema.json
#   will try to load "spatialx_schema.json" and "spatialxy_schema.json"
#   as dataset schemas
#
#   URLs may also be used, e.g:
#
# scheming.dataset_schemas = http://example.com/spatialx_schema.json

#   Preset files may be included as well. The default preset setting is:
scheming.presets = ckanext.scheming:presets.json

#   The is_fallback setting may be changed as well. Defaults to false:
scheming.dataset_fallback = false

}

```


