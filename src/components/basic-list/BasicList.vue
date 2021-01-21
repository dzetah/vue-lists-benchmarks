<template>
    <ul class="list">
        <BasicListItem v-for="item in items" :key="item" :item="item" />
    </ul>
</template>

<script>
import BasicListItem from './BasicListItem'

export default {
    name: 'BasicList',
    components: { BasicListItem },
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
    },
    methods: {
        addItems() {
            const newItems = new Array(this.itemNumber).fill(null).map((_, index) => `item-${this.items.length - 1 + index}`)
            this.items.push(...newItems);
        }
    }
}
</script>
