```
{
  "@context": "http://www.w3.org/ns/anno.jsonld",
  "id": "fs:/ipfs/QmContent/scene1",
  "type": "Annotation",
  "motivation": "classifying",
  "creator": "fs:/ipfs/QmParty", // COALA IP: party?
  "dc:description": "I classify the targeted media as scene 1",
  "body": "fs:/ipfs/QmContent/vocab/scene",
  "target": {
    "type": "List", // show the items in this order
    "items": [
      "fs:/ipfs/QmContent/scene1/movie.mp4",
      "fs:/ipfs/QmContent/scene1/hero.jpg",
      "fs:/ipfs/QmContent/scene1/transcript.txt"
    ]
  }
}
```