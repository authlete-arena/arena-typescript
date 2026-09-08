# PostSsfTransmitterTransmitterIdDelegateStreamStatusReadScopeConditionUnion

The condition that the access token's scope must satisfy.

The condition can range from a simple single string to more complex
structures that combine operators such as `and`, `or`, and `matches`.

When the condition is a single string, the access token must include
a scope with the specified name:

```
"scope1"
```

When the condition is a list of strings, the access token must include
all of the scopes listed:

```
["scope1", "scope2"]
```

A logical AND can be represented using a JSON object with the `and`
property with a list of conditions as its value:

```
{"and": ["scope1", "scope2"]}
```

Likewise, a logical OR can be represented using a JSON object with the
`or` property with a list of conditions as its value:

```
{"or": ["scope1", "scope2"]}
```

More complex conditions can be constructed by combining the `and` and
`or` operators:

```
{
  "or": [
    {"and": ["scope1", "scope2"]},
    {"and": ["scope3", "scope4"]}
  ]
}
```

The `matches` operator can be used to require that the access token
include a scope matching the specified regular expression:

```
{"matches": "^.*e1$"}
```

The following is a complex example that combines all of the mechanisms
introduced so far.

```
{
  "or": [
    {
      "and": ["scope1", "scope3"]
    }
  ],
  {
    "or": [
      "scope4",
      ["scope2", "scope3"],
      {
        "matches": "^.*e1$"
      }
    ]
  }
}
```

If the access token only has the scopes `scope1` and `scope2`, the
above scope condition evaluates to true and access to the resource
is granted. (This is because the regular expression `^.*e1$` in the
condition matches `scope1`, causing the overall condition to evaluate
to true.)



## Supported Types

### `boolean`

```typescript
const value: boolean = true;
```

### `string`

```typescript
const value: string = "<value>";
```

### `any[]`

```typescript
const value: any[] = [
  "<value 1>",
  "<value 2>",
  "<value 3>",
];
```

### `operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadScopeCondition`

```typescript
const value:
  operations.PostSsfTransmitterTransmitterIdDelegateStreamStatusReadScopeCondition =
    {};
```

