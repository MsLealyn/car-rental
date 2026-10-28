<script>
    export default{
        props: ['bookingconfirmed', 'bookingView'],
        data(){
            return{

            }
        },
        methods:{

        }
    }


</script>

<template>
    <div v-for="booked in bookingconfirmed"  class="max-w-4xl mx-auto py-10 pl-50">
        <div  class="bg-white rounded-lg border-2 border-blue-400/20 p-6 md:p-8 lg:p-10 shadow-lg">
            <div class="space-y-6">
                <h1 class="text-2xl md:text-3xl font-bold text-blue-700 uppercase text-center">My Bookings</h1>
                <div class="text-center">
                    <h1 class="text-2xl font-bold text-orange-800 uppercase">Car Rental Booking Confirmation</h1>
                </div>
                <div class="flex justify-between">
                    <p class="text-gray-800 font-bold">Booking Status: <span class="text-green-500 uppercase">Confirmed</span></p>
                    <p class="text-gray-800 font-bold">Booking Reference: BOOK-903649902</p>
                </div>
                <!-- Personal Information Section -->
                <div class="border-t border-gray-200 pt-6 space-y-6">
                    <h3 class="text-blue-800 font-bold block">1. RENTER DETAILS</h3>

                    <div class="grid md:grid-cols-2 gap-6">


                        <div class="space-y-3">
                            <p class="text-gray-700 font-medium block">Phone Number: {{ booked.number }}</p>
                            <p class="text-gray-700 font-medium block">Email Address: {{ booked.email }}</p>
                            <p class="text-gray-700 font-medium block">Full Name: {{ booked.name }}</p>



                        </div>
                    </div>

                </div>

                <div class="space-y-3">
                    <h1 class="text-blue-800 font-bold block">2. RENTAL PERIOD & LOCATION</h1>
                    <div class="flex justify-between items-center pr-50">
                        <div>
                            <p class="text-gray-700 font-medium block">Pick Up: {{ booked.PickLoc }}</p>
                            <p class="text-gray-700 font-medium block">Drop Off: {{ booked.droploc }}</p>
                        </div>
                        <div class="">
                            <p class="text-gray-700 font-medium block">Agency Location: Tagum City</p>
                            <p class="text-gray-700 font-medium block">Duration: {{ booked.duration }}</p>
                        </div>
                    </div>


                </div>

                <div v-for="addbooking in bookingView" class="space-y-3">
                    <h1 class="text-blue-800 font-bold block">3. PAYMENT SUMMARY</h1>
                    <div class="flex justify-between items-center pr-63">
                        <div>
                            <p class="text-gray-700 font-medium block">Price:  ₱<span class="text-green-700">{{ addbooking.price }}</span>/24hrs</p>
                            <p class="text-gray-700 font-medium block">Service Type: {{ addbooking.name }}</p>
                        </div>
                        <div >
                            <p class="text-gray-700 font-medium block">Sub-total:</p>
                            <p class="text-gray-700 font-medium block">Total: ₱<span class="text-red-700">{{ addbooking.price }}</span></p>
                        </div>

                    </div>

                </div>
                <h1 class="text-blue-800 font-bold block">IMPORTANT POLICY & REQUIREMENTS</h1>
                <div class="mb-2">
                    <p class="text-gray-700 italic text-sm"><span class="font-bold">Counter Requirements:</span> Present
                        a valid
                        driver’s license, booking
                        reference number, and a major credit
                        card matching the main driver's name for the security deposit.
                    </p>
                    <p class="text-gray-700 italic text-sm"><span class="font-bold">Cancellation Policy:</span> Free
                        cancellation and
                        rebooking available prior to pick-up for flexible
                        bookings. Prepaid bookings may incur a
                        fee depending on timing.
                    </p>
                    <p class="text-gray-700 italic text-sm"><span class="font-bold">Manage Reservation:</span> You can
                        view, change, or
                        cancel your active status anytime through your account dashboard.</p>

                </div>
            </div>
        </div>
    </div>



</template>