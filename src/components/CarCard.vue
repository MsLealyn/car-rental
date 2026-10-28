<script>
export default {
    props: ['carsPicture'],
    emits: ['openModal'],
    data() {
        return {

        }
    },
    methods: {
        detailBtn(n, b, p, i, s, t, d, f) {
            this.$emit('openModal', { name: n, brand: b, price: p, image: i, status: s, type: t, description: d, features: f })
        }
    }
}
</script>

<template>
    <!-- <div> -->
    <section
        class="py-10 min-h-screen bg-cover bg-center bg-[url('https://i.pinimg.com/736x/de/b0/29/deb029d0c81400200bfd0efc90836c14.jpg')]"
        id="services">

        <h2 class="text-2xl sm:text-3xl font-bold text-white mb-8 text-center px-4">DSLJ Car Rental</h2>

        <div
            class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8 container mx-auto px-4 sm:px-6 md:px-12 lg:pl-50 lg:pr-10">

            <div v-for="service in carsPicture" :key="service.id || service.name" class="">
                <div
                    class="bg-sky-200 rounded-lg shadow-md overflow-hidden hover:scale-103 transition duration-300 cursor-pointer">
                    <img :src="service.image" alt=""
                        class="w-full h-48 sm:h-56 md:h-64 object-cover hover:scale-103 transition duration-300">

                    <div class="py-2 px-3 text-center">
                        <div class="flex justify-center items-center gap-2 sm:gap-3 flex-wrap">
                            <h3 class="text-base sm:text-lg font-bold">{{ service.name }}</h3>
                            <p class="text-base sm:text-lg font-bold">{{ service.brand }}</p>
                        </div>

                        <p class="italic text-sm sm:text-base">{{ service.type }}</p>
                        <p class="text-blue-950 font-semibold text-sm sm:text-base">{{ service.status }}</p>
                    </div>

                    <div class="flex justify-between items-center mb-5 px-4 sm:px-5">
                        <p class="text-lg sm:text-xl font-bold">₱{{ service.price }}</p>
                        <button
                            @click="detailBtn(service.name, service.brand, service.price, service.image, service.status, service.type, service.description, service.features)"
                            class="px-4 sm:px-5 py-2 text-sm sm:text-base text-white bg-sky-500 rounded-lg hover:scale-103 transition duration-300 cursor-pointer">Details</button>
                    </div>
                </div>
            </div>

        </div>
    </section>

</template>