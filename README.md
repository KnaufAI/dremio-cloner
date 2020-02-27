Dremio Cloner is a python-based utility for Dremio Enterprise. It supports the following commands: get, put, cascade-acl, report-acl.

# Command &quot;get&quot;

Command &quot;get&quot; selectively saves definitions for objects such as Source, Space, Folder, PDS, VDS, ACLs, Reflections, Queues, Rules, Tags, Wikis, and Votes from a Dremio environment into a JSON file.

The command is configured with a JSON file with configuration attributes listed below. For detailed description of the configuration JSON attributes, see Reference section below in Appendix 1.

- &quot;command&quot;:&quot;get&quot;
- &quot;source&quot;: defines Dremio Environment with
  - &quot;endpoint&quot;
  - &quot;username&quot;
  - &quot;password&quot;
  - &quot;verify\_ssl&quot;
  - &quot;is\_community\_edition&quot;
  - &quot;graph\_api\_support&quot;
- &quot;target&quot;: defines an output filename with
  - &quot;filename&quot;
- &quot;options&quot;:
  - defines logging options with
    - &quot;logging.level&quot;
    - &quot;logging.format&quot;
    - &quot;logging.filename&quot;
    - &quot;logging.verbose&quot;
  - miscellaneous options with
    - &quot;max\_errors&quot;
    - &quot;http\_timeout&quot;
  - defines scope of Space processing with
    - &quot;space.filter&quot;
    - &quot;space.exclude.filter&quot;
    - &quot;space.folder.filter&quot;
    - &quot;space.folder.exclude.filter&quot;
  - defines scope of Source processing with
    - &quot;source.filter&quot;
    - &quot;source.exclude.filter&quot;
    - &quot;source.folder.filter&quot;
    - &quot;source.folder.exclude.filter&quot;
  - defines scope of PDS processing with
    - &quot;pds.filter&quot;
    - &quot;pds.exclude.filter
    - &quot;pds.list.useapi&quot;
  - defines scope of VDS processing with
    - &quot;vds.filter&quot;
    - &quot;vds.exclude.filter&quot;
    - &quot; vds.dependencies.process\_mode&quot;

Please see a sample JSON configuration file in the Appendix 2.

# Command &quot;put&quot;

Command &quot;put&quot; selectively updates an existing Dremio Environment based on a JSON file previously generated by &quot;get&quot; command.

The command is configured with a JSON file with configuration attributes listed below. For detailed description of the configuration JSON attributes, see Reference section below in Appendix 1.

- &quot;command&quot;:&quot;put&quot;
- &quot;source&quot;: defines an output filename with
  - &quot;filename&quot;
- &quot;target&quot;: defines Dremio Environment with
  - &quot;endpoint&quot;
  - &quot;username&quot;
  - &quot;password&quot;
  - &quot;verify\_ssl&quot;
  - &quot;is\_community\_edition&quot;
- &quot;options&quot;:
  - defines logging options with
    - &quot;logging.level&quot;
    - &quot;logging.format&quot;
    - &quot;logging.filename
    - &quot;logging.verbose&quot;
  - miscellaneous options with
    - &quot;max\_errors&quot;
    - &quot;http\_timeout&quot;
    - &quot;source.retry\_timedout&quot;
    - &quot;dry\_run&quot;
  - Defines scope of User processing with
    - &quot;user.process\_mode&quot;
    - &quot;space.ignore\_missing\_acl\_user&quot;
    - &quot;space.ignore\_missing\_acl\_group&quot;
    - &quot;folder.ignore\_missing\_acl\_user&quot;
    - &quot;folder.ignore\_missing\_acl\_group&quot;
    - &quot;source.ignore\_missing\_acl\_user&quot;
    - &quot;source.ignore\_missing\_acl\_group&quot;
    - &quot;pds.ignore\_missing\_acl\_user&quot;
    - &quot;pds.ignore\_missing\_acl\_group&quot;
    - &quot;vds.ignore\_missing\_acl\_user&quot;
    - &quot;vds.ignore\_missing\_acl\_group&quot;
  - defines scope of Space processing with
    - &quot;space.process\_mode&quot;
    - &quot;space.filter&quot;
    - &quot;space.exclude.filter&quot;
    - &quot;folder.process\_mode&quot;
    - &quot;space.folder.filter&quot;
    - &quot;space.folder.exclude.filter&quot;
  - defines scope of Source processing with
    - &quot;source.process\_mode&quot;
    - &quot;source.filter&quot;
    - &quot;source.exclude.filter&quot;
    - &quot;source.folder.filter&quot;
    - &quot;source.folder.exclude.filter&quot;
  - defines scope of PDS processing with
    - &quot;pds.process\_mode&quot;
    - &quot;pds.filter&quot;
    - &quot;pds.exclude.filter
    - &quot;pds.list.useapi&quot;
  - defines scope of VDS processing with
    - &quot;vds.process\_mode&quot;
    - &quot;vds.filter&quot;
    - &quot;vds.exclude.filter&quot;
    - &quot;vds.max\_hierarchy\_depth&quot;
  - defines scope of Reflection processing with
    - &quot;reflection.process\_mode&quot;



