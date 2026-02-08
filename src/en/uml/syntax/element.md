# Elements

Elements are visible or interactive objects on the event page. They are defined as:

```js
type(attr1: value1, attr2: value2, ...) { Hello! }
```

Here `type` is the element type; `attrN` and `valueN` are attribute names and values. Attributes depend on the element type; required ones are noted in each element’s docs.

The `id` attribute is optional and shared by all elements. After an element is defined, its `id` maps to a `Rect` variable representing the element’s draw bounds.

The optional `{ Hello }` block is text content. It only applies to the `p` (paragraph) element.
