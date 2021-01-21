<template>
    <RecycleScroller
        class="list"
        :items="items"
        :min-item-size="22"
        #default="{ item }"
    >
        <DynamicListItem :key="item.message" :message="item.message" style="height: 22px" />
    </RecycleScroller>
</template>

<script>
import { RecycleScroller } from 'vue-virtual-scroller'
import 'vue-virtual-scroller/dist/vue-virtual-scroller.css'
import DynamicListItem from './DynamicListItem'

export default {
    name: 'DynamicList',
    components: { RecycleScroller, DynamicListItem },
    props: {
        itemNumber: {
            type: Number,
            default: 20000
        }
    },
    data() {
        return {
            items: new Array(this.itemNumber).fill(null).map((_, index) => ({ id: index, message: `item-${index}` }))
        }
    }
}
</script>
