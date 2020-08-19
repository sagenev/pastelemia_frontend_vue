<template>
  <div>
    <v-navigation-drawer v-model="drawer" app clipped>
      <v-list dense>
        <v-list-item class="px-2">
          <v-list-item-avatar>
            <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
          </v-list-item-avatar>

          <v-list-item-title
            ><strong>Claudio Vallejos</strong><br /><small
              >Admin</small
            ></v-list-item-title
          >

          <v-btn icon> </v-btn>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item link @click="expand = !expand">
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Principal</v-list-item-title>
          </v-list-item-content>
          <v-list-item-content>
            <v-icon v-if="!expand">mdi-menu-down</v-icon>
            <v-icon v-else>mdi-menu-up</v-icon>
          </v-list-item-content>
        </v-list-item>

        <v-expand-transition transition="fade-transition">
          <v-col v-show="expand">
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>Opción 1</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>Opción 2</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>Opción 3</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-col>
        </v-expand-transition>

        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-cog</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Opciones</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Pastelemia</v-toolbar-title>
      <v-spacer></v-spacer>

       <v-btn icon>
      <v-icon>mdi-message</v-icon>
    </v-btn>

    <div class="text-center">
      <v-menu
        v-model="opciones"
        :close-on-content-click="false"
        :nudge-width="200"
        offset-x
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn v-bind="attrs" v-on="on">
            <v-icon>mdi-cog</v-icon>
          </v-btn>
        </template>

        <v-card>
          <v-list>
            <v-list-item>
              <v-list-item-avatar>
                <img
                  src="https://randomuser.me/api/portraits/men/85.jpg"
                  alt="John"
                />
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title>Claudio Vallejos</v-list-item-title>
                <v-list-item-subtitle>Admin</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list>

          <v-divider></v-divider>

          <v-list>
            <v-list-item link>
              <v-list-item-action>
                <v-icon>mdi-text-box-outline</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <small>Mis datos</small>
              </v-list-item-content>
            </v-list-item>
            <v-list-item link>
              <v-list-item-action>
                <v-icon>mdi-account-edit</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <small>Editar Perfil</small>
              </v-list-item-content>
            </v-list-item>
          </v-list>

          <v-card-actions>
            <v-spacer></v-spacer>

            <v-btn text @click="opciones = false">Cancelar</v-btn>
          </v-card-actions>
        </v-card>
      </v-menu>
    </div>

    <v-btn icon>
      <v-icon>mdi-logout</v-icon>
    </v-btn>

    </v-app-bar>

  
  
  </div>
</template>

<script>

export default {
  name: "Header",
  components:{

  },
  data() {
    return {
      drawer: null,
      expand: false,
      opciones: false
    };
  }
};
</script>