Please see a sample JSON configuration file in the Appendix 3.

# Command &quot;cascade-acl&quot;

Command &quot;cascade-acl&quot; selectively propagates ACLs in an object hierarchy.

The command is configured with a JSON file with configuration attributes listed below. For detailed description of the configuration JSON attributes, see Reference section below in Appendix 1.

- &quot;command&quot;:&quot;cascade-acl&quot;
- &quot;target&quot;: defines Dremio Environment with
  - &quot;endpoint&quot;
  - &quot;username&quot;
  - &quot;password&quot;
  - &quot;verify\_ssl&quot;
- &quot;options&quot;:
  - defines logging options with
    - &quot;logging.level&quot;
    - &quot;logging.format&quot;
    - &quot;logging.filename
    - &quot;logging.verbose&quot;
  - miscellaneous options with
    - &quot;max\_errors&quot;
    - &quot;http\_timeout&quot;
    - &quot;source.retry\_timedout&quot;
    - &quot;dry\_run&quot;
  - defines scope of Space processing with
    - &quot;space.filter&quot;
    - &quot;space.exclude.filter&quot;
    - &quot;space.cascade-acl-origin.override-object&quot;
    - &quot;space.folder.filter&quot;
    - &quot;space.folder.exclude.filter&quot;
    - &quot;space.folder.cascade-acl-origin.filter&quot;
  - defines scope of Source processing with
    - &quot;source.filter&quot;
    - &quot;source.exclude.filter&quot;
    - &quot;source.cascade-acl-origin.override-object&quot;
    - &quot;source.folder.filter&quot;
    - &quot;source.folder.exclude.filter&quot;
  - defines scope of PDS processing with
    - &quot;pds.filter&quot;
    - &quot;pds.exclude.filter
    - &quot;pds.list.useapi&quot;
  - defines scope of VDS processing with
    - &quot;vds.filter&quot;
    - &quot;vds.exclude.filter&quot;

Note, if none of _space.cascade-acl-origin.override-object_, _space.folder.cascade-acl-origin.filter_, _source.cascade-acl-origin.override-object_ specified:

- each Space ACL will be propagated through its hierarchy and applied to Folders and VDSs as per filter configuration
- each Source ACL will be propagated through its hierarchy and applied to PDSs as per filter configuration



Please see a sample JSON configuration file in the Appendix 4.



# Command &quot;report-acl&quot;

Command &quot;report-acl&quot; command produces a security report on all objects in a Dremio environment.

The command is configured with a JSON file with configuration attributes listed below. For detailed description of the configuration JSON attributes, see Reference section below in Appendix 1.

- &quot;command&quot;:&quot;report-acl&quot;
- &quot;source&quot;: defines Dremio Environment with
  - &quot;endpoint&quot;
  - &quot;username&quot;
  - &quot;password&quot;
  - &quot;verify\_ssl&quot;
- &quot;target&quot;: defines an output filename with
  - &quot;filename&quot;
- &quot;options&quot;:
  - defines logging options with
    - &quot;logging.level&quot;
    - &quot;logging.format&quot;
    - &quot;logging.filename
    - &quot;logging.verbose&quot;
  - miscellaneous options with
    - &quot;max\_errors&quot;
    - &quot;http\_timeout&quot;
    - &quot;source.retry\_timedout&quot;
  - defines scope of Space processing with
    - &quot;report.csv.delimiter&quot;
    - &quot;report.csv.newline&quot;
  - defines scope of Space processing with
    - &quot;space.filter&quot;
    - &quot;space.exclude.filter&quot;
    - &quot;space.folder.filter&quot;
    - &quot;space.folder.exclude.filter&quot;
  - defines scope of Source processing with
    - &quot;source.filter&quot;
    - &quot;source.exclude.filter&quot;
    - &quot;source.folder.filter&quot;
    - &quot;source.folder.exclude.filter&quot;
  - defines scope of PDS processing with
    - &quot;pds.filter&quot;
    - &quot;pds.exclude.filter
    - &quot;pds.list.useapi&quot;
  - defines scope of VDS processing with
    - &quot;vds.filter&quot;
    - &quot;vds.exclude.filter&quot;

