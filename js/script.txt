$(document).ready(function(){
	$('.mob_main_menu').click(function(){
		$(this).toggleClass('open_menu');
		$('.main_menu').toggleClass('show_menu')
	});
	$('.filter_open').click(function(){
		$('.filters form').slideToggle("slow");
	})
	$('.do_filtration').click(function(e){
		e.preventDefault();
		if($(window).width() < "1170")
		$('.filters form').slideToggle("slow");
		$('.item').removeClass('active1');
		$('.item').removeClass('active2');
		$('.item').removeClass('active3');
		if($('#all_datas').prop('checked') == true){
			$('.august_5').addClass('active1');
			$('.august_6').addClass('active1');
			$('.august_7').addClass('active1');
		}
		if($('#first_data').prop('checked') == true){
			$('.august_5').addClass('active1');
		}
		if($('#second_data').prop('checked') == true){
			$('.august_6').addClass('active1');
		}
		if($('#third_data').prop('checked') == true){
			$('.august_7').addClass('active1');
		}
		if($('#all_themes').prop('checked') == true){
			$('.main_scene_item').addClass('active2');
			$('.warriors_item').addClass('active2');
			$('.artisans_item').addClass('active2');
			$('.tustan_univ_item').addClass('active2');
			$('.theatre_lawn_item').addClass('active2');
			$('.chamber_scene_item').addClass('active2');
			$('.spirit_territory_item').addClass('active2');
		}
		if($('#main_scene').prop('checked') == true){
			$('.main_scene_item').addClass('active2');
		}
		if($('#warriors').prop('checked') == true){
			$('.warriors_item').addClass('active2');
		}
		if($('#artisans').prop('checked') == true){
			$('.artisans_item').addClass('active2');
		}
		if($('#tustan_univ').prop('checked') == true){
			$('.tustan_univ_item').addClass('active2');
		}
		if($('#theatre_lawn').prop('checked') == true){
			$('.theatre_lawn_item').addClass('active2');
		}
		if($('#chamber_scene').prop('checked') == true){
			$('.chamber_scene_item').addClass('active2');
		}
		if($('#spirit_territory').prop('checked') == true){
			$('.spirit_territory_item').addClass('active2');
		}
		if($('#all_locations').prop('checked') == true){
			$('.scene1').addClass('active3');
			$('.scene2').addClass('active3');
			$('.scene3').addClass('active3');
		}
		if($('#first_location').prop('checked') == true){
			$('.scene1').addClass('active3');
		}
		if($('#second_location').prop('checked') == true){
			$('.scene2').addClass('active3');
		}
		if($('#third_location').prop('checked') == true){
			$('.scene3').addClass('active3');
		}
		var calc = 0;
		$('.item').each(function() {
			if($(this).hasClass('active1')&&$(this).hasClass('active2')&&$(this).hasClass('active3')){
				$(this).css({
					display: 'block'
				})
				calc++;
			}
			else
				$(this).css({
					display: 'none'
				});
			})
			console.log(calc);
		})
	$('.clear_btn').click(function(e){
		e.preventDefault();
		$('.checkbox_block input[type="checkbox"]').prop('checked', false);
		$('h4+.checkbox_block input[type="checkbox"]').prop('checked', true);
		$('.item').css({
			display: 'block'
		})
		if($(window).width() < "1170")
		$('.filters form').slideToggle("slow");
	})
	$(window).resize(function(){
		if($(window).width() >= "1170")
		$('.filters form').css({
			display: 'block'
		})
	else
		$('.filters form').css({
			display: 'none'
		})
	})
	all_input('.data ');
	all_input('.theme ');
	all_input('.location ');

	function all_input(all){
		$(all + 'input[type="checkbox"]').change(function(){
			if($(all + 'input[type="checkbox"]').prop('checked') == true)
				$(all + 'h4+.checkbox_block input[type="checkbox"]').prop('checked', false);
		})
		$(all + 'h4+.checkbox_block input[type="checkbox"]').change(function(){
			if($(all + 'h4+.checkbox_block input[type="checkbox"]').prop('checked') == true)
				$(all + '.checkbox_block input[type="checkbox"]').prop('checked', true)
			else
				{$(all + '.checkbox_block input[type="checkbox"]').prop('checked', false);
				$(all + 'h4+.checkbox_block input[type="checkbox"]').prop('checked', true)}
	})
}

	
});