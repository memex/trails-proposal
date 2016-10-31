
# Step

Steps describe individual parts of a [Trail](Trail.md), linking one [Collection](Collection.md) to zero or more subsequent Steps.

Think of Steps as like slides in a Powerpoint presentation or segments of a video. Unlike a 'linear' presentation however, they can be followed by n Steps, allowing 'non linear' or 'branching' presentations. 

Subsequent Steps can be defined in ordered Lists or unordered Composites. This could serve as a hint to a consuming application as to how to display them.

### Motivation 
linking

### Body
[Collection](Collection.md)

### Target
- none
- [Step](Step.md)
- List of zero or more [Steps](Step.md)
- Composite of zero or more [Steps](Step.md)

## Examples

### Single target (linear)

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/steps/1",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Step 1",
  "dc:description": "I'm the first part of trail1 linking collection 1 to step 2",
  "body": "http://memex.global/collections/1",
  "target": "http://memex.global/steps/2" // linear
}
```

### Multiple ordered targets (non linear)
```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/2",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Step 2",
  "dc:description": "I'm the second part of trail1 linking collection2 to step 3 and step 4",
  "body": "http://memex.global/collections/2",
  "target": {
    "type": "List", // specific order
    "items": [
      "http://memex.global/steps/3",
      "http://memex.global/steps/4"
    ]
  }
}
```

### Multiple unordered targets (non linear)
```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/steps/2",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Step 2",
  "dc:description": "I'm the second part of trail1 linking collection2 to step 3 and step 4",
  "body": "http://memex.global/collections/2",
  "target": {
    "type": "Composite", // no specific order
    "items": [
      "http://memex.global/steps/3",
      "http://memex.global/steps/4"
    ]
  }
}
```