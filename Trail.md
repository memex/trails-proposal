
# Trail

Trails act as containers for one or more [Steps](Step.md).

Steps determine their linking order via the `target` property. However, it is useful to know which trail a specific Step belongs to.

It is also necessary to know which Step is the first in any given Trail.

A Trail's target is an ordered list of one or more Steps. The first Step represents the entry point for the Trail. The following Steps can be in any order - likely the order in which they were added to the Trail.

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