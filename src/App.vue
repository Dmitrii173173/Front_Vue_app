
<template>
    <div class="app">
        
            <form @submit.prevent >
                <h4>Create Ticket</h4>
                <input v-bind:value="departurecity" @input="departurecity = $event.target.value" class="input" type="text" placeholder="Departure City">
                <input v-bind:value="arrivalcity" @input="arrivalcity = $event.target.value" class="input" type="text" placeholder="Arrival City">
                <input v-bind:value="departuredatetime" @input="departuredatetime = $event.target.value" class="input" type="text" placeholder="Departure Date Time">
                <input v-bind:value="arrivadatetime" @input="arrivadatetime = $event.target.value" class="input" type="text" placeholder="Arriva Date Time">
                <input v-bind:value="cost" @input="cost = $event.target.value" class="input" type="text" placeholder="Сost">
                <button class="btn" @click="createTicket">Create</button>
            </form>
        
        
            <div class="ticket" v-for="ticket in tickets" v-bind:key="ticket.id">
                <div><strong>Departure City: </strong>{{ ticket.departurecity }}</div>
                <div><strong>Arrival City: </strong>{{ ticket.arrivalcity }}</div>
                <div><strong>Departure Date Time: </strong>{{ ticket.departuredatetime }}</div>
                <div><strong>Arriva Date Time: </strong>{{ ticket.arrivadatetime }}</div>
                <div><strong>Cost: </strong>{{ ticket.cost }}</div>
            </div>
        
    </div>
</template>

<script>
export default {
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
            departurecity: '',
            arrivalcity: '',
            departuredatetime: '',
            arrivaDatetime: '',
            cost: ''
        }
    },

    methods:{
      createTicket(){
          const newTicket = {
              id: Date.now(),
              departurecity: this.departurecity,
              arrivalcity: this.arrivalcity,
              departuredatetime: this.departuredatetime,
              arrivadatetime: this.arrivadatetime,
              cost: this.cost,
          }
          this.tickets.push(newTicket);
          this.departurecity = '';
          this.arrivalcity = '';
          this.departuredatetime = '';
          this.arrivadatetime = '';
          this.cost = '';

      },
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
.ticket {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
.form{
    display: flex;
    flex-direction: column;
}
.input{
    width: 100%;
    border: 2p solid teal;
    padding: 10px 15px;
    margin-top: 15px;
}
.btn{
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 1px solid teal;
}
</style>