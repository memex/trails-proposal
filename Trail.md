
# Trail

Trails act as containers for one or more [Steps](Step.md).

Think of a Trail as like a Powerpoint or video file. It contains a sequence of media that can be presented accordingly by a consuming application.


### Motivation 
linking

### Body
none

### Target
- [Step](Step.md)
- List of one or more [Steps](Step.md)

## Examples

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "http://memex.global/trails/1",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Trail 1",
  "dc:description": "I link the targeted steps to trail 1",
  "target": {
    "type": "List",
    "items": [
      "http://memex.global/steps/1",
      "http://memex.global/steps/2",
      "http://memex.global/steps/3",
      "http://memex.global/steps/4"
    ]
  }
}