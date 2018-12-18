<template>
	<div class='list'>
		<ul v-for='(item, index) of cities' :key='index'>
			<li class='item'>{{index}}</li>
		</ul>
	</div>
</template>

<script>
export default {
	props: {
		cities: Object
	},
	name: 'CityAlphabet'
}
</script>

<style lang='stylus' scoped>
	@import '~styles/variables.styl'
	.list
		display: flex
		flex-direction: column
		justify-content: center
		position: absolute
		top: 1.58rem
		right: 0
		bottom: 0
		width: .4rem
		.item
			text-align: center
			line-height: .44rem
			color: $bgColor
</style>