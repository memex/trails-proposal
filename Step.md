
# Step

## Description
Steps describe individual parts of a [Trail](Trail.md), linking 1 [Collection](Collection.md) to 0 or more Steps.

Think of Steps as like slides in a Powerpoint presentation or segments of a video. Unlike a 'linear' presentation however, they can be followed by n Steps, allowing 'non linear' or 'branching' presentations. 

Subsequent Steps can be defined in ordered Lists or unordered Composites. This could serve as a hint to a consuming application as to how to display these Steps.

## Motivation 
linking

## Body
[Collection](Collection.md) Resource

## Targets
A Resource, [List, or Composite](https://www.w3.org/TR/annotation-model/#sets-of-bodies-and-targets) of 1 or more Steps. 

## Examples

### Single target (linear)

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/step1",
  "type": "Annotation",
  "mx:type": "step",
  "motivation": "linking",
  "dc:title": "Step 1",
  "dc:description": "I'm the first part of trail1 linking collection 1 to step2",
  "body": "http://example.org/collection1",
  "target": "http://example.org/step2" // linear
}
```

### Multiple ordered targets (non linear)
```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/step2",
  "type": "Annotation",
  "mx:type": "step",
  "motivation": "linking",
  "dc:title": "Step 2",
  "dc:description": "I'm the second part of trail1 linking collection2 to step3 and step4",
  "body": "http://example.org/collection2",
  "target": {
    "type": "List", // specific order
    "items": [
      "http://example.org/step3",
      "http://example.org/step4"
    ]
  }
}
```

### Multiple unordered targets (non linear)
```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/step2",
  "type": "Annotation",
  "mx:type": "step",
  "motivation": "linking",
  "dc:title": "Step 2",
  "dc:description": "I'm the second part of trail1 linking collection2 to step3 and step4",
  "body": "http://example.org/collection2",
  "target": {
    "type": "Composite", // no specific order
    "items": [
      "http://example.org/step3",
      "http://example.org/step4"
    ]
  }
}
```