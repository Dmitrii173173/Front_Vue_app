<template>
    <div>
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
    props:{
        tickets:{
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>
.ticket {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
</style>
