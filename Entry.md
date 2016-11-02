
# Entry

Entries bookmark or describe a resource or [fragment](https://www.w3.org/TR/annotation-model/#fragment-selector) of a resource.

These are the basic units of a 'memex-like' application. They are records of items of interest that a user may wish to assemble into a narrative [Trail](Trail.md).

An Entry could target a whole file of any type, or select a fragment within it using a [fragment selector](https://www.w3.org/TR/annotation-model/#fragment-selector).

Examples of selectors:

- movie.mp4#t=30,60
- image.jpg#xywh=100,100,300,300
- text.txt#char=0,100

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
  "id": "//memex.global/users/userid/entries/1",
  "type": "Annotation",
  "motivation": "bookmarking",
  "target": "fs:/mc/QmContent#t=30,60"
}
```

### Describing, single body

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "//memex.global/users/userid/entries/1",
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
  "id": "//memex.global/users/userid/entries/1",
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