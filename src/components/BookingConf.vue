<script>
export default {
    props: ['bookingConfirm', 'confirm'],
    emits: ['displayBooking', 'complete', 'gotoModal'],
    data() {
        return {


        }
    },
    methods: {
        viewBookings() {
            this.$emit('displayBooking', this.bookingConfirm)
        },
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
    <div v-for="(con, index) in bookingConfirm">
        <div class="w-full h-fit pb-10 flex justify-center items-center pl-50 pt-10 bg-sky-50">
            <div class="w-200 border  border-orange-800 shadow-lg rounded-lg bg-gray-100">
                <div class="text-2xl py-4 px-6 bg-blue-400/20 text-orange-800 text-center font-bold uppercase">
                    Booking Confirmation
                </div>
                <div class="flex justify-center gap-10">
                    <div>
                        <div>
                            <p class="text-gray-700 font-bold">Name:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.name }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Email Address:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.email }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Pick Up Location:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.PickLoc }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Date of Service:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.dateS }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Pick Up Time:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.PickLoc }}
                            </p>
                        </div>
                       
                    </div>

                    <div>
                        <div>
                            <p class="text-gray-700 font-bold">Phone Number:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.number }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Passenger:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.pass }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Drop Off Location:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.droploc }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Return Date of Service:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.returnD }}
                            </p>
                        </div>
                        <div>
                            <p class="text-gray-700 font-bold">Return Time:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.returnT }}
                            </p>
                        </div>
                    </div>
                </div>
                <div v-for="add in confirm">
                    <div class="mb-4 px-10 flex justify-between items-center">
                        <p class="text-gray-700 font-bold">Total Cost: ₱{{ add.price }}</p>
                        <div class="flex items-center gap-5">
                            <div>
                                <p class="text-gray-700 font-bold">Service type: <span class="font-semibold text-gray-900">{{ add.name }}</span> </p>
                            </div>
                        </div>

                    </div>
                </div>
                <div class="flex items-center justify-center space-x-2 mb-4">
                    <button
                        @click="viewBookings(con.name, con.email, con.number, con.PickLoc, con.droploc, con.dateS, con.amount, con.duration, con.price)"
                        class="bg-orange-800 text-white py-2 px-4 rounded hover:bg-blue-400 focus:outline-none focus:shadow-outline"
                        type="submit">
                        Confirm
                    </button>
                    <button @click="deleteBookConfirmation(index)"
                        class="bg-orange-800 text-white py-2 px-4 rounded hover:bg-red-600 focus:outline-none focus:shadow-outline"
                        type="submit">
                        Cancel
                    </button>
                </div>
            </div>

        </div>
    </div>
</template>