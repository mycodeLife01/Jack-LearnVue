<script>
    export default {
        props: {
            title: String
        },
        emits: ['enlarge-text']
    }

</script>

<template>
    
    <h4>{{ title }}</h4>
    <button @click="$emit('enlarge-text')">Enlarge Text</button>
    <slot/>
</template>