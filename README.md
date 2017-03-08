
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

"There is a new profession of trail blazers, those who find delight in the task of establishing useful trails through the enormous mass of the common record." -- Vannevar Bush (1945)

[Wikipedia](https://en.wikipedia.org/wiki/Memex): "Memex is the name of the hypothetical proto-hypertext system that Vannevar Bush described in his 1945 The Atlantic Monthly article '[As We May Think](http://www.theatlantic.com/magazine/archive/1945/07/as-we-may-think/303881/)'. Bush describes the Memex as an electromechanical device enabling individuals to develop and read a large self-contained research library, create and follow associative trails of links and personal annotations, and recall these trails at any time to share them with other researchers. This device would closely mimic the associative processes of the human mind, but it would be gifted with permanent recollection."

Bush: "With one item in its grasp, [the human mind] snaps instantly to the next that is suggested by the association of thoughts, in accordance with some intricate web of trails carried by the cells of the brain. It has other characteristics, of course; trails that are not frequently followed are prone to fade, items are not fully permanent, memory is transitory. Yet the speed of action, the intricacy of trails, the detail of mental pictures, is awe-inspiring beyond all else in nature. Man cannot hope fully to duplicate this mental process artificially, but he certainly ought to be able to learn from it." (As We May Think, Section 6)

"The basic idea of [associative indexing] is a provision whereby any item may be caused at will to select immediately and automatically another. This is the essential feature of the memex. The process of tying two items together is the important thing...The user taps a single key, and the items are permanently joined...When numerous items have been thus joined together to form a trail, they can be reviewed in turn, rapidly or slowly, by deflecting a lever like that used for turning the pages of a book. It is exactly as though the physical items had been gathered together from widely separated sources and bound together to form a new book. It is more than this, for any item can be joined into numerous trails." (As We May Think, Section 7)

USECASE#1 (Bush): "The owner of the memex, let us say, is interested in the origin and properties of the bow and arrow. Specifically he is studying why the short Turkish bow was apparently superior to the English long bow in the skirmishes of the Crusades. He has dozens of possibly pertinent books and articles in his memex. First he runs through an encyclopedia, finds an interesting but sketchy article, leaves it projected. Next, in a history, he finds another pertinent item, and ties the two together. Thus he goes, building a trail of many items. Occasionally he inserts a comment of his own, either linking it into the main trail or joining it by a side trail to a particular item. When it becomes evident that the elastic properties of available materials had a great deal to do with the bow, he branches off on a side trail which takes him through textbooks on elasticity and tables of physical constants. He inserts a page of longhand analysis of his own. Thus he builds a trail of his interest through the maze of materials available to him." (As We May Think, Section 7)

USECASE#2 (Bush): "...And his trails do not fade. Several years later, his talk with a friend turns to the queer ways in which a people resist innovations, even of vital interest. He has an example, in the fact that the outraged Europeans still failed to adopt the Turkish bow. In fact he has a trail on it. A touch brings up the code book. Tapping a few keys projects the head of the trail. A lever runs through it at will, stopping at interesting items, going off on side excursions. It is an interesting trail, pertinent to the discussion. So he sets a reproducer in action, photographs the whole trail out, and passes it to his friend for insertion in his own memex, there to be linked into the more general trail." (As We May Think, Section 7)
