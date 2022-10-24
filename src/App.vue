<template>
  <v-app id="inspire">
   <HeaDer @handeDrawer="drawer =!drawer"/>
   <SideBar :drawer="drawer"/>

    

    <v-main>
      <v-container class="py-8 px-6"  fluid  >
<router-view>

</router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import HeaDer from "@/components/HeaDer";
import SideBar from "@/components/SideBar";
  export default {
    components:{HeaDer,SideBar},
    data: () => ({
      cards: ['Today', 'Yesterday'],
      drawer: true,
     
    }),
  }
</script>
