# OOS_UTIL_LOB

- [Constants](#constants)
- [CLOB2BLOB Function](#clob2blob)
- [BLOB2CLOB Function](#blob2clob)
- [GET_FILE_SIZE Function](#get_file_size)
- [GET_LOB_SIZE Function](#get_lob_size)
- [GET_LOB_SIZE Function](#get_lob_size)
- [REPLACE_CLOB Function](#replace_clob)


## <a name="constants"></a>Constants

Name | Code | Description
--- | --- | ---
gc_unit_b | `gc_unit_b constant varchar2(1) := 'B';` | 
gc_unit_kb | `gc_unit_kb constant varchar2(2) := 'KB';` | 
gc_unit_mb | `gc_unit_mb constant varchar2(2) := 'MB';` | 
gc_unit_gb | `gc_unit_gb constant varchar2(2) := 'GB';` | 
gc_unit_tb | `gc_unit_tb constant varchar2(2) := 'TB';` | 
gc_unit_pb | `gc_unit_pb constant varchar2(2) := 'PB';` | 
gc_unit_eb | `gc_unit_eb constant varchar2(2) := 'EB';` | 
gc_unit_zb | `gc_unit_zb constant varchar2(2) := 'ZB';` | 
gc_unit_yb | `gc_unit_yb constant varchar2(2) := 'YB';` | 
gc_size_kb | `gc_size_kb constant number := power(1024, 2);` | 
gc_size_mb | `gc_size_mb constant number := power(1024, 3);` | 
gc_size_gb | `gc_size_gb constant number := power(1024, 4);` | 
gc_size_tb | `gc_size_tb constant number := power(1024, 5);` | 
gc_size_pb | `gc_size_pb constant number := power(1024, 6);` | 
gc_size_eb | `gc_size_eb constant number := power(1024, 7);` | 
gc_size_zb | `gc_size_zb constant number := power(1024, 8);` | 
gc_size_yb | `gc_size_yb constant number := power(1024, 9);` | 





 
## <a name="clob2blob"></a>CLOB2BLOB Function


<p>
<p>Convers clob to blob</p>
</p>

### Syntax
```plsql
function clob2blob(
  p_clob in clob)
  return blob
```

### Parameters
Name | Description
--- | ---
`p_clob` | Clob to conver to blob
*return* | blob
 
 





 
## <a name="blob2clob"></a>BLOB2CLOB Function


<p>
<p>Converts blob to clob</p><p>Notes:</p><ul>
<li>Copied from <a href="http://stackoverflow.com/questions/12849025/convert-blob-to-clob">http://stackoverflow.com/questions/12849025/convert-blob-to-clob</a></li>
</ul>

</p>

### Syntax
```plsql
function blob2clob(
  p_blob in blob)
  return clob
```

### Parameters
Name | Description
--- | ---
`p_blob` | blob to be converted to clob
*return* | clob
 
 





 
## <a name="get_file_size"></a>GET_FILE_SIZE Function


<p>
<p>Returns human readable file size</p>
</p>

### Syntax
```plsql
function get_file_size(
  p_file_size in number,
  p_units in varchar2 default null)
  return varchar2
```

### Parameters
Name | Description
--- | ---
`p_file_size` | size of file in bytes
`p_units` | See <code>gc_size_...</code> consants for options. If not provided, most significant one automatically chosen.
*return* | Human readable file size
 
 





 
## <a name="get_lob_size"></a>GET_LOB_SIZE Function


<p>
<p>See get_file_size</p>
</p>

### Syntax
```plsql
function get_lob_size(
  p_lob in clob,
  p_units in varchar2 default null)
  return varchar2
```

### Parameters
Name | Description
--- | ---
`p_lob` | 
`p_units` | 
 
 





 
## <a name="get_lob_size"></a>GET_LOB_SIZE Function


<p>
<p>See get_file_size</p>
</p>

### Syntax
```plsql
function get_lob_size(
  p_lob in blob,
  p_units in varchar2 default null)
  return varchar2
```

### Parameters
Name | Description
--- | ---
`p_lob` | 
`p_units` | 
 
 





 
## <a name="replace_clob"></a>REPLACE_CLOB Function


<p>
<p>Replaces p_search with p_replace</p><p>Oracle&#39;s replace function does handle clobs but runs into 32k issues</p><p>Notes:</p><ul>
<li>Source: <a href="http://dbaora.com/ora-22828-input-pattern-or-replacement-parameters-exceed-32k-size-limit/">http://dbaora.com/ora-22828-input-pattern-or-replacement-parameters-exceed-32k-size-limit/</a></li>
</ul>

</p>

### Syntax
```plsql
function replace_clob(
  p_str in clob,
  p_search in varchar2,
  p_replace in clob)
  return clob
```

### Parameters
Name | Description
--- | ---
`p_str` | 
`p_search` | 
`p_replace` | 
*return* | Replaced string
 
 





 
