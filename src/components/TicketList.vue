<template>
    <div>
        <h3>Tickets list</h3>
        <ticket-item  
        v-for="ticket in tickets" 
        :ticket="ticket" 
        :key="ticket.id"/>
    </div>
</template>

<script>
import TicketItem from "./TicketItem.vue";
export default {
  components: { TicketItem },
    props:{
        tickets:{
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>

</style>
