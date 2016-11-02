
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
  "id": "//memex.global/userid/trails/1",
  "type": "Annotation",
  "motivation": "linking",
  "dc:title": "Trail 1",
  "dc:description": "I link the targeted steps to trail 1",
  "target": {
    "type": "List",
    "items": [
      "//memex.global/userid/steps/1",
      "//memex.global/userid/steps/2",
      "//memex.global/userid/steps/3",
      "//memex.global/userid/steps/4"
    ]
  }
}