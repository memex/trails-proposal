
# Trail

## Description
Trails act as containers for 1 or more [Steps](Step.md).

Think of a Trail as like a Powerpoint presentation file, or a video file. It contains a sequence of media that can be presented accordingly by a consuming application.

## Motivation 
linking

## Body
none

## Targets
A Resource, or [List](https://www.w3.org/TR/annotation-model/#sets-of-bodies-and-targets) of 1 or more [Steps](Step.md). 

## Examples

```
{
  "@context": ["http://www.w3.org/ns/anno.jsonld", "http://example.org/vocab/memex.jsonld"],
  "id": "http://example.org/trail1",
  "type": "Annotation",
  "mx:type": "trail",
  "motivation": "linking",
  "dc:title": "Trail 1",
  "dc:description": "I link the targeted steps to trail1",
  "target": {
    "type": "List", // use List for specific order, Composite for any order
    "items": [
      "http://example.org/step1",
      "http://example.org/step2",
      "http://example.org/step3",
      "http://example.org/step4"
    ]
  }
}