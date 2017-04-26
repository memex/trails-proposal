```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "fs:/ipfs/<hash>/scene1",
  "type": "Annotation",
  "motivation": "classifying",
  "creator": "fs:/ipfs/QmParty", // COALA IP: party?
  "dc:description": "I classify the targeted media as scene 1",
  "body": "fs:/ipfs/<hash>/vocab/scene",
  "target": {
    "type": "List", // show the items in this order
    "items": [
      "fs:/ipfs/<hash>/scene1/movie.mp4",
      "fs:/ipfs/<hash>/scene1/hero.jpg",
      "fs:/ipfs/<hash>/scene1/transcript.txt"
    ]
  }
}
```