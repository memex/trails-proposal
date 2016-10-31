
# Entry

Entries bookmark or describe a resource or [fragment](https://www.w3.org/TR/annotation-model/#fragment-selector) of a resource.

These are the basic units of a 'memex-like' application. They are records of items of interest that a user may wish to assemble into a narrative [Trail](Trail.md).

### Motivation
- bookmarking
- describing

### Body
- none
- Resource
- Choice

### Target
- Resource
- Fragment

## Examples

### Bookmarking, no body

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/userid/entries/1",
  "type": "Annotation",
  "motivation": "bookmarking",
  "target": "fs:/mc/QmContent#t=30,60"
}
```

### Describing, single body

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/userid/entries/1",
  "type": "Annotation",
  "motivation": "describing",
  "body": "fs:/mc/QmContent",
  "target": "fs:/mc/QmContent#t=30,60"
}
```

### Describing, choice of body

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/userid/entries/1",
  "type": "Annotation",
  "motivation": "describing",
  "body": {
    "type": "Choice", // multiple languages
    "items": [
      {
          "type": "TextualBody",
          "value": "Awesome scene",
          "format": "text/html",
          "language" : "en"
      },
      {
          "type": "TextualBody",
          "value": "Fantastische Szene",
          "format": "text/html",
          "language" : "de"
      }
    ]
  },
  "target": "fs:/mc/QmContent#t=30,60"
}
```