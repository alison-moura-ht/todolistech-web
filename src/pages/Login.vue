<template>
  <v-container>
    <v-row>
      <v-col cols="4" offset="4">
        <v-form class="mt-16">
          <v-card variant="outlined" class="pa-10">
            <v-card-title>Entre no sistema</v-card-title>
            <v-card-text>
              <v-text-field
                label="Email"
                type="email"
                variant="outlined"
                v-model="usuario.email"
              ></v-text-field>
              <v-text-field
                label="Senha"
                type="password"
                variant="outlined"
                v-model="usuario.senha"
              ></v-text-field>
            </v-card-text>
            <v-card-actions>
              <v-btn color="error" variant="text" class="mx-10" rounded
                >Cancelar</v-btn
              >
              <v-btn @click="fazerLogin()" color="success" elevation="0" rounded
                >Entrar</v-btn
              >
            </v-card-actions>
          </v-card>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import AuthService from "./../service/AuthService";

export default {
  data: () => {
    return {
      usuario: {},
    };
  },
  methods: {
    async fazerLogin() {
      try {
        const resultado = await AuthService.login(this.usuario);
        this.$router.push("/home");
      } catch (error) {
        alert(error.message);
      }
    },
  },
};
</script>
