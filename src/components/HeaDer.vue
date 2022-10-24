<template>
  <v-app-bar app 
     
      color="white"
      elevate-on-scroll elevation="4"
      
    >
      <v-app-bar-nav-icon @click="$emit('handeDrawer')"></v-app-bar-nav-icon>
           <v-spacer></v-spacer>
      <v-col cols="12" lg="6">
         <v-form class="mt-5">
          <v-text-field placeholder="search" rounded outlined  dense append-icon="mdi-magnify" />
         </v-form>
      </v-col>
      <v-spacer></v-spacer>

 <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <span v-bind="attrs"  v-on="on" style="cursor_pointer" class="mx-5 mr-10"> 
          <v-badge offset-x="10" offset-y="10" color="red" content="5">
               <v-icon>mdi-bell</v-icon>
          </v-badge>
        </span>
      </template>
     

     
    <v-list three-line width="250">
      <template v-for="(item, index) in items">
        <v-subheader v-if="item.header" :key="item.header" v-text="item.header" ></v-subheader>

        <v-divider
          v-else-if="item.divider"
          :key="index"
          :inset="item.inset"
        ></v-divider>

        <v-list-item
          v-else
          :key="item.title"
        >
          <v-list-item-avatar>
            <v-img :src="item.avatar"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title v-html="item.title"></v-list-item-title>
            <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>
    </v-list>
    </v-menu>


    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <span v-bind="attrs"  v-on="on" style="cursor_pointer" class="mx-5 mr-10"> 
        <v-chip link>
            <v-badge dot bottom offset-x="10" offset-y="10" color="green">
                  <v-avtar size="40">
                  <!-- <v-img src="i2.jpg"></v-img> -->
                  </v-avtar>
            </v-badge>
            <span>Ezo</span>
        </v-chip>
        </span>
      </template>
      <v-list  class="py-0">
        <v-list-item two-line >
          <v-list-item-avatar width=" 50">
             <v-img src="i2.jpg"></v-img>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title>
              sharlie chine
            </v-list-item-title>
            <v-list-item-subtitle>
              logged in
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-list-item v-for="menu in menus" :key="menu.title">
          <v-list-icon>
            <v-icon>{{menu.icon}}</v-icon>
          </v-list-icon>
          <v-list-content>
            <v-list-tile>{{menu.title}}</v-list-tile>
          </v-list-content>
        </v-list-item>
      </v-list>
     
    </v-menu>

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
</template>
<script>
export default {

    data() {
        return{
          menus:[
            {title:"Profile",icon:"mdi-acount"},
            {title:"Change Password",icon:"mdi-key"},
            {title:"Setting",icon:"mdi-cog"},
            {title:"Logout",icon:"mdi-logout"},
          ],
      items: [
        { header: 'Today' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          title: 'Brunch this weekend?',
          subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?`,
        },
        { divider: true, inset: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
          subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`,
        },
       
      
      ],
        }
    },
}
</script>