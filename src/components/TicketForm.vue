

<template>
    <div>
        <form @submit.prevent >
                <h4>Create Ticket</h4>
                <input v-model="ticket.departurecity" class="input" type="text" placeholder="Departure City">
                <input v-model="ticket.arrivalcity" class="input" type="text" placeholder="Arrival City">
                <input v-model="ticket.departuredatetime" class="input" type="text" placeholder="Departure Date Time">
                <input v-model="ticket.arrivadatetime" class="input" type="text" placeholder="Arriva Date Time">
                <input v-model="ticket.cost" class="input" type="text" placeholder="Cost">
                <button class="btn" @click="createTicket">Create</button>
        </form>
    </div>
</template>

<script>
export default {
    data(){
        return{
            ticket:{
                departurecity: '',
                arrivalcity: '',
                departuredatetime: '',
                arrivadatetime: '',
                cost: ''
            }
        }
    },
    methods:{
        createTicket(){
            this.ticket.id = Date.now();
            this.$emit('create', this.ticket)
            this.ticket = {
                departurecity: '',
                arrivalcity: '',
                departuredatetime: '',
                arrivadatetime: '',
                cost: ''
            }
        }
    }
}
</script>

<style scoped>
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
