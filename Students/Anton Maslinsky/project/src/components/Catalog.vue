<template>
    <div class="product-box__list">
        <item 
            itemType="catalog" 
            v-for="item of items" 
            :item="item" 
            :key="item.id_product"
        />
    </div>    
</template>

<script>
import item from './Item.vue';

export default {
    components: { item },

    data() {
        return {
            items: [],
            url: '/api/catalog',
        }
    },
    
    mounted() {
        this.$parent.get(this.url).then(data => {
            this.items = data;
        })
    },
}
</script>

<style>

</style>