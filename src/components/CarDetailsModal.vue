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
                <div class="bg-[#87d8f3] w-fit h-fit pb-6 pt-2 px-4 sm:px-6 rounded-2xl shadow-xl">

                    <div class="flex justify-end p-2">
                        <button @click="remove"
                            class="cursor-pointer font-bold text-xl hover:text-red-500 transition-colors">X</button>
                    </div>


                    <div class="flex flex-col md:flex-row lg:w-fit justify-center items-center gap-6 md:gap-10">
                        <img class="w-full md:w-90 h-64 sm:h-80 rounded-3xl object-cover" :src="detail.image"
                            alt="Car Picture">

                        <div class="w-full md:w-80 space-y-3 text-left">
                            <h1 class="text-xl sm:text-2xl font-bold font-arial">{{ detail.name }} {{ detail.brand }}
                            </h1>
                            <h1 class="text-lg font-arial flex gap-2">
                                <p class="font-bold"> Features:</p> {{ detail.features }}
                            </h1>
                            <h1 class="text-lg font-arial flex items-center gap-2">
                                <svg class="w-7 h-7" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                                    <path fill="rgb(15, 15, 15)"
                                        d="M320 80C377.4 80 424 126.6 424 184C424 241.4 377.4 288 320 288C262.6 288 216 241.4 216 184C216 126.6 262.6 80 320 80zM96 152C135.8 152 168 184.2 168 224C168 263.8 135.8 296 96 296C56.2 296 24 263.8 24 224C24 184.2 56.2 152 96 152zM0 480C0 409.3 57.3 352 128 352C140.8 352 153.2 353.9 164.9 357.4C132 394.2 112 442.8 112 496L112 512C112 523.4 114.4 534.2 118.7 544L32 544C14.3 544 0 529.7 0 512L0 480zM521.3 544C525.6 534.2 528 523.4 528 512L528 496C528 442.8 508 394.2 475.1 357.4C486.8 353.9 499.2 352 512 352C582.7 352 640 409.3 640 480L640 512C640 529.7 625.7 544 608 544L521.3 544zM472 224C472 184.2 504.2 152 544 152C583.8 152 616 184.2 616 224C616 263.8 583.8 296 544 296C504.2 296 472 263.8 472 224zM160 496C160 407.6 231.6 336 320 336C408.4 336 480 407.6 480 496L480 512C480 529.7 465.7 544 448 544L192 544C174.3 544 160 529.7 160 512L160 496z" />
                                </svg>
                                <p class="font-bold"> Seaters:</p> {{ detail.seaters }}
                            </h1>
                            <h1 class="text-lg font-arial flex items-center gap-2">
                                <svg class="w-7 h-7" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                                    <path fill="rgb(15, 15, 15)"
                                        d="M384 128L448 128L448 544C448 561.7 462.3 576 480 576L512 576C529.7 576 544 561.7 544 544C544 526.3 529.7 512 512 512L512 128C512 92.7 483.3 64 448 64L352 64L352 64L192 64C156.7 64 128 92.7 128 128L128 512C110.3 512 96 526.3 96 544C96 561.7 110.3 576 128 576L352 576C369.7 576 384 561.7 384 544L384 128zM256 320C256 302.3 270.3 288 288 288C305.7 288 320 302.3 320 320C320 337.7 305.7 352 288 352C270.3 352 256 337.7 256 320z" />
                                </svg>
                                <p class="font-bold"> Seaters:</p> {{ detail.door }}
                            </h1>
                            <h1 class="text-lg font-arial flex items-center gap-2">
                                <svg class="w-7 h-7" xmlns="http://www.w3.org/2000/svg"
                                    viewBox="0 0 640 640">
                                    <path fill="rgb(15, 15, 15)"
                                        d="M96 128C96 92.7 124.7 64 160 64L320 64C355.3 64 384 92.7 384 128L384 320L392 320C440.6 320 480 359.4 480 408L480 440C480 453.3 490.7 464 504 464C517.3 464 528 453.3 528 440L528 286C500.4 278.9 480 253.8 480 224L480 164.5L454.2 136.2C445.3 126.4 446 111.2 455.8 102.3C465.6 93.4 480.8 94.1 489.7 103.9L561.4 182.7C570.8 193 576 206.4 576 220.4L576 440C576 479.8 543.8 512 504 512C464.2 512 432 479.8 432 440L432 408C432 385.9 414.1 368 392 368L384 368L384 529.4C393.3 532.7 400 541.6 400 552C400 565.3 389.3 576 376 576L104 576C90.7 576 80 565.3 80 552C80 541.5 86.7 532.7 96 529.4L96 128zM160 144L160 240C160 248.8 167.2 256 176 256L304 256C312.8 256 320 248.8 320 240L320 144C320 135.2 312.8 128 304 128L176 128C167.2 128 160 135.2 160 144z" />
                                </svg>
                                <p class="font-bold"> Seaters:</p> {{ detail.gas }}
                            </h1>

                            <div>
                                <p class="font-arial font-bold text-lg">
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