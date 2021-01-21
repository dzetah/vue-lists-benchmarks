<template>
    <li class="list-item">{{ message }}</li>
</template>

<script>
export default {
    name: 'DynamicListItem',
    props: {
        message: {
            type: String,
            required: true
        }
    }
}
</script>