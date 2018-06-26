<template>
	<div class="cat-images">
		<div class="title">
			<h2>WELCOME TO CAT WORLD</h2>
		</div>
		<swiper :options="swiperOption">
		    <swiper-slide v-for="(cat, index) in cats" :key="index">
		    	<img :src="cat.url[0]">
		    </swiper-slide>
		    <div class="swiper-pagination" slot="pagination"></div>
		    <div class="swiper-button-prev" slot="button-prev"></div>
	        <div class="swiper-button-next" slot="button-next"></div>
		</swiper>
	</div>
</template>

<script>
	var parseString = require('xml2js').parseString;
	export default {
		data() {
			return {
				cats: [],
				swiperOption: {
			        pagination: {
			            el: '.swiper-pagination'
			        },
			        navigation: {
				        nextEl: '.swiper-button-next',
				        prevEl: '.swiper-button-prev',
				    },
			    }
			}
		},
		mounted() {
			this.getCatImages()
		},
		methods: {
			getCatImages() {
				axios.get('http://thecatapi.com/api/images/get?format=xml&results_per_page=20&type=gif')
				.then(response => {
					let self = this
					parseString(response.data, function (err, result) {
						self.cats = result.response.data[0].images[0].image
				    }); 
				})
				.catch(error => {
					console.log(error)
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
.title {
	text-align: center;
}
</style>