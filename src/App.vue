
<template>
    <div class="app">
        <h1>T I C K E T shop</h1>
        <div class="app_btns">
            <button>
                
            </button>
            <my-select 
            v-model="selectedSort"
            :options="sortOptions"
            />
        </div>
        <ticket-form
            @create="createTicket"

        />
        <ticket-list 
            :tickets="tickets"
        />
    </div>
</template>

<script>
import MySelect from './components/MySelect.vue';
import TicketForm from './components/TicketForm.vue';
import TicketList from './components/TicketList.vue';
export default {
    components: {
        TicketList,
        TicketForm,
        MySelect
    },
    data(){
        return{
            tickets:[
                {id: 1, departurecity:'Moscow', arrivalcity:'Beijing', departuredatetime:'12.03.2022, 21:00',
                arrivadatetime:'12.03.2022, 13:00', cost:'300000'},
                {id: 2, departurecity:'Dubai', arrivalcity:'New-York', departuredatetime:'22.04.2022, 03:00',
                arrivadatetime:'22.04.2022, 20:30', cost:'120000'},
                {id: 3, departurecity:'Bangkok', arrivalcity:'Islamabad', departuredatetime:'06.16.2022, 16:30',
                arrivadatetime:'06.17.2022, 06:20', cost:'20000'},
            ],
            selectedSort:'',
            sortOptions:[
                {value:'departurecity', departurecity:'Departure City'},
                {value:'arrivalcity', arrivalcity:'Arrival City'},
            ]
        }
    },

    methods:{
      createTicket(ticket){
          this.tickets.push(ticket);
      },
      watch:{
                selectedSort(newValue){
                    this.tickets.sort ((ticket1, ticket2 ) => {
                        return ticket1[newValue]?.localeCompare(ticket2[newValue])
                    })
                },
            }
    }
}
</script>
<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app{
    padding: 20px;
}
.app_btns{
    margin: 50px;
    display: flex;
    justify-content: space-between;
}
</style>