<script>
export default {
    props: ['bookingconfirmed', 'bookingView'],
    data() {
        return {

        }
    },
    methods: {

    }
}
</script>

<template>
    <div v-for="(booked, index) in bookingconfirmed" :key="index"
        class="max-w-4xl mx-auto py-6 sm:py-10 px-4 sm:px-6 lg:px-8">
        <div class="bg-white rounded-lg border-2 border-blue-400/20 p-5 sm:p-8 lg:p-10 shadow-lg">
            <div class="space-y-6">
              
                <h1 class="text-xl sm:text-2xl md:text-3xl font-bold text-blue-700 uppercase text-center">My Bookings
                </h1>

                <div class="text-center">
                    <h1 class="text-lg sm:text-2xl font-bold text-orange-800 uppercase">Car Rental Booking Confirmation
                    </h1>
                </div>

            
                <div
                    class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2 text-sm sm:text-base">
                    <p class="text-gray-800 font-bold">Booking Status: <span
                            class="text-green-500 uppercase">Confirmed</span></p>
                    <p class="text-gray-800 font-bold">Booking Reference: BOOK-903649902</p>
                </div>

               
                <div class="border-t border-gray-200 pt-6 space-y-4">
                    <h3 class="text-blue-800 font-bold block">1. RENTER DETAILS</h3>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="space-y-3">
                            <p class="text-gray-700 font-medium block">Full Name: <span
                                    class="font-semibold text-gray-900">{{ booked.name }}</span></p>
                            <p class="text-gray-700 font-medium block">Phone Number: <span
                                    class="font-semibold text-gray-900">{{ booked.number }}</span></p>
                            <p class="text-gray-700 font-medium block truncate">Email Address: <span
                                    class="font-semibold text-gray-900">{{ booked.email }}</span></p>
                        </div>
                    </div>
                </div>

                <div class="space-y-3 border-t border-gray-200 pt-6">
                    <h1 class="text-blue-800 font-bold block">2. RENTAL PERIOD & LOCATION</h1>
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4">
                        <div>
                            <p class="text-gray-700 font-medium block">Pick Up: <span
                                    class="font-semibold text-gray-900">{{ booked.PickLoc }}</span></p>
                            <p class="text-gray-700 font-medium block">Drop Off: <span
                                    class="font-semibold text-gray-900">{{ booked.droploc }}</span></p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-medium block">Agency Location: <span
                                    class="font-semibold text-gray-900">Tagum City</span></p>
                            <p class="text-gray-700 font-medium block">Duration: <span
                                    class="font-semibold text-gray-900">{{ booked.duration }}</span></p>
                        </div>
                    </div>
                </div>

                <div v-for="(addbooking, addIndex) in bookingView" :key="addIndex"
                    class="space-y-3 border-t border-gray-200 pt-6">
                    <h1 class="text-blue-800 font-bold block">3. PAYMENT SUMMARY</h1>
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4">
                        <div>
                            <p class="text-gray-700 font-medium block">Price: ₱<span
                                    class="text-green-700 font-semibold">{{ addbooking.price }}</span>/24hrs</p>
                            <p class="text-gray-700 font-medium block">Service Type: <span
                                    class="font-semibold text-gray-900">{{ addbooking.name }}</span></p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-medium block">Sub-total:</p>
                            <p class="text-gray-700 font-medium block">Total: ₱<span class="text-red-700 font-bold">{{
                                    addbooking.price }}</span></p>
                        </div>
                    </div>
                </div>

                <div class="border-t border-gray-200 pt-6 space-y-3">
                    <h1 class="text-blue-800 font-bold block">IMPORTANT POLICY & REQUIREMENTS</h1>
                    <div class="space-y-2 mb-2">
                        <p class="text-gray-700 italic text-sm">
                            <span class="font-bold">Counter Requirements:</span> Present a valid driver’s license,
                            booking reference number, and a major credit card matching the main driver's name for the
                            security deposit.
                        </p>
                        <p class="text-gray-700 italic text-sm">
                            <span class="font-bold">Cancellation Policy:</span> Free cancellation and rebooking
                            available prior to pick-up for flexible bookings. Prepaid bookings may incur a fee depending
                            on timing.
                        </p>
                        <p class="text-gray-700 italic text-sm">
                            <span class="font-bold">Manage Reservation:</span> You can view, change, or cancel your
                            active status anytime through your account dashboard.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>