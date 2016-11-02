
# Collection

Collections act as containers for one or more [Entries](Entry.md).

If [Steps](Step.md) are like slides in a Powerpoint presentation, Collections are the set of individual pieces of content ([Entries](Entry.md)) to include in them.

### Motivation 
classifying

### Body
memex.global/classes/collection

### Target
- [Entry](Entry.md)
- List of one or more [Entries](Entry.md)
- Composite of one or more [Entries](Entry.md)

## Examples

### Single target

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "memex.global/users/userid/collections/1",
  "type": "Annotation",
  "motivation": "classifying",
  "body": "memex.global/classes/collection",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted entries to collection 1",
  "target": "memex.global/users/userid/entries/1"
}
```

### Multiple ordered targets

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "memex.global/users/userid/collections/1",
  "type": "Annotation",
  "motivation": "classifying",
  "body": "memex.global/classes/collection",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted entries to collection 1",
  "target": {
    "type": "List", // show the items in this order
    "items": [
      "memex.global/users/userid/entries/1",
      "memex.global/users/userid/entries/2",
      "memex.global/users/userid/entries/3"
    ]
  }
}
```

### Multiple unordered targets

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "memex.global/users/userid/collections/2",
  "type": "Annotation",
  "motivation": "classifying",
  "body": "memex.global/classes/collection",
  "dc:title": "Collection 2",
  "dc:description": "I link the targeted entries to collection 2",
  "target": {
    "type": "Composite", // show the items in any order
    "items": [
      "memex.global/users/userid/entries/4,
      "memex.global/users/userid/entries/5",
      "memex.global/users/userid/entries/6"
    ]
  }
}
```
