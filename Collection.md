
# Collection

Collections act as containers for one or more [Entries](Entry.md).

If [Steps](Step.md) are slides in a Powerpoint presentation, Collections are the 'canvas' onto which the individual pieces of content ([Entries](Entry.md)) are drawn.

### Motivation 
linking

### Body
none

### Target
- [Entry](Entry.md)
- List of one or more [Entries](Entry.md)
- Composite of one or more [Entries](Entry.md)

## Examples

### Single target

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/collection1",
  "type": "Annotation",
  "mx:type": "collection",
  "motivation": "linking",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted entries to collection1",
  "target": "http://example.org/entry1"
}
```

### Multiple ordered targets

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/collection1",
  "type": "Annotation",
  "mx:type": "collection",
  "motivation": "linking",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted entries to collection1",
  "target": {
    "type": "List", // show the items in this order
    "items": [
      "http://example.org/entry1",
      "http://example.org/entry2",
      "http://example.org/entry3"
    ]
  }
}
```

### Multiple unordered targets

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/collection2",
  "type": "Annotation",
  "mx:type": "collection",
  "motivation": "linking",
  "dc:title": "Collection 2",
  "dc:description": "I link the targeted entries to collection2",
  "target": {
    "type": "Composite", // show the items in any order
    "items": [
      "http://example.org/entry4,
      "http://example.org/entry5",
      "http://example.org/entry6"
    ]
  }
}
```
