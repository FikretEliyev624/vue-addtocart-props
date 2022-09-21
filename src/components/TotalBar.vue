<template>
    <div class="flex justify-center py-32">
        <p class="text-2xl font-medium text-white mx-2">Total: {{totalCalculate()}} Azn</p>
        <button @click="deleteAllItem" class="mx-2 px-2 py-1 rounded-lg hover:bg-rose-500 bg-red-600 text-white font-medium">Remove All</button>
    </div>
</template>

<script>
export default {
    props:{
        totalCalculate:{
            type:Function,
            required:true
        },
        deleteAllItem:{
            type:Function,
            required:true
        }
    }
}
</script>