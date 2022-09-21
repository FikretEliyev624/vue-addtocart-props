<template>
    <div class="bg-blue-300 min-h-auto">
        <div>
            <p class="text-center text-4xl font-bold text-white">Products</p>
            <AppProducts @add-item="addItem" :Db="productList" />           
        </div>
        <div class='mt-20 mb-16'>
            <p class="text-center text-4xl font-bold text-white">Bucket</p>  
        </div>
             <AddToCart @delete-item="deleteItem" :newDb="newList"/> 
             
             <div class="mt-20">
        <p class="text-center text-4xl font-bold text-white">Total Bar</p>
            <TotalBar :totalCalculate='totalCalculate' :deleteAllItem='deleteAllItem'/>
    </div>
        </div>
</template>

<script>
import AppProducts from '@/components/AppProducts'
import AddToCart from '@/components/AddToCart'
import TotalBar from '@/components/TotalBar'
export default {
    components:{
        AppProducts,
        AddToCart,
         TotalBar
    },
    data(){
        return{
            productList:[
                {id:1,title:'ASUS TUF Gaming A15 FA507RE-HN054 90NR08Y2-M003B0 (2022)',text:'15.6″ 144Hz/R7-6800H/RAM 8GB DDR5-4800MHz/SSD 512GB/RTX 3050Ti 4GB',img:'https://gamenotebaku.az/cdn/storage/product_images/kMuRtZHKLZpHwAdZe/fullHD/kMuRtZHKLZpHwAdZe.png',price:2400,count:1},
                {id:2,title:'ASUS ROG Strix G17 G713RW-LL154 90NR08H4-M009F0 (2022)',text:'17.3 240Hz/3ms, WQHD (2560×1440)/R7-6800H/RAM 16GB DDR5-4800MHz/SSD 1TB Gen4/RTX 3070Ti 8GB',img:'https://aztech.az/wp-content/uploads/2022/06/ASUS-ROG-Strix-SCAR-17-G733ZW-KH116W-90NR08G2-M009M0-2022-5.png',price:2600,count:1},
                {id:3,title:'MSI Pulse GL76 12UGK 9S7-17L314-446 (2022)',text:'17.3″ 360Hz, sRGB: 100%/i9-12900H/RAM 16GB/SSD 1TB/RTX 3070 8GB',img:'https://asset.msi.com/resize/image/global/product/product_16393758296207a13ff28cb94f2c7567e589edf0c0.png62405b38c58fe0f07fcef2367d8a9ba1/1024.png',price:4769,count:1},
    ],
    newList:[],
        }
    },
    methods: {
        addItem(item){
            this.newList.find(product=>product.id===item.id)
            ?item.count++
            :this.newList.push(item)


        },
        deleteItem(cart){
            this.newList=this.newList.filter(item=>item!==cart)
            cart.count=1
             

        },
        deleteAllItem(){
            this.newList.length=0

        },
        totalCalculate(){
            return this.newList.reduce((total,user)=>total+user.count*user.price,0)
        }
    },
}
</script>