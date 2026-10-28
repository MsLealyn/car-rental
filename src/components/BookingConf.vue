<script>
export default {
    props: ['bookingConfirm', 'confirm'],
    emits: ['displayBooking', 'complete', 'gotoModal'],
    data() {
        return {

        }
    },
    methods: {
        viewBookings(fullname, emailAdd, phoneNumber, pickUpLocation, dropOffLocation, DateOfService, AmountPayable, Duration, i) {
            this.$emit('complete', { name: fullname, email: emailAdd, number: phoneNumber, PickLoc: pickUpLocation, droploc: dropOffLocation, dateS: DateOfService, amount: AmountPayable, duration: Duration, price: i })
        },
        deleteBookConfirmation(page) {
            this.$emit('gotoModal', page)
        },
    }
}
</script>

<template>
    <div v-for="(con, index) in bookingConfirm" :key="index">
        <div class="w-full h-fit pb-10 flex justify-center items-center px-4 sm:px-6 lg:px-8 pt-10 bg-sky-50">
            <div class="w-full max-w-3xl border border-orange-800 shadow-lg rounded-lg bg-gray-100 overflow-hidden">
              
                <div class="text-xl sm:text-2xl py-4 px-6 bg-blue-400/20 text-orange-800 text-center font-bold uppercase">
                    Booking Confirmation
                </div>

            
                <div class="p-4 sm:p-8 grid grid-cols-1 md:grid-cols-2 gap-6">
                
                    <div class="space-y-3">
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Name:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.name }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Email Address:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.email }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Pick Up Location:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.PickLoc }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Date of Service:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.dateS }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Pick Up Time:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.PickLoc }}
                            </p>
                        </div>
                    </div>

               
                    <div class="space-y-3">
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Phone Number:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.number }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Passenger:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.pass }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Drop Off Location:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.droploc }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Return Date of Service:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.returnD }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold text-sm sm:text-base">Return Time:</p>
                            <p class="px-3 py-2.5 w-full rounded-md bg-white border border-gray-200 shadow-sm text-sm sm:text-base truncate">
                                {{ con.returnT }}
                            </p>
                        </div>
                    </div>
                </div>

             
                <div v-for="(add, addIndex) in confirm" :key="addIndex">
                    <div class="mb-4 px-4 sm:px-8 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2">
                        <p class="text-gray-700 font-bold text-base sm:text-lg">Total Cost: ₱{{ add.price }}</p>
                        <div class="flex items-center gap-5">
                            <div>
                                <p class="text-gray-700 font-bold text-sm sm:text-base">Service type: <span class="font-semibold text-gray-900">{{ add.name }}</span></p>
                            </div>
                        </div>
                    </div>
                </div>

             
                <div class="flex items-center justify-center space-x-4 mb-6 px-4">
                    <button
                        @click="viewBookings(con.name, con.email, con.number, con.PickLoc, con.droploc, con.dateS, con.amount, con.duration, con.price)"
                        class="bg-orange-800 text-white py-2.5 px-6 rounded hover:bg-blue-400 focus:outline-none focus:shadow-outline font-semibold transition-colors cursor-pointer"
                        type="submit">
                        Confirm
                    </button>
                    <button @click="deleteBookConfirmation(index)"
                        class="bg-orange-800 text-white py-2.5 px-6 rounded hover:bg-red-600 focus:outline-none focus:shadow-outline font-semibold transition-colors cursor-pointer"
                        type="submit">
                        Cancel
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>