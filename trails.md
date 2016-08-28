
Here we have: 

- Three **entry** objects describing .mp4, .jpg, and .txt files defined as annotations with the `describing` motivation or `bookmarking` motivation, in which case a `body` is not required.

- Two **collection**s defined as annotations with a `linking` motivation, each targeting a List (ordered) or Composite (unordered) set of **entry** objects.

- One **trail** defined as an annotation with a `linking` motivation, targeting a set of **step**s. 

- Two **step**s defined as annotations with a `linking` motivation, linking a **collection** to one or more **collection**s.

A client application would display this media using whatever layout strategy it sees fit - perhaps a custom `mx:layoutStrategy` property could be used?

# Entries

## Entry 1
fs:/ipfs/QmContent/entry1

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "entry",
  "motivation": "describing", // or bookmarking (body not required)
  "body": {
    "type": "Choice",
    "items": [
      {
          "type": "TextualBody",
          "value": "Awesome movie",
          "format": "text/html",
          "language" : "en"
      },
      {
          "type": "TextualBody",
          "value": "děsivý film",
          "format": "text/html",
          "language" : "cs"
      },
      {
          "type": "TextualBody",
          "value": "Toller Film",
          "format": "text/html",
          "language" : "de"
      }
    ]
  },
  "target": "fs:/ipfs/QmContent/movie.mp4"
}
```

## Entry 2
fs:/ipfs/QmContent/entry2

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "entry",
  "motivation": "describing", // or bookmarking (body not required)
  "body": {
    "type": "Choice",
    "items": [
      {
          "type": "TextualBody",
          "value": "Awesome movie",
          "format": "text/html",
          "language" : "en"
      },
      {
          "type": "TextualBody",
          "value": "děsivý obrázek",
          "format": "text/html",
          "language" : "cs"
      },
      {
          "type": "TextualBody",
          "value": "Super Bild",
          "format": "text/html",
          "language" : "de"
      }
    ]
  },
  "target": "fs:/ipfs/QmContent/image.jpg"
}
```

## Entry 3
fs:/ipfs/QmContent/entry3

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "entry",
  "motivation": "describing", // or bookmarking (body not required)
  "body": {
    "type": "Choice",
    "items": [
      {
          "type": "TextualBody",
          "value": "Awesome text",
          "format": "text/html",
          "language" : "en"
      },
      {
          "type": "TextualBody",
          "value": "děsivý textu",
          "format": "text/html",
          "language" : "cs"
      },
      {
          "type": "TextualBody",
          "value": "ehrfürchtig Text",
          "format": "text/html",
          "language" : "de"
      }
    ]
  },
  "target": "fs:/ipfs/QmContent/text.txt"
}
```

# Collections

## Collection 1
fs:/ipfs/QmContent/collection1

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "collection",
  "motivation": "linking",
  "dc:title": "Collection 1",
  "dc:description": "I link the targeted media as collection1",
  "target": {
    "type": "List", // show the items in this order
    "items": [
      "fs:/ipfs/QmContent/collection1/entry1",
      "fs:/ipfs/QmContent/collection1/entry2",
      "fs:/ipfs/QmContent/collection1/entry3"
    ]
  }
}
```

## Collection 2
fs:/ipfs/QmContent/collection2

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "collection",
  "motivation": "linking",
  "dc:title": "Collection 2",
  "dc:description": "I link the targeted media as collection2",
  "target": {
    "type": "Composite", // show the items in any order
    "items": [
      "fs:/ipfs/QmContent/collection2/entry4,
      "fs:/ipfs/QmContent/collection2/entry5",
      "fs:/ipfs/QmContent/collection2/entry6"
    ]
  }
}
```

# Trails

## Trail 1
fs:/ipfs/QmContent/trail1

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "trail",
  "motivation": "linking",
  "dc:title": "Trail 1",
  "dc:description": "I link the targeted steps as trail1",
  "target": {
    "type": "List", // specific order
    "items": [
      "fs:/ipfs/QmContent/step1",
      "fs:/ipfs/QmContent/step2"
    ]
  }
}
```

# Steps

## Step 1
fs:/ipfs/QmContent/step1

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "step",
  "motivation": "linking",
  "dc:description": "I'm the first part of a trail linking collection1 to step2",
  "body": "fs:/ipfs/QmContent/collection1",
  "target": "fs:/ipfs/QmContent/step2" // linear
}
```

## Step 2
fs:/ipfs/QmContent/step2

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "fs:/ipfs/QmContent/vocab/memex.jsonld"],
  "type": "Annotation",
  "mx:type": "step",
  "motivation": "linking",
  "dc:description": "I'm the second part of a trail linking collection2 to collection3 and collection4",
  "body": "fs:/ipfs/QmContent/collection2",
  "target": {
    "type": "Composite", // no specific order - nonlinear
    "items": [
      "fs:/ipfs/QmContent/collection3",
      "fs:/ipfs/QmContent/collection4"
    ]
  }
}
```