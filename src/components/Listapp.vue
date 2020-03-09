<template>
<v-card>
  <v-card-title>
      
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Busqueda por Email"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
  <v-data-table
    :headers="headers"
    :items="participants"
    :items-per-page="10"
    :search="search"
    class="elevation-1"  
  >
  </v-data-table>
  </v-card>

</template>



<script>
import participants from '../participants.json';

  export default {
    name: 'Listapp',
    props: {
      firstname: {
        type: String,
        required: true,
      },
      lastname: {
        type: String,
        required: true,
      },
      email: {
        type: String,
        required: true,
      },
      created: {
        type: Number,
        required: true,
      },
      paymentoption: {
        type: String,
        required: true,
      },
      state: {
        type: String,
        required: true,
        default: 'waitinglist',
      }
    
  },

    data () {
      return {
        search: '',
        headers: [
          {
            text: 'Firstname',
            align: 'start',
            /*sortable: false,*/
            value: 'firstname',
            filterable: false,
          },
          { text: 'Lastname', value: 'lastname', filterable: false, },
          { text: 'Email', value: 'email' },
          { text: 'Created', value: 'created', filterable: false, },
          { text: 'paymentoption', value: 'paymentoption', filterable: false,},
          { text: 'State', value: 'state', filterable: false, },
        ],
        participants: []
    }
    },

    mounted() {
      this.participants=participants;
    },

  }
 
  
</script>
