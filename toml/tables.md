# TOML Tables

A section block in TOML is called a 'table' and looks like this:

```toml

[section]

key = "value"
```

The table is surrounded by single brackets if it is a single table element. A sub-table can be written with dotted notation and looks like:

```toml

[section]

key1 = "value"

[section.subsection]

key2 = "value"
```

In JSON, this would look something like:

```json
{
    "section": [
        {
            "key1": "value"
            "subsection": {
                "key2": "value"
            }
        },
    ]
}

```
