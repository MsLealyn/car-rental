<script>
    export default {
        data() {
            return {
                
            }
        },
        methods: {
            toCars(page) {
                this.$emit('go-To', page)
            },
            toContact(page) {
                this.$emit('go-To', page)
            }
        }
    }
</script>

<template>
    <section id="about" class="py-12 md:py-20 px-4 sm:px-8 md:px-12 lg:px-20 bg-[#121212] min-h-screen h-auto flex items-center">
        <div class=" mx-auto">
            <div class="mb-12">
            
                <h2 class="text-purple-400 text-base sm:text-lg mb-2" data-aos="fade-down">
                    About Us
                </h2>
                <h3 class="mb-4 text-2xl sm:text-3xl md:text-4xl font-bold text-white section-title" data-aos="fade-down">
                    Your Journey, Our Priority.
                </h3>
                <p class="mb-8 max-w-3xl text-sm sm:text-base text-gray-400 leading-relaxed" data-aos="fade-down">
                    We believe every journey should be comfortable, convenient, and memorable. DSLJ car rental service is
                    dedicated to providing reliable vehicles and a hassle-free booking experience for every traveler.
                </p>

                <div class="grid gap-4 sm:gap-6 grid-cols-2 lg:grid-cols-4">
                   
                    <div class="rounded-lg border border-gray-800 bg-[#1A1A1A] p-4 sm:p-6 text-center hover:scale-105 transition-transform duration-300 cursor-pointer">
                        <h4 class="mb-1 sm:mb-2 text-2xl sm:text-3xl font-bold text-purple-400">11+</h4>
                        <p class="text-xs sm:text-sm md:text-base text-gray-400">Years Service</p>
                    </div>
                 
                    <div class="rounded-lg border border-gray-800 bg-[#1A1A1A] p-4 sm:p-6 text-center hover:scale-105 transition-transform duration-300 cursor-pointer">
                        <h4 class="mb-1 sm:mb-2 text-2xl sm:text-3xl font-bold text-purple-400">15+</h4>
                        <p class="text-xs sm:text-sm md:text-base text-gray-400">Branches Nationwide</p>
                    </div>
                
                    <div class="rounded-lg border border-gray-800 bg-[#1A1A1A] p-4 sm:p-6 text-center hover:scale-105 transition-transform duration-300 cursor-pointer">
                        <h4 class="mb-1 sm:mb-2 text-2xl sm:text-3xl font-bold text-purple-400">500+</h4>
                        <p class="text-xs sm:text-sm md:text-base text-gray-400">Cars Available</p>
                    </div>
              
                    <div class="rounded-lg border border-gray-800 bg-[#1A1A1A] p-4 sm:p-6 text-center hover:scale-105 transition-transform duration-300 cursor-pointer">
                        <h4 class="mb-1 sm:mb-2 text-2xl sm:text-3xl font-bold text-purple-400">50+</h4>
                        <p class="text-xs sm:text-sm md:text-base text-gray-400">Repeated Renters</p>
                    </div>
                </div>
            </div>

         
            <div class="flex flex-col sm:flex-row items-center gap-4 mt-8" data-aos="fade-up">
                <button @click="toCars('CarCard')"
                    class="w-full sm:w-auto text-center cursor-pointer rounded-full bg-purple-600 hover:bg-purple-700 text-white py-3 px-8 transition duration-300">
                    View Cars
                </button>
                <button @click="toContact('ContactView')"
                    class="w-full sm:w-auto text-center cursor-pointer rounded-full border-2 py-3 px-8 border-white text-white hover:bg-white hover:text-purple-900 transition duration-300 ease-in-out">
                    Contact Us
                </button>
            </div>
        </div>
    </section>
</template>