(function($) {

	var typedJs = {};

	// Main object init
	typedJs.init = function( scope ){
		this.initElement();
		this.refreshEvents();
	};

	// Will hook into Kallyas PB to refresh the element
	typedJs.refreshEvents = function(){
		var that = this;
		$(document).on('ZnNewContent', function(e){
			that.initElement( e.content );
		});
	};

	// Will initialise the animated text element
	typedJs.initElement = function( scope ){
		var $el = scope ? scope.find('.zn-dynamic-animated-typed') : $(".zn-dynamic-animated-typed");

		if( $el.length === 0 ){
			return;
		}

		$el.each(function(){
			var $this = $(this),
				$stringContainer = $this.prev('.zn_animated_dynamic_texts'),
				config =$stringContainer.data('config'),
				defaults = {
					stringsElement: $stringContainer
				},
				config = $.extend(defaults, config);


			//if($hideCursorTime.data('hidecursor'))
			//$stringContainer = $this.prev('.zn_animated_dynamic_texts'),

			var timeCursor = $stringContainer.data('hidecursor');
			if(timeCursor){
				setTimeout(function(){
					$this.next('.typed-cursor').hide();
				}, timeCursor);
			}

			//init the animated text
			$this.typed(config);

		});
	};

	typedJs.init();

})(jQuery);