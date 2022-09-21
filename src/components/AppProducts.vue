<template>
    <div class="mt-20">
                <ul class="flex flex-wrap">
                    <ProductItem @add-item="$emit('add-item',$event)" v-for="product in Db" :item="product" :key="product.id" />
                </ul>
            </div>
</template>

<script>
    import ProductItem from '@/components/ProductItem'
export default {
    props:['Db'],
    components:{
        ProductItem
    }
}
</script>

