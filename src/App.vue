<template>
    <div>
        <div>
            <button @click="addDateOfDeparture">DateOfDeparture</button>
            <button @click="addDepartureCity">DepartureCity</button>
            <button @click="addArrivalCity">ArrivalCity</button>
            <button @click="addDepartureDateTime">DepartureDateTime</button>
            <button @click="addArrivaDateTime">ArrivaDateTime</button>
            <button @click="addCost">Cost</button>
            <button @click="addResults">results</button>
        </div>
        <div> DateOfDeparture : <strong>{{ DateOfDeparture }}</strong></div>
        <div> DepartureCity : <strong>{{ DepartureCity }}</strong></div>
        <div> ArrivalCity : <strong>{{ ArrivalCity }}</strong></div>
        <div> DepartureDateTime : <strong>{{ DepartureDateTime }}</strong></div>
        <div> ArrivaDateTime : <strong>{{ ArrivaDateTime }}</strong></div>
        <div> Cost : <strong>{{ Cost }}</strong></div>
        <div> addResults : <strong>{{ results }}</strong></div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            DateOfDeparture: 0,
            DepartureCity: 0,
            ArrivalCity: 0,
            DepartureDateTime: 0,
            ArrivaDateTime: 0,
            Cost: 0,
            results: 0
        }
    },
    methods:{
        addDateOfDeparture(){
            this.DateOfDeparture += 1;
        },
        addDepartureCity(){
            this.DepartureCity += 1;
        },
        addArrivalCity(){
            this.ArrivalCity += 1;

        },
        addDepartureDateTime(){
            this.DepartureDateTime += 1;
        },
        addArrivaDateTime(){
            this.ArrivaDateTime += 1;
        },
        addCost(){
            this.Cost += 1;
        },
        addResults(){
            this.results += 1;
        }
    }
}
</script>

<style>

</style>