<template>
	<div>
		<p> Este es mi componente </p>
		<hr>
		<p>El link enviado por propiedad: <a :href="url" target="_blank">pinche aqui</a></p>
		<hr>
		<p>El texto comienza aqui: {{ text }}</p>
		<button @click="emitBtn()">{{ btntext }}</button>
	</div>
</template>

<script>
export default {
    props: {
			text: { type: String },
			btntext: { type: String, default: "Emitir"},
			url: { type: String} 
    },
    data() {
			return {
				number: 15
			}
    },
		mounted() {
			this.$EvenBus
		},
    methods: {
			emitBtn() {
				this.$emit('click:btn', this.number);
			}
    },
}
</script>