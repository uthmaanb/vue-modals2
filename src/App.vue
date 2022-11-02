<template>
	<h1>{{ title }}</h1>
	<p>welcome...</p>
	<teleport to=".modals" v-if="showModal">
		<Modal theme="sale" @close="toggleModal">
			<template v-slot:links>
				<a href="#">sign up now</a>
				<a href="#">more info</a>
			</template>
			<h1>Ninja Giveaway!</h1>
			<p>grab your ninja swag for half price!</p>
		</Modal>
	</teleport>
	<div v-if="showModal2">
		<Modal @close="toggleModal2">
			<template v-slot:links>
				<a href="#">sign up now</a>
				<a href="#">more info</a>
			</template>
			<h1>Ninja Giveaway!</h1>
			<p>grab your ninja swag for half price! this is number 2</p>
		</Modal>
	</div>
	<button @click.alt="toggleModal">open modal (alt)</button>
	<button @click.alt="toggleModal2">open modal2 (alt)</button>
</template>

<script>
	import Modal from "./components/Modal";

	export default {
		name: "App",
		components: { Modal },
		data() {
			return {
				title: "Vue App",
				header: "Signup for the giveaway!",
				text: "Grab your ninja swag",
				showModal: false,
				showModal2: false,
			};
		},

		methods: {
			toggleModal() {
				this.showModal = !this.showModal;
			},
			toggleModal2() {
				this.showModal2 = !this.showModal2;
			},
		},
	};
</script>

<style>
	#app, .modals {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
	h1 {
		border-bottom: 1px solid #ddd;
		display: inline-block;
		padding-bottom: 10px;
	}
</style>
