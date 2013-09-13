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

Setup:

	var carousels = document.querySelectorAll('.pandacarousel');
	var Carousels = [];
	
	for (var c = 0, cl = carousels.length; c < cl; c++) {
	
		Carousels.push(new PandaCarousel(carousels[c]));
	
	}

Change Layout:

	var single = document.querySelector('.single-layout');
	var double = document.querySelector('.double-layout');
	var triple = document.querySelector('.triple-layout');
	
	var setLayout = function(childrenPerPage) {
	
		for (var c = 0, cl = Carousels.length; c < cl; c++) {
		  
			Carousels[c].setLayout(childrenPerPage);
		
		}
	
	};
	
	single.addEventListener('click', function() { setLayout(1); }, false);
	double.addEventListener('click', function() { setLayout(2); }, false);
	triple.addEventListener('click', function() { setLayout(3); }, false);


### Todo ###

- Currently uses top/left for position and animation because not all JS libraries can handle transforms at the moment (looking at you Leaflet). I'm thinking of making this configurable so that implementations can take advantage of the better performance (especially on Android/iOS) that transforms bring.
- Needs some decoupling so that the events and the actions are separate and individually extendable.
