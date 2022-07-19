# Musings on Data Shapes

Collection of examples of data we'd like to be able to write.

## Enums

Any finite collection of values can be listed as an enum, which is a form of tagged union (how, exactly, tbd).

```
enum Option<T>
{
    Some(T t),
    None
}
```

```
enum HttpCodes
{
    Continue = 100,
    Ok = 200,
    BadRequest = 400,
    // etc
}
```

```
enum LspMethod
{
    // Expands the nested values into this one? Or just truly nested?
    TextDocument: TextDocumentMethods,
}

enum TextDocumentMethods
{
    // Magic expands the base value to be prefixed with 'textDocument/'
    const Value: string = "textDocument/\(SourceValue)";

    Definition = "definition",
    TypeDefinition = "typeDefinition",
    Implementation = "implementation",
    // etc
}
```
