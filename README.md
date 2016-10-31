
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

- Three [Entries](Entry.md) describing [fragments](https://www.w3.org/TR/annotation-model/#fragment-selector) of .mp4, .jpg, and .txt files.
There are 12 [Entries](Entry.md) in total, but for the sake of keeping the example concise only 3 are described. 

## Presentation

A client application would display these linked elements using whatever layout/navigation strategy it sees fit.
One example of a layout strategy might be to show each Step in a Trail as a slide in a slide presentation. The contents of each slide would be dereferenced from the Collection specified in the Step's `body`. Collections serve as a means to show one or more Entries per narrative Step. Each Step targets 0 or more subsequent Steps. These might be used to provide navigation to the next slide, or slides in the case of a nonlinear/branching presentation.
Collections and Steps can both make use of Lists or Composites to specify whether their respective targets should be displayed in a particular order.

## IPFS
It is possible to store these JSON-LD annotations in a peer-to-peer content-addressable network such as Mediachain or IPFS. To do so, the `id` property must be excluded as per [this discussion](https://github.com/ipfs/notes/issues/152#issuecomment-239153915).
Content IRIs can take the form `fs:/mc/QmContent` ('mc' for the mediachain p2p network) or `fs:/ipfs/QmContent/` ('ipfs' for the ipfs p2p network).
Once IPLD is implemented hashes will be equivalent for both networks.

## Questions

- Would an `mx:layoutStrategy` property be useful to give consuming clients a hint as to how to best present a Trail?
- What is the correct syntax for a `dc:description` with multiple languages?
- When a `body` is not provided in the case of Trails and Collections, is it correct to say that the targeted annotations are _linked_ to the Trail/Collection?