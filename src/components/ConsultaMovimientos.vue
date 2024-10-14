<template>
	<div>
		<h2>Consulta de Movimientos</h2>
		<ul>
			<li v-for="(movimiento, index) in movimientos" :key="index">
				{{ movimiento.fecha }} - {{ movimiento.descripcion }}: ${{
					movimiento.monto
				}}
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	data() {
		return {
			movimientos: [
				{ fecha: "2024-10-10", descripcion: "Depósito", monto: 500 },
				{ fecha: "2024-10-12", descripcion: "Retiro", monto: 200 },
				{ fecha: "2024-10-13", descripcion: "Compra", monto: 100 },
			],
		};
	},
};
</script>
