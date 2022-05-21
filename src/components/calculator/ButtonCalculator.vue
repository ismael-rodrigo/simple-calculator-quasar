<template>
    <q-btn  push :color="button_color" round >{{props.value}}</q-btn>
</template>

<script setup>
const emit = defineEmits()

let props = defineProps({
  value: String,


})

let button_color = 'purple'
if(!isNaN(props.value) || props.value == '.')button_color = 'secondary'



</script>

<style>

</style>