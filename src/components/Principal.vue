<template>
   <div>
    <v-img contain src="../assets/principal.png">
    <v-container fluid class="fill-height pa-0 ma-0">

        <v-row>
            <v-col>
                <v-row justify="center" align="center">
                    <v-card rounded color="transparent" elevation="0">
                    <v-card-title class="justify-center white--text bienvenido" > 
                        <h1 >¡Bienvenido!</h1> </v-card-title>
                        <v-card-text>
                            <v-row>
                                <v-text-field
                                    label="Usuario"
                                    outlined
                                    filled
                                    rounded
                                    dense
                                    dark
                                ></v-text-field>
                            </v-row>
                            <v-row>
                                <v-text-field
                                    label="Contraseña"
                                    outlined
                                    filled
                                    rounded
                                    dense
                                    dark
                                    color="white"
                                    v-model="password"
                                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                    :type="show1 ? 'text' : 'password'"
                                    name="input-10-1"
                                    @click:append="show1 = !show1"
                                ></v-text-field>
                            </v-row>
                            <v-row align="center" justify="center" class="mt-2">
                              <template>
                                <v-row justify="center">
                                  <v-dialog
                                      v-model="dialog"
                                      persistent
                                      max-width="600px"
                                  >
                                    <template v-slot:activator="{ on, attrs }">
                                      <v-btn
                                          elevation="2"
                                          color="#337CA0"
                                          dark
                                          rounded
                                          class="mr-3 caja"
                                          v-bind="attrs"
                                          v-on="on"
                                      >REGISTRARSE</v-btn>
                                    </template>
                                    <v-card>
                                      <v-card-text>
                                        <v-container>
                                          <v-row>
                                            <v-col cols="12">
                                              <v-text-field
                                                  label="Usuario *"
                                                  required
                                                  filled
                                                  rounded
                                                  dense
                                              ></v-text-field>
                                            </v-col>
                                            <v-col cols="12">
                                              <v-text-field
                                                  label="Email *"
                                                  required
                                              ></v-text-field>
                                            </v-col>
                                            <v-col cols="12">
                                             <v-text-field
                                              v-model="password"
                                              :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                              :type="show1 ? 'text' : 'password'"
                                              name="input-10-1"
                                              label="Contraseña *"
                                              hint="Mínimo 8 caracteres"
                                              counter
                                              @click:append="show1 = !show1"
                                            ></v-text-field>
                                            </v-col>
                                            
                                          </v-row>
                                        </v-container>
                                        
                                      </v-card-text>
                                      <v-card-actions>
                                        <v-spacer></v-spacer>
                                        <v-btn
                                            color="blue darken-1"
                                            text
                                            @click="dialog = false"
                                        >
                                          Close
                                        </v-btn>
                                        <v-btn
                                            color="blue darken-1"
                                            text
                                            @click="dialog = false"
                                        >
                                          Save
                                        </v-btn>
                                      </v-card-actions>
                                    </v-card>
                                  </v-dialog>
                                  <v-btn
                                          elevation="2"
                                          color="#00E140"
                                          dark
                                          rounded
                                          class="caja"
                                          to="/Explorar"
                                      >INICIAR SESIÓN</v-btn>
                                </v-row>
                              </template>
                            </v-row>
                            
                        </v-card-text>
                    </v-card>
                </v-row>
            </v-col>
        </v-row>
    </v-container></v-img></div> 
</template>

<style>
.bienvenido{
    text-shadow: 2px 3px 10px #000000;
}
.caja{
    font-weight: bold;
    text-shadow: 1px 1px 4px rgba(0,0,0,0.7);
}
</style>
<script>
export default {
    data(){
        return{
            show1 :false,
            password : '',
            dialog: false
        }
    }
}
</script>