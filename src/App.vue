<template>
	<h1>Мини фотошоп</h1>
	<div class="content">
		<base-img :imgSrc="'https://picsum.photos/300/300'" width="500px" height="500px"/>
		<base-button :btnText="'Спрятать картинку'"/>
	</div>
</template>

<script>
import BaseImg from './components/BaseImg.vue'
import BaseButton from './components/BaseButton.vue'

export default {
	components: {
		BaseImg,
		BaseButton
	}
}
</script>

<style scoped>
	h1{
		text-align: center;
	}

	.content{
		max-width: 90rem;
		margin-inline: auto;
	}
</style>
