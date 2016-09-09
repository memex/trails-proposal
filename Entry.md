
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
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/entry1",
  "type": "Annotation",
  "mx:type": "entry",
  "motivation": "bookmarking",
  "target": "http://example.org/movie.mp4#t=30,60"
}
```

### Describing, single body

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/entry1",
  "type": "Annotation",
  "mx:type": "entry",
  "motivation": "describing",
  "body": "http://example.com/body1",
  "target": "http://example.org/movie.mp4#t=30,60"
}
```

### Describing, choice of body

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/entry1",
  "type": "Annotation",
  "mx:type": "entry",
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
  "target": "http://example.org/movie.mp4#t=30,60"
}
```