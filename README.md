# PandaCarousel #

A JS carousel that supports mouse/touch/pointers and multiple layout styles. Example: http://jsbin.com/udiniq/4

## Usage ##

	<link href="PandaCarousel.css" rel="stylesheet">
	
	<!-- Each PandaCarousel needs a width and height set. The child panels will be sized up to this container -->
	<style>
	
		.pandacarousel {
			width: 100%;
			height: 100%;
		}
	
	</style>
	
	<div id="my-carousel" class="pandacarousel">
	    <div class="panel">
	        Lorizzle ipsum bow wow wow sit amizzle.
	    </div>
	    <div class="panel">
	        Pellentesque egizzle for sure. Sizzle erizzle.
	    </div>
	</div>
	
	<!-- PandaCarousel requires `window.requestAnimationFrame`. It's wise to polyfill this for now. See https://gist.github.com/paulirish/1579671. -->
	<script src="RequestAnimationFrame.js"></script> 
	<script src="PandaCarousel.js"></script>
	<script>
		
		var carousel = new PandaCarousel(document.getElementById('my-carousel'));
		carousel.setLayout(1); // Set the number of columns
		
	</script>

### Todo ###

- Currently uses top/left for position and animation because not all JS libraries can handle transforms at the moment (looking at you Leaflet). I'm thinking of making this configurable so that implementations can take advantage of the better performance (especially on Android/iOS) that transforms bring.
- Needs some decoupling so that the events and the actions are separate and individually extendable.
