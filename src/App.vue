<template>
  <div id="app">
		<router-view></router-view>
  </div>
</template>

<script>

export default {
  components: {},
	mounted() {
		this.$router.replace({ name: "Login" });
	},
	
}
</script>

<style src="./main.css">
</style>
