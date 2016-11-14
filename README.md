
# Introduction

This is a proposal for a method to define linear and nonlinear narrative 'trails' of content using the [Web Annotation Data Model](https://www.w3.org/TR/annotation-model/).
The goal is to permit a 'Memex-like' application where users 'bookmark' content in a local database which provides a searchable index and UI allowing [Entries](Entry.md) to be combined into [Collections](Collection.md), which in turn can be referenced in each [Step](Step.md) of a greater narrative [Trail](Trail.md). The elements of this model should be sufficiently decoupled as to allow remixing [Entries](Entry.md) and [Collections](Collection.md) into other narrative [Trails](Trail.md).
The model makes use of 'meta-annotations' (annotations targeting annotations) to create the proposed structures.

## Example

![](Trails.jpg)
*Elements contained within a dotted element outline are targets of the containing element.*

This example shows: 

- One [Trail](Trail.md)

- Four [Steps](Step.md)

- Four [Collections](Collection.md)

- Twelve [Entries](Entry.md)

## Presentation

A client application would display these linked elements using whatever layout/navigation strategy it sees fit.
One example of a layout strategy might be to show each Step in a Trail as a slide in a slide presentation. The contents of each slide would be dereferenced from the Collection specified in the Step's `body`. Collections serve as a means to show one or more Entries per narrative Step. Each Step targets 0 or more subsequent Steps. These might be used to provide navigation to the next slide, or slides in the case of a nonlinear/branching presentation.
Collections and Steps can both make use of Lists or Composites to specify whether their respective targets should be displayed in a particular order.

## P2P
It is possible to store these JSON-LD annotations in a peer-to-peer content-addressable network such as Mediachain or IPFS. To do so, the `@id` property must be excluded as per [this discussion](https://github.com/ipfs/notes/issues/152#issuecomment-239153915).
Content IRIs can take the form `fs:/mc/QmContent` ('mc' for the mediachain p2p network) or `fs:/ipfs/QmContent/` ('ipfs' for the ipfs p2p network).
Once IPLD is implemented hashes will be equivalent for both networks.

## Questions

- Authors of Trails may wish to include a `viewingHint` property to give consuming clients a hint as to how to best present the content e.g. `"memex:viewingHint": "iiif"`.
- What is the correct syntax for a `dc:description` with multiple languages?

## Background and inspiration
[Wikipedia](https://en.wikipedia.org/wiki/Memex): "Memex is the name of the hypothetical proto-hypertext system that Vannevar Bush described in his 1945 The Atlantic Monthly article '[As We May Think](http://www.theatlantic.com/magazine/archive/1945/07/as-we-may-think/303881/)'. Bush describes the Memex as an electromechanical device enabling individuals to develop and read a large self-contained research library, create and follow associative trails of links and personal annotations, and recall these trails at any time to share them with other researchers. This device would closely mimic the associative processes of the human mind, but it would be gifted with permanent recollection."
