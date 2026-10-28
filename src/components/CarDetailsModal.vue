<script>
import MyBookingsView from './MyBookingsView.vue';

export default {
    props: ['carsPicture'],
    emits: ['closeToParent', 'showForm'],
    data() {
        return {

        }
    },
    methods: {
        // detailBtnclose(mod) {
        //     this.$emit('closeModal', mod)
        // },
        remove(detail) {
            this.$emit('closeToParent', detail)
        },
        bookNow(i, n, modal) {
            this.$emit('showForm', { price: i, name: n }, modal)
        }
    }
}
</script>

<template>
    <div v-for="detail in carsPicture" :key="detail.id"
        class="fixed inset-0 z-50 overflow-y-auto flex items-center justify-center p-4">
     
        <div class="fixed inset-0 bg-black/10 backdrop-blur-2xl"></div>

        <div class="relative z-10 w-full max-w-4xl my-auto">
            <div class="grid grid-cols-1">
                <div class="bg-[#87d8f3] w-full h-fit pb-6 pt-2 px-4 sm:px-6 rounded-2xl shadow-xl">
                 
                    <div class="flex justify-end p-2">
                        <button @click="remove"
                            class="cursor-pointer font-bold text-xl hover:text-red-500 transition-colors">X</button>
                    </div>

                  
                    <div class="flex flex-col md:flex-row justify-center items-center gap-6 md:gap-10">
                        <img class="w-full md:w-90 h-64 sm:h-80 rounded-3xl object-cover" :src="detail.image"
                            alt="Car Picture">

                        <div class="w-full md:w-80 space-y-3 text-left">
                            <h1 class="text-xl sm:text-2xl font-bold font-arial">{{ detail.name }} {{ detail.brand }}
                            </h1>
                            <h1 class="text-sm font-arial">
                                <span class="font-bold">Description:</span> {{ detail.description }}
                            </h1>
                            <h1 class="text-sm font-arial">
                                <span class="font-bold">Key Features:</span> {{ detail.features }}
                            </h1>
                            <div>
                                <p class="font-arial font-bold text-md">
                                    Price: <span class="font-semibold">₱{{ detail.price }}.00 /24hrs</span>
                                </p>
                                <button @click="bookNow(detail.price, detail.name, true)"
                                    class="bg-[#0d4976e0] hover:bg-[#0d4976] px-8 py-2 rounded-full text-white font-arial font-semibold mt-4 sm:mt-5 transition-colors w-full sm:w-auto">
                                    BOOK
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>