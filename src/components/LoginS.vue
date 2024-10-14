<template>
	<div class="login-container">
		<h2>Login - Simulador de Cajero Automático</h2>
		<form @submit.prevent="handleLogin">
			<div class="input-group">
				<label for="account-number">Número de cuenta</label>
				<input
					type="text"
					v-model="accountNumber"
					id="account-number"
					placeholder="Ingrese su número de cuenta"
					required
				/>
			</div>

			<div class="input-group">
				<label for="pin">PIN</label>
				<input
					type="password"
					v-model="pin"
					id="pin"
					placeholder="Ingrese su PIN"
					required
				/>
			</div>

			<button type="submit">Iniciar sesión</button>

			<p v-if="errorMessage" class="error">{{ errorMessage }}</p>
		</form>
	</div>
</template>

<script>
export default {
	data() {
		return {
			accountNumber: "",
			pin: "",
			errorMessage: "",
		};
	},
	methods: {
		handleLogin() {
			const validAccountNumber = "1111222233334444";
			const validPin = "1111";

			if (this.accountNumber === validAccountNumber && this.pin === validPin) {
				this.errorMessage = "";
				this.$emit("login-success"); // Emite el evento de éxito de login
			} else {
				this.errorMessage =
					"Número de cuenta o PIN incorrecto. Intente nuevamente.";
			}
		},
	},
};
</script>

<style scoped>
.login-container {
	max-width: 400px;
	margin: 50px auto;
	padding: 20px;
	border: 1px solid #ddd;
	border-radius: 8px;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
	text-align: center;
}

.input-group {
	margin-bottom: 15px;
}

.input-group label {
	display: block;
	font-weight: bold;
	margin-bottom: 5px;
}

.input-group input {
	width: 100%;
	padding: 10px;
	font-size: 16px;
	border: 1px solid #ddd;
	border-radius: 4px;
}

button {
	padding: 10px 20px;
	background-color: #4caf50;
	color: white;
	border: none;
	border-radius: 4px;
	font-size: 16px;
	cursor: pointer;
}

button:hover {
	background-color: #45a049;
}

.error {
	color: red;
	margin-top: 10px;
}
</style>
