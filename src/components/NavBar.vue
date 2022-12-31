<template>
	<v-app-bar
		color="orange"
		dark
	>
		<v-spacer></v-spacer>
		<v-btn outlined class="ml-3">
			<router-link to="/">Main</router-link>
		</v-btn>
		<v-btn outlined class="ml-3">
			<router-link to="/photos/">Photos</router-link>
		</v-btn>
	</v-app-bar>
</template>

<script>
export default {
	name: 'NavBar'
}
</script>
