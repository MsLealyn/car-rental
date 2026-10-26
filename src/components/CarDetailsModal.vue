<script>
export default {
    props: ['carsPicture'],
    data(){
        return{
            
        }

    },
    methods: {
        // detailBtnclose(mod) {
        //     this.$emit('closeModal', mod)
        // }
        remove(detail){
            this.$emit('closeToParent', detail)
        }
    }

}
</script>

<template>
    <div v-for="detail in carsPicture" :key="detail.id" class="fixed top-0 inset-0">
        <div class="w-full h-screen bg-black/10 backdrop-blur-2xl absolute top-0"></div>
        <div class=" w-full h-fit flex justify-center items-center mt-50 relative top-0">
            <div class="grid grid-cols-1">
                <div  class="bg-[#87d8f3] w-190 h-fit pb-5">
                    <div class="flex justify-end p-3">
                        <button @click="remove" class="cursor-pointer font-bold hover:text-red-500">X</button>
                    </div>
                    <div class="flex justify-center items-center gap-10">
                        <img class="w-90 h-80 rounded-3xl" :src="detail.image" alt="">
                        <div class="w-80 space-y-2">
                            <h1 class="text-2xl font-bold font-arial">{{ detail.name }} {{ detail.brand }}</h1>
                            <h1 class="text-sm font-arial"><span class="font-bold">Description:</span> {{ detail.description }}</h1>
                            <h1 class="text-sm font-arial"><span class="font-bold">Key Features:</span>  {{ detail.features }}</h1>
                            <div>
                                <p class="font-arial font-bold text-md">Price:<span class="font-semibold">₱{{
                                    detail.price
                                        }}.00 /24hrs</span></p>
                                <button
                                    class="bg-[#0d4976e0] px-8 py-2 rounded-full text-white font-arial font-semibold mt-5">BOOK</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </div>
    <!-- <div v-for="detail in carsPicture" :key="detail.id" class="w-full h-screen bg-amber-50/50 backdrop-blur-md flex justify-center items-center fixed top-0">
        <div class="w-100 h-100 bg-blue-200">
            <p @click="remove" class="cursor-pointer text-end">x</p>
            <img :src="detail.image" alt="">
        </div>
    </div> -->
</template>