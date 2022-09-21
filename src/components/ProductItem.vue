<template>
    <li class="mx-24 bg-orange-400 rounded-lg text-white w-64 border-2 border-orange-400">
                        <div class="flex justify-center">
                            <img class="w-32 my-3" :src="item.img" :alt="item.title">
                        </div>
                        <div>
                           <div>
                                <p class="font-medium my-5 text-center text-xl">{{ item.title }}</p>
                                <p class="text-base font-medium text-center">{{ item.text }}</p>
                           </div>
                            <div class="flex justify-center my-5">
                                <p class="text-base mx-2 font-bold">{{ item.price }}<span class="ml-1">Azn</span></p>
                                <button @click="$emit('add-item',item)" class="px-2 hover:bg-green-400 mx-2 py-1 bg-green-500 text-medium text-white rounded-lg">Add</button>
                            </div>
                        </div>
    </li>
</template>


<script>
export default {
    props:['item']
}
</script>