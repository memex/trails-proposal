
# Collection

Collections act as containers for one or more [Entries](Entry.md).

If [Steps](Step.md) are like slides in a Powerpoint presentation, Collections are the set of individual pieces of content ([Entries](Entry.md)) to include in them.

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
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/collections/collection1",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted entries to collection1",
  "target": "http://memex.global/entries/entry1"
}
```

### Multiple ordered targets

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/collections/collection1",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted entries to collection1",
  "target": {
    "type": "List", // show the items in this order
    "items": [
      "http://memex.global/entries/entry1",
      "http://memex.global/entries/entry2",
      "http://memex.global/entries/entry3"
    ]
  }
}
```

### Multiple unordered targets

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/collections/collection2",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Collection 2",
  "dc:description": "I link the targeted entries to collection2",
  "target": {
    "type": "Composite", // show the items in any order
    "items": [
      "http://memex.global/entries/entry4,
      "http://memex.global/entries/entry5",
      "http://memex.global/entries/entry6"
    ]
  }
}
```
