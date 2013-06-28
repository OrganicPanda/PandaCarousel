PandaCarousel
=============

A JS carousel that supports mouse/touch/pointers and multiple layout styles. Example: http://jsbin.com/udiniq/4

Todo
----

- Currently uses top/left for position and animation because not all JS libraries can handle transforms at the moment (looking at you Leaflet). I'm thinking of making this configurable so that implementations can take advantage of the better performance (especially on Android/iOS) that transforms bring.
- Needs some decoupling so that the events and the actions are separate and individually extendable.
