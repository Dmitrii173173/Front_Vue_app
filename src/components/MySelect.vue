<template>
    <select v-model="modelVaue" @change="changeOptions">
        <option disabled value="">Choice from list</option>
        <option v-for="option in options" :key="option.value" :value="option.value">
                {{option.departurecity}}

        </option>
    </select>
</template>

<script>

export default {
        name:'my-select',
        props:{
            modelValue:{
                type: String
            },
            options:{
                type: Array,
                default: ()=> []
            }
        },
        methods:{
            changeOptions(event){
                this.$emit('update:modelVaue', event.target.value);
            }
            
        }
        
    }
</script>

<style scoped>

</style>
