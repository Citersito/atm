<template>
	<div id="app">
		<div v-if="!isLoggedIn">
			<!-- Muestra el login si el usuario no ha iniciado sesión -->
			<Login @login-success="handleLoginSuccess" />
		</div>

		<div v-else>
			<!-- Muestra las opciones del cajero automático si el usuario ha iniciado sesión -->
			<div class="buttons">
				<div class="button" @click="currentView = 'ConsultaSaldo'">
					<p>Consulta de saldo</p>
				</div>
				<div class="button" @click="currentView = 'ConsultaMovimientos'">
					<p>Consulta de Movimientos</p>
				</div>
				<div class="button" @click="currentView = 'PagoServicios'">
					<p>Pago de servicios</p>
				</div>
				<div class="button" @click="currentView = 'RetiroDinero'">
					<p>Retiro de dinero</p>
				</div>
				<div class="button" @click="currentView = 'DepositosCuenta'">
					<p>Deposito a cuenta</p>
				</div>
				<div class="button" @click="currentView = 'Ajustes'">
					<p>Ajustes</p>
				</div>
			</div>

			<!-- Renderiza el componente dependiendo del botón seleccionado -->
			<component :is="currentView"></component>
		</div>
	</div>
</template>

<script>
import Login from "./LoginS.vue";
import ConsultaSaldo from "./ConsultaSaldo.vue";
import ConsultaMovimientos from "./ConsultaMovimientos.vue";
import DepositosCuenta from "./DepositosCuenta.vue";

export default {
	data() {
		return {
			isLoggedIn: false, // Estado de inicio de sesión
			currentView: "ConsultaSaldo", // Componente inicial por defecto
		};
	},
	components: {
		Login,
		ConsultaSaldo,
		ConsultaMovimientos,
		DepositosCuenta,
	},
	methods: {
		handleLoginSuccess() {
			this.isLoggedIn = true; // Cambia el estado para mostrar el menú del cajero
		},
	},
};
</script>

<style>
/* Agrega estilos personalizados si es necesario */
</style>
