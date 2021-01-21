<template>
    <li class="list-item" :class="{ even: item % 2 === 0 }">{{ item }}</li>
</template>

<script>
export default {
    name: 'BasicListItem',
    props: {
        item: {
            type: Number,
            required: true
        }
    }
}
</script>

<style>
li.even {
    background-color: rgba(22, 64, 240, 0.1);
}
</style>