This is a simple wrapper over python `string.Formatter` with one difference. If
the format field is not specified in the arguments the field is not parsed. This
makes possible to build incremental templates.

Examples:

`pynt 'Hello {name}' name=Daniel'` -> `Hello Daniel`
`pynt '{greeting} {0}' Daniel greeting=hello` -> `Hello Daniel`
`pynt 'Hello {name}' -> `Hello {name}`

Why?

It is very useful for templating files in an incremental way. To use a file
you can use process subtition from bash. `pynt <(cat file) foo bar tar=zar`

License: Apache 2.0


