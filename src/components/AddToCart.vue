<template>
    <div class="overflow-x-auto relative">
    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
        <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
            <tr>
                <th scope="col" class="py-3 px-6">
                    
                </th>
                 <th scope="col" class="py-3 px-6">
                    Product name
                </th>
                <th scope="col" class="py-3 px-6">
                    Features
                </th>
                <th scope="col" class="py-3 px-6">
                    Price
                </th>
                <th scope="col" class="py-3 px-6">
                    Total
                </th>
                <th scope="col" class="py-3 px-6">
                    Number
                </th>
                <th scope="col" class="py-3 px-6">
                    
                </th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="item in newDb" :key="item.id" class="bg-white text-black border-b dark:bg-gray-800 dark:border-gray-700">
                <th scope="row" class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                    <img class="w-20" :src="item.img" :alt="item.title" />
                </th>
                <td class="py-4 px-6 font-bold">
                    {{ item.title }}
                </td>
                <td class="py-4 px-6 font-medium">
                    {{ item.text }}
                </td>
                <td class="py-4 px-8 font-medium">
                    {{ item.price }}
                </td>
                <td class="py-4 px-6">
                    {{ total=item.count*item.price }} 
                </td>
                <td class="py-4 px-6">
                    <input v-model="item.count" type="text" class="py-2 px-2 rounded-lg text-blue-600 w-24 focus:outline-none border-none text-xl bg-pink-300">
                </td>
                <td class="py-4 px-6">
                    <button @click="$emit('delete-item',item)" class="text-xl hover:bg-rose-300 rounded-full px-2 py-1 bg-red-600 text-white">x</button>
                </td>
            </tr>
        </tbody>
    </table>
</div>
</template>

<script>
export default {
    props:['newDb'],
}
</script>