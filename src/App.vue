<template>
  <v-app id="inspire">
      <!--  -->
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Welcome
          </v-list-item-title>
          <v-list-item-subtitle>
            Azrul
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>



    <v-app-bar
      app
      color="primary"
      dark
      prominent
      src="coffee.jpg"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(143,98,81,.2), rgba(143,98,81,.5)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer = !drawer" > </v-app-bar-nav-icon>

      <v-app-bar-title>My ToDo List

      </v-app-bar-title>
      

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>


  export default {
    data: () => ({ 
      drawer: null,
      items: [
          { title: 'Home', icon: 'mdi-home', to: '/' },
          { title: 'History', icon: 'mdi-history', to: '/History' },
        ],
       }),
  }
</script>

