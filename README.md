# PandaCarousel #

A JS carousel that supports mouse/touch/pointers and multiple layout styles. Example: http://jsbin.com/udiniq/4

## Usage ##

### HTML ###

	<div class="pandacarousel">
		<div class="panel">
			Lorizzle ipsum bow wow wow sit amizzle.
		</div>
		<div class="panel">
			Pellentesque egizzle for sure. Sizzle erizzle.
		</div>
	</div>

### CSS ###

.pandacarousel needs a width and height set. This is left up to the implementation:

	.pandacarousel {
		width: 100%;
		height: 100%;
	}

### JS ###

PandaCarousel requires `window.requestAnimationFrame`. It's wise to polyfill this for now. See https://gist.github.com/paulirish/1579671.

Setup:

	var carousel = new PandaCarousel(document.getElementById('my-carousel'));

Change Layout:

	carousel.setLayout(1); // Set the number of columns

### Todo ###

- Currently uses top/left for position and animation because not all JS libraries can handle transforms at the moment (looking at you Leaflet). I'm thinking of making this configurable so that implementations can take advantage of the better performance (especially on Android/iOS) that transforms bring.
- Needs some decoupling so that the events and the actions are separate and individually extendable.
