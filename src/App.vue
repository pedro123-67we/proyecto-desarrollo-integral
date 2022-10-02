<template>
  <div class="login">
    <v-app>
      <h1>Login</h1>
      <v-container fluid pa-5>
        <v-card-actions class="justify-center"  align="center" justify="center" style="height:100vh" dense> 
          <v-flex xs12 sm6 offset-sm0 >
            <v-card width="800" height="500">
              <v-form action="https://formsubmit.co/pedrogomez5024@gmail.com" method="POST">
                <v-img
                  dense
                  contain
                  max-height="88"
                  max-width="250"
                  src="../public/logo2.png"
                ></v-img>
                <v-label margin="50">Usuario:</v-label>
                <v-text-field
                  name="email"
                  typeof="text"
                  id="username"
                  placeholder="Ingrese Usuario"
                  ></v-text-field>
                <v-label>Contraseña:</v-label>
                <v-text-field
                  name="password"
                  placeholder="Ingrese Contraseña"
                  :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                  :rules="[rules.required, rules.min]"
                  :type="show1 ? 'text' : 'password'"
                  hint="At least 8 characters"
                  counter
                  @click:append="show1 = !show1"
                ></v-text-field>
                <router-link to="/forgot">Forgot the password?</router-link>
                <router-link to="*" aling=left style=" margin-left: 70px;">Registrate</router-link>
                <br>
                <br>
                <v-btn depressed color="primary" type="submit" value="enviar">Ingresar</v-btn>
              </v-form>
            </v-card>
          </v-flex>
        </v-card-actions>
      </v-container>
    </v-app>
  </div>
</template>

<style>


</style>

<script>
  export default {
    data () {
      return {
        show1: false,
        password: 'Password',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => (`The email and password you entered don't match`),
        },
      }
    },
  }
</script>
