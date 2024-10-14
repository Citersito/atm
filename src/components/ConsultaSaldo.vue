<template>
	<div>
		<h2>Consulta de Saldo</h2>
		<p>
			Tu saldo actual es: <strong>{{ saldo }}</strong>
		</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			saldo: 1000, // Puedes conectarlo a una API real más adelante
		};
	},
};
</script>
