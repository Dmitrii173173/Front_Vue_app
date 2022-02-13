<template>
        <div class="ticket">
                <div><strong>Departure City: </strong>{{ ticket.departurecity }}</div>
                <div><strong>Arrival City: </strong>{{ ticket.arrivalcity }}</div>
                <div><strong>Departure Date Time: </strong>{{ ticket.departuredatetime }}</div>
                <div><strong>Arriva Date Time: </strong>{{ ticket.arrivadatetime }}</div>
                <div><strong>Cost: </strong>{{ ticket.cost }}</div>
        </div>
    
</template>

<script>
export default {
        props: {
            ticket: {
                type: Object,
                required: true,
            }
        }
    }
</script>

<style scoped>

</style>