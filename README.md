This is a simple wrapper over python `string.Formatter` with one difference. If
the format field is not specified in the arguments the field is not parsed. This
makes possible to build incremental templates.

Examples:

- `pynt 'Hello {name}' name=Daniel'` -> `Hello Daniel`
- `pynt '{greeting} {0}' Daniel greeting=hello` -> `Hello Daniel`
- `pynt 'Hello {name}'` -> `Hello {name}`
- `pynt '{greeting} {name}' greeting=Hello` -> `Hello {name}`

By passing `-` as first argument the template is read from the stdin:
- `pynt '{greeting} {name}' greeting=Hello | pynt - name=Daniel` -> `Hello Daniel`

Why?

It is very useful for templating files in an incremental way. To use a file
you can use process substitution from bash. `pynt <(cat file) foo bar tar=zar`

License: Apache 2.0


