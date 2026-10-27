<script>
export default {
    props: ['carsPicture'],
    data() {
        return {
            
        }
    },
    methods:{
        detailBtn(service){
            this.$emit('openModal', service)
        }
    }
}
</script>

<template>
    <!-- <div> -->
    <section class="py-10 bg-cover bg-center bg-[url('https://i.pinimg.com/736x/de/b0/29/deb029d0c81400200bfd0efc90836c14.jpg')]" id="services">

        <h2 class="text-3xl font-bold text-white mb-8 text-center">DSLJ Car Rental</h2>

        <div class="grid grid-cols-3 gap-8 container mx-auto pl-50">

            <div v-for="(service, index) in carsPicture" :key="service.id" class="">
                <div
                    class="bg-sky-200 rounded-lg shadow-md overflow-hidden hover:scale-103 transition duration-300 cursor-pointer">
                        <img :src="service.image" alt=""
                            class="w-full h-64 object-fit hover:scale-103 transition duration-300">

                    <div class="py-1 text-center">
                        <div class="flex justify-center items-center gap-3">
                            <h3 class="text-lg font-bold">{{ service.name }}</h3>
                            <p class="text-lg font-bold">{{ service.brand }}</p>
                        </div>

                        <p class="italic">{{ service.type }}</p>
                        <p class="text-blue-950 font-semibold">{{ service.status }}</p>
                    </div>

                    <div class="flex justify-between items-center mb-5 px-5">
                        <p class="text-xl">₱{{ service.price }}</p>
                        <button @click="detailBtn(service)"
                            class="px-5 py-2 text-white bg-sky-500 rounded-lg hover:scale-103 transition duration-300 cursor-pointer">Details</button>
                    </div>
                </div>
            </div>

        </div>
    </section>
 
</template>