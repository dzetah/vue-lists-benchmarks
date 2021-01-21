<template>
    <ul class="list">
        <FunctionalListItem v-for="item in items" :key="item" :item="item" />
    </ul>
</template>

<script>
import FunctionalListItem from './FunctionalListItem'

export default {
    name: 'FunctionalList',
    components: { FunctionalListItem },
    props: {
        itemNumber: {
            type: Number,
            default: 20000
        }
    },
    data() {
        return {
            items: new Array(this.itemNumber).fill(null).map((_, index) => index)
        }
    }
}
</script>
