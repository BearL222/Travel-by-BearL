<template>
  <div class='icons'>
    <swiper>
    	<swiper-slide v-for='(page, index) of pages' :key='index'>
				<div class='icon' v-for="item of page" :key='item.id'>
		      <div class='icon-img'>
		        <img class='icon-img-content' :src='item.imgUrl'/>
		        <p class='icon-desc'>{{item.desc}}</p>
		      </div>
		    </div>
    	</swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
	name: 'HomeIcons',
	data () {
		return {
			iconList: [{
				id: '0001',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon1'
			}, {
				id: '0002',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon2'
			}, {
				id: '0003',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon3'
			}, {
				id: '0004',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon4'
			}, {
				id: '0005',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon5'
			}, {
				id: '0006',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon6'
			}, {
				id: '0007',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon7'
			}, {
				id: '0008',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon8'
			}, {
				id: '0009',
				imgUrl: 'https://github.com/BearL222/Warehouse/raw/master/images/YelpForMovies/baseline-edit-black-18/2x/baseline_edit_black_18dp.png',
				desc: 'Icon9'
			}]
		}
	},
	computed: {
		pages () {
			const pages = []
			this.iconList.forEach((item, index) => {
				const page = Math.floor(index / 8)
				if(!pages[page]) {
					pages[page] = []
				}
				pages[page].push(item)
			})
			return pages
		}
	}
}
</script>

<style lang='stylus' scoped>
  @import '~styles/variables.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
  	height: 0
  	padding-bottom: 50%
  .icon
  	position: relative
  	overflow: hidden
  	float: left
  	height: 0
  	width: 25%
  	padding-bottom: 25%
		.icon-img
			position: absolute
			top: 0
			left: 0
			right: 0
			bottom: .44rem
			box-sizing: border-box
			padding: .1rem
			.icon-img-content
				display: block
				height: 100%
		.icon-desc
			position: absolute
			left: 0
			right: 0
			bottom: 0
			height: .44rem
			line-height: .44rem
			text-align: center
			color: $darkTextColor
			ellipsis()
			
</style>