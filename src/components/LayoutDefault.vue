<template>
	<div class="container">
		<div id="barralateral">
			<BarraLateral />
		</div>
		<main class="content">
			<ContenidoPrincipal />
		</main>
	</div>
</template>

<script>
import BarraLateral from "./BarraLateral.vue";
import ContenidoPrincipal from "./ContenidoPrincipal.vue";
export default {
	components: {
		BarraLateral,
		ContenidoPrincipal,
	},
};
</script>

<style></style>