Note, that this command does not provide any option for Scope definition. Please see a sample JSON configuration file in the Appendix 5.



# Configuration Options

## _Target_ or _Source_ section, when Dremio Environment definition is required.

| **Configuration Option** | **Description** |
| --- | --- |
| _endpoint_ | Defines Dremio API endpoint. For example, [http://localhost:9047/](http://localhost:9047/). Mandatory attribute. |
| _username_ | Dremio user name. Must be an Admin. Mandatory attribute. |
| _password_ | Dremio user password. Optional field. If not provided, CLI will request password at runtime. |
| _verify\_ssl_ | If set to False, Dremio Cloner will not validate SSL certificate of the Dremio Environment. Default is True. |
| _is\_community\_edition_ | Set it to True if reading Dremio CE. Writing to Dremio CE is not supported. |
| _graph\_api\_support_ | Dremio Graph API is only available in EE starting version 4.0.0. Default value is False. |

## _Target_ or _source_ section, when defined with a file name

| **Configuration Option** | **Description** |
| --- | --- |
| filename | Defines a filename for input or output. |

## Logging options

| **Configuration Option** | **Description** |
| --- | --- |
| _logging.level_ | Defines logging level: DEBUG, INFO, WARN, ERROR |
| _logging.format_ | Logging format. For example: &quot;%(levelname)s:%(asctime)s:%(message)s&quot; |
| _logging.filename_ | Filename for logging. File will be appended if exists. If this option is omitted, standard output will be used for logging. |
| _logging.verbose_ | Default False. Produce verbose logging such as log entire entity definitions if set to True. |

## Miscellaneous options

| **Configuration Option** | **Description** |
| --- | --- |
| _max\_errors_ | Defines a number of errors at which processing will be terminated. |
| _http\_timeout_ | Timeout for each API call. This parameter might become important in certain situations when Sources defined in Dremio are not available.   |
| _dry\_run_ | Defines a Dremio Cloner execution that will not update a target Dremio environment. In conjunction with logging.level set to WARN allows to execute Dremio Cloner without an impact on the target environment and check the log file for all activities that would have been submitted to the target Dremio Environment otherwise. Respective log entries will include _dry\_run_ keyword. |
| _vds.\_max\_hierarchy\_depth_ | Defines maximum level of VDS hierarchy supported by Dremio Cloner. It&#39;s a guard rail with default value of 100. |

## Scope of Dremio Space processing

| **Configuration Option** | **Description** |
| --- | --- |
| _space.filter_ | A filter that defines what Spaces will be **included** into processing. &quot;\*&quot; will include all Spaces. Empty field will exclude all Spaces. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _space.exclude.filter_. |
| _space.exclude.filter_ | A filter that defines what Spaces will be **excluded** into processing. &quot;\*&quot; will exclude all Spaces. Empty field will include all Spaces. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _space.filter_. |
| _space.folder.filter_ | A filter that defines what Space Folders will be **included** into processing. &quot;\*&quot; will include all Folders. Empty field will exclude all Folders. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _space.folder_._exclude_._filter_. |
| _space.folder.exclude.filter_ | A filter that defines what Space Folders will be **excluded** into processing. &quot;\*&quot; will exclude all Folders. Empty field will include all Spaces. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _space.folder_._filter_. |

## Scope of Dremio Source processing

| **Configuration Option** | **Description** |
| --- | --- |
| _source.filter_ | A filter that defines what Sources will be **included** into processing. &quot;\*&quot; will include all Sources. Empty field will exclude all Sources. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _source.exclude.filter_. |
| _source.exclude.filter_ | A filter that defines what Spaces will be **excluded** into processing. &quot;\*&quot; will exclude all Spaces. Empty field will include all Sources. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _source.filter_. |
| _source.folder.filter_ | A filter that defines what Source Folders will be **included** into processing. &quot;\*&quot; will include all Folders. Empty field will exclude all Folders. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _source.exclude.filter_. |
| _source.folder.exclude.filter_ | A filter that defines what Source Folders will be **excluded** into processing. &quot;\*&quot; will exclude all Folders. Empty field will include all Spaces. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _source.filter_. |

## Scope of Dremio PDS processing

| **Configuration Option** | **Description** |
| --- | --- |
| _pds.filter_ | A filter that defines what PDSs will be **included** into processing. &quot;\*&quot; will include all PDSs. Empty field will exclude all PDSs. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _pds.exclude.filter_. |
| _pds.exclude.filter_ | A filter that defines what PDSs will be **excluded** into processing. &quot;\*&quot; will exclude all PDSs. Empty field will include all PDSs. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _pds.filter_. |
| _&quot;pds.list.useapi&quot;_ | Forces to use API for collecting list of PDSs if set to True. Default value is False which means that INFOMRATION\_SCHEMA will be utilized instead of API. False is a recommended value. |

## Scope of Dremio VDS processing

| **Configuration Option** | **Description** |
| --- | --- |
| _vds.filter_ | A filter that defines what VDSs will be **included** into processing. &quot;\*&quot; will include all VDSs. Empty field will exclude all VDSs. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _vds.exclude.filter_. |
| _vds.exclude.filter_ | A filter that defines what VDSs will be **excluded** into processing. &quot;\*&quot; will exclude all VDSs. Empty field will include all VDSs. Star may be used multiple times in the filter to define a pattern. Works in logical AND with _vds.filter_. |

## Scope of user and group processing

| **Configuration Option** | **Description** |
| --- | --- |
| _user.process\_mode_ | Determines if users will be created in the target Dremio Environment if they are referenced in the source JSON file but not in the target environment. Applicable for &quot;put&quot; command only. However, user creation is not possible with the current Dremio API. This parameter can only have a single value _skip_. |
| _&quot;space.ignore\_missing\_acl\_user&quot; __&quot;space.ignore\_missing\_acl\_group&quot;__&quot;folder.ignore\_missing\_acl\_user&quot; __&quot;folder.ignore\_missing\_acl\_group&quot;__&quot;source.ignore\_missing\_acl\_user&quot; __&quot;source.ignore\_missing\_acl\_group&quot;__&quot;pds.ignore\_missing\_acl\_user&quot; __&quot;pds.ignore\_missing\_acl\_group&quot;__&quot;vds.ignore\_missing\_acl\_user&quot;__&quot;vds.ignore\_missing\_acl\_group&quot;_ | These configuration parameters define if Dremio Cloner ignores a situation when a user or a group is defined in an ACL in the source JSON file but is not present in the target Dremio Environment. This situation is a potential security risk as an ACL may be created with no limitations in the target environment when all referenced users and groups cannot be found. Default value is False. |

## Scope of object-level processing

| **Configuration Option** | **Description** |
| --- | --- |
| _space.process\_mode __folder.process\_mode__ source.process\_mode __pds.process\_mode__ vds.process\_mode__reflection.process\_mode_ | Defines whether Dremio Cloner will 1) insert new objects only or 2) update existing objects only or 3) do an upsert. These parameters can be set to: _skip_, _create\_only_, _update\_only_, _create\_overwrite_.  _skip_ will prevent any changes to the target Dremio Environment for the specified object type.  Note, _pds.process\_mode_ can only take _skip_ and _promote._ An example of usage would be the following settings:_space.process\_mode: skip__folder.process\_mode: skip__vds.process\_mode: create\_overwrite_This configuration will not update any Space or Folder. However, it will update VDSs as per VDS related filters. |
| _vds.dependencies.process\_mode_ | Possible values: _ignore_, _get_. Default _ignore_. If set to _get_, Dremio Cloner  will collect information on all decencies throughout the object hierarchy (VDS and PDS) required for each VDS that satisfies VDS filter criteria. |

## Cascade-acl specific parameters

| **Configuration Option** | **Description** |
| --- | --- |
| _space.cascade-acl-origin.override-object_ | If specified, overrides default behavior for Space hierarchy and an ACL of the object specified in this parameter will be used through **all Spaces all hierarchies** instead of the respective Spaces&#39; ACLs. |
| _source.cascade-acl-origin.override-object_ | If specified, overrides default behavior for Source hierarchy and an ACL of the object specified in this parameter will be used through **all Source all hierarchies** instead of the respective Sources&#39; ACLs. |
| _space.folder.cascade-acl-origin.filter_ | If specified, overrides default behavior for Space hierarchy and an ACLs of the Folders selected by this will be used through **its Folder hierarchy** instead of the respective Source&#39;s ACL. |

## Report-acl specific parameters

| **Configuration Option** | **Description** |
| --- | --- |
| _report.csv.delimiter_ | A field delimiter used to generate a report. |
| _report.csv.newline_ | A new line delimiter used to generate a report. |
