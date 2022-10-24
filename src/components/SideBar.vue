<template>
   <v-navigation-drawer v-model="drawer" app >
      <v-img src="i2.jpg">
        <div class="text-center" >
        <!-- <v-sheet  color="grey lighten-4" class="pa-4 mt-2" style="position:absolute"> -->
        <v-avatar class="mb-4 mt-4"  color="grey darken-1"  size="64">
            <v-img aspect-ratio="30" src="i1.png"></v-img>
        </v-avatar>
        <h4 class="white--text">Vuetify Admine panel</h4>
      <!-- </v-sheet> -->
        </div>
      </v-img>
      <v-divider></v-divider>
      <v-list>
        <v-list-item v-for="[icon, text] in links" :key="icon" link >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
</template>
<script>
export default {
    // props:['drawer'],
   
    data() {
       return{
         links: [
        ['mdi-microsoft-windows', 'dashboard'],
        ['mdi-account', 'Profile'],
        ['mdi-clipboard-list-outline', 'Product'],
        ['mdi-clipboard-list', 'Order'],
        ['mdi-alert-octagon', 'System setting'],
      ],
       } 
    },
}
</script>