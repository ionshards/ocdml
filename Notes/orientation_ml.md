#Orientation/Shape/Configuration Markup Language

##Project Goal

Develop a markup language that can be used to annotate the conventional configurations and orientations of spatial entities.
 
The application would be in developing an algorithm that could take a list of objects and return their conventional orientations.  Also, given a combination of two objects, it could return their conventional configuration.

##Relevant literature and previous work

* [WordsEye](http://lucky.cs.columbia.edu:2001)
    * Coyne, O. Rambow, J. Hirschberg, and R. Sproat. Frame Semantics in Text-to-Scene Generation. In Proceedings of the KES'10 workshop on 3D Visualisation of Natural Language, 2010.
    * Coyne and R. Sproat. WordsEye: An automatic text-to-scene conversion system. In SIGGRAPH Proceedings of the Annual Conference on Computer Graphics, 2001.
    
* ISO-Space
    * We can inherit the `Spatial_Entity` tag from ISO-Space, though we will probably want to extend its attributes
    
* [Geons](http://en.wikipedia.org/wiki/Geon_\(psychology\))

* [Affordances](http://en.wikipedia.org/wiki/Affordance)
    * Donald A. Norman, The Design of Everyday Things


##Possible data sources

* WordNet

* Scene descriptions
    * [ImageCLEF IAPR TC-12 Benchmark](http://imageclef.org/photodata): natural language descriptions of still natural images

* Newswire texts

##Notes from talking to James

How are books configured when they are put on a shelf?

What if we take the shelf to be some sort of cube-like entity that has the following surfaces?

* `FRONT`
    * The open surface whose outside faces the front
* `BACK`
    * A closed or open surface whose outside faces the back
* `TOP`
    * A closed or open surface whose outside faces up
* `BOTTOM`
    * A closed surfaced whose outsides faces down
    * the “shelf”
* `RIGHT`
    * A closed or open surface whose outside faces right
* `LEFT`
    * A closed or open surface whose outside faces left


What if we take a book (at least, when closed and when its textual content is encoded in a writing system whose directionality is horizontal from left-to-right) to be cube-like with the following surfaces

* `FRONT`
    * A closed surface
    * The “front cover”
* `BACK`
    * A closed surface
    * The “back cover”
* `TOP`
    * An open? or closed? surface whose outside faces up
    * The “top edges of the pages”
* `BOTTOM`
    * An open? or closed? surface whose outside faces down
    * The “bottom edges of the pages”
* `LEFT`
    * A closed surface whose outside faces left
    * The “binding”
* `RIGHT`
    * An open? or closed? surface whose outside faces right
    * The “right edges of the pages”

There seems to be a conventional configuration between books and shelves.  If we take a book as a figure and a shelf as a ground, then we can map create a mapping from each surface of the book to the shelf to define a configuration which would encode the orientation of the figure relative to the ground.

* The `LEFT` of the book is aligned with the `FRONT` of the bookcase
* The `RIGHT` of the book is aligned with the `BACK` of the bookcase
* The `FRONT` of the book is aligned with the `RIGHT` of the bookcase
* The `BACK` of the book is aligned with the `LEFT` of the bookcase
* The `TOP` of the book is aligned with the `TOP` of the bookcase
* The `BOTTOM` of the book is aligned with the `BOTTOM` of the bookcase

###Initial Thoughs on an Inventory of Geometric Primitives

####0-D
* `POINT`
    * 0 edges
    * 1 point
    * 0 surfaces
    
####1-D
* `LINE-SEGMENT`
    * 1 edge
    * 2 points
    * 0 surfaces
    
####2-D
* `N-GON`
    * N edges
    * N points
    * 2 surfaces

* `DISC`
    * 1 edge
    * 0 points
    * 2 surfaces

* `ANNULUS`
    * 2 edges
    * 0 points
    * 2 surfaces


####3-D
* `CLOSED CUBOID`
    * 12 surfaces
    * 8 points
    * 12 edges
    
* `CUBE OPEN-1`
    * 10 surfaces
    * 8 points
    * 12 edges
        
* `CLOSED CYLINDER`
    * 3 surfaces
    * 0 points
    * 2 edges

* `OPEN CYLINER`
    * Same as closed cylinder but with different surface topology
        
* `TORUS`
    * 1 surface
    * 0 points
    * 0 edges

* `SPHERE`
    * 1 surface
    * 0 points
    * 0 edges


* `CLOSED CONE`
    * 2 surfaces
    * 1 point
    * 1 edge
    
* `OPEN CONE`
    * 2 surfaces
    * 1 point
    * 1 edge

* `CLOSED PYRAMID` (n-hedron with n-gon base connected to an apex point)
    * N+1 surfaces
    * N+1 points
    * N edges

###Inventories of N-D:M-D relations
#### 1-D:1-D
* `POINT:POINT`
    * point of light on a dot of ink
    
#### 3-D:3-D
* `TOROID:CYLINDROID`
    * ring on a finger, beer-cozy on a beer can
    * pull-tab on an un-opened beer can 
    * a life-saver on the wall of a cylindrical structure?
    * o-ring inside a pipe

* `CUBOID:CUBOID`
    * book on a bookshelf
    * ice cube in an ice-tray
    * 

* How do humans stand?
    * Humans stand erect on two feet (this is probably the default orientation for a human)
    * *standing* is possibly a configuration as opposed to *sitting* or *lying prone* etc.
    * The kinds of things that *standing* selects for are things with an intrinsic vertical axis, and the bottom surface of the `figure` is connected to a `ground` surface/edge.

* How do dogs stand?
    * Dogs stand "on all fours"

* books

humans

tables

doors

tables

WordsEye

Literature:

    Frame Semantics in Text-to-Scene Generation
    Columbia University
    Bob Coyne, Owen Rambow, Julia Hirschberb, and Richard Sproat

facing
overlooking