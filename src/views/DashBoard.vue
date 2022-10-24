<template>
    <div class="dashboard">
        <v-ezoheader class="d-flex justify-space-between align-center">
            <h3>Dashboard</h3>
            <v-btn color="success" class="rounded-lg">
                view orders
            </v-btn>
        </v-ezoheader>
        <v-row class="mt-5">
            <v-col cols="12" lg="7"> 
             <v-alert dense text type="success">
               <strong>login successfuly</strong> prop and a <strong>type</strong> of success
                    </v-alert>
          <v-row >
             <v-col lg="6" cols="12" v-for="active in activities" :key="active.title">
               <v-card elevation="2" class="rounded-lg">
                <v-card-text class=" d-flex justify-space-between align-center">
                <div>
                    <strong>{{active.title}}</strong><br>
                    <small>i am here</small>
                </div>
                <v-avatar :color="active.color" size="70">
                  <span class="white--text">{{active.amount}}</span>
                </v-avatar>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
            </v-col>

         <v-col lg="5" cols="12">
           <v-card>
            <v-card-title>Activities</v-card-title>
            <v-timeline  align-top dense >
        <v-timeline-item  color="green"  small >
          <v-row class="pt-1">
            <v-col cols="6">
              <strong>50 minutes ago</strong>
            </v-col>
          </v-row>
        </v-timeline-item>
        <v-timeline-item  color="pink"  small>
          <v-row class="pt-1">
            <v-col cols="6">
              <strong>10 minutes ago</strong>
            </v-col>
          </v-row>
        </v-timeline-item>
        <v-timeline-item  color="purple"  small>
          <v-row class="pt-1">
            <v-col cols="6">
              <strong>33 minutes ago</strong>
            </v-col>
          </v-row>
        </v-timeline-item>
      </v-timeline>
           </v-card>
         </v-col>
        </v-row>
        <v-row>
            <v-col lg="12">
                <v-data-table caption="Recent orders"  :headers="headers" :items="desserts" :items-per-page="5" class="elevation-1"></v-data-table>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    name:"DashBoard",
    data(){
        return{
            activities:[
                {title:"total products",color:'red',amount:"4545"},
                {title:"total catogrey",color:'purple',amount:"364"},
                {title:"total order",color:'cyan',amount:"1224"},
                {title:"total purchase",color:'amber',amount:"7690"},
            ],
             headers: [
          {
            text: 'Dessert (100g serving)',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: 'Calories', value: 'calories' },
          { text: 'Fat (g)', value: 'fat' },
          { text: 'Carbs (g)', value: 'carbs' },
          { text: 'Protein (g)', value: 'protein' },
          { text: 'Iron (%)', value: 'iron' },
        ],
        desserts: [
          {
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%',
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%',
          },
          {
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%',
          },
          {
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%',
          },
          {
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%',
          },
          {
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%',
          },
          {
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%',
          },
          {
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%',
          },
          {
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%',
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%',
          },
        ],
        }
    }
}
</script>
<style scoped>

</style>