<template>
	<v-app>
		<v-container fluid>
			<NavBar />
			<router-view />
		</v-container>
	</v-app>
</template>

<script>
import NavBar from '@/components/NavBar'

export default {
	name: 'App',
	components: {
		NavBar
	}
}
</script>
