
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
  "id": "http://memex.global/trails/trail1",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Trail 1",
  "dc:description": "I link the targeted steps to trail1",
  "target": {
    "type": "List",
    "items": [
      "http://memex.global/steps/step1",
      "http://memex.global/steps/step2",
      "http://memex.global/steps/step3",
      "http://memex.global/steps/step4"
    ]
  }
}