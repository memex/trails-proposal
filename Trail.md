
# Trail

Trails act as containers for one or more [Steps](Step.md).

Steps determine their linking order via the `target` property. However, it is useful to know which trail(s) a given Step belongs to.

It is also necessary to know which Step is the first in any given Trail.

A Trail's target is an ordered list of one or more Steps. The first Step represents the entry point for the Trail. The following Steps can be in any order - likely the order in which they were added to the Trail.

### Motivation 
classifying

### Body
//memex.global/classes/trail

### Target
- [Step](Step.md)
- List of one or more [Steps](Step.md)

## Examples

```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "//memex.global/users/userid/trails/1",
  "type": "Annotation",
  "motivation": "classifying",
  "body": "//memex.global/classes/trail",
  "dc:title": "Trail 1",
  "dc:description": "I classify the targeted steps as part of trail 1",
  "target": {
    "type": "List",
    "items": [
      "//memex.global/users/userid/steps/1",
      "//memex.global/users/userid/steps/2",
      "//memex.global/users/userid/steps/3",
      "//memex.global/users/userid/steps/4"
    ]
  }
}