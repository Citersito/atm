<template>
	<div>
		<h2>Depósito a Cuenta</h2>
		<form @submit.prevent="realizarDeposito">
			<label for="monto">Monto a depositar:</label>
			<input v-model="monto" type="number" id="monto" required />
			<button type="submit">Depositar</button>
		</form>
		<p v-if="mensaje">{{ mensaje }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			monto: "",
			mensaje: "",
		};
	},
	methods: {
		realizarDeposito() {
			if (this.monto > 0) {
				this.mensaje = `Has depositado $${this.monto} exitosamente.`;
				// Aquí puedes integrar lógica real de backend
				this.monto = ""; // Limpiar el campo después de depositar
			} else {
				this.mensaje = "El monto debe ser mayor a 0.";
			}
		},
	},
};
</script>
