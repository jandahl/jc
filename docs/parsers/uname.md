
# jc.parsers.uname
jc - JSON CLI output utility `uname -a` command output parser

Usage (cli):

    $ uname -a | jc --uname

    or

    $ jc uname -a

Usage (module):

    import jc.parsers.uname
    result = jc.parsers.uname.parse(uname_command_output)

Limitations:

    must use 'uname -a'

Compatibility:

    'linux', 'darwin', 'freebsd'

Example:

    $ uname -a | jc --uname -p
    {
      "kernel_name": "Linux",
      "node_name": "user-ubuntu",
      "kernel_release": "4.15.0-65-generic",
      "operating_system": "GNU/Linux",
      "hardware_platform": "x86_64",
      "processor": "x86_64",
      "machine": "x86_64",
      "kernel_version": "#74-Ubuntu SMP Tue Sep 17 17:06:04 UTC 2019"
    }


## info
```python
info()
```


## process
```python
process(proc_data)
```

Final processing to conform to the schema.

Parameters:

    proc_data:   (dictionary) raw structured data to process

Returns:

    Dictionary. Structured data with the following schema:

    {
        "kernel_name":        string,
        "node_name":          string,
        "kernel_release":     string,
        "operating_system":   string,
        "hardware_platform":  string,
        "processor":          string,
        "machine":            string,
        "kernel_version":     string
    }


## parse
```python
parse(data, raw=False, quiet=False)
```

Main text parsing function

Parameters:

    data:        (string)  text data to parse
    raw:         (boolean) output preprocessed JSON if True
    quiet:       (boolean) suppress warning messages if True

Returns:

    Dictionary. Raw or processed structured data.

