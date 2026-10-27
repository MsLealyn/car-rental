<script>
export default {
    props: ['bookingConfirm'],
    data() {
        return {

            
        }
    },
    methods: {
        viewBookings() {
            this.$emit('displayBooking', this.bookingConfirm)
        },
        viewBookings(fullname, emailAdd, phoneNumber, pickUpLocation, dropOffLocation, DateOfService, AmountPayable, Duration) {
            this.$emit('complete', { name: fullname, email: emailAdd, number: phoneNumber, PickLoc: pickUpLocation, droploc: dropOffLocation, dateS: DateOfService, amount: AmountPayable, duration: Duration })
        }
    }
}

</script>
<template>
    <div v-for="con in bookingConfirm">
        <div class="w-full h-fit pb-10 flex justify-center items-center pl-50 pt-10">
            <div class="w-200 border border-orange-800 shadow-lg rounded-lg">
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
                        <div>
                            <p class="text-gray-700 font-bold">Type of Services:</p>
                            <p class=" px-3 py-3 mb-3 w-90 h-10 rounded-md bg-gray-100 shadow-sm">
                                {{ con.typeS }}
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
                        <div class="flex items-center gap-5">
                            <div>
                                <p class="text-gray-700 font-bold">Amount Payable:</p>
                                <p class=" px-3 py-3 mb-3 w-42 h-10 rounded-md bg-gray-100 shadow-sm">
                                    {{ con.amount }}
                                </p>
                            </div>
                            <div>
                                <p class="text-gray-700 font-bold">Duration:</p>
                                <p class=" px-3 py-3 mb-3 w-42 h-10 rounded-md bg-gray-100 shadow-sm">
                                    {{ con.duration }}
                                </p>
                            </div>
                        </div>

                    </div>
                </div>
                <div class="mb-4 px-10">
                    <label class="block text-gray-700 font-bold mb-2" for="message">
                        Message
                    </label>
                    <textarea
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        id="message" rows="4" placeholder="Enter any additional information"></textarea>
                </div>
                <div class="flex items-center justify-center space-x-2 mb-4">
                    <button @click="viewBookings(con.name, con.email, con.number, con.PickLoc, con.droploc, con.dateS, con.amount, con.duration)"
                        class="bg-orange-800 text-white py-2 px-4 rounded hover:bg-blue-400 focus:outline-none focus:shadow-outline"
                        type="submit">
                        Confirm
                    </button>
                    <button
                        class="bg-orange-800 text-white py-2 px-4 rounded hover:bg-red-600 focus:outline-none focus:shadow-outline"
                        type="submit">
                        Cancel
                    </button>
                </div>
            </div>

        </div>
    </div>
    <!-- <div v-for="con in bookingConfirm"
        class="max-w-md mx-auto mt-10 w-200 bg-white border border-orange-800 shadow-lg rounded-lg overflow-hidden">
        <div class="text-2xl py-4 px-6 bg-blue-400/20 text-orange-800 text-center font-bold uppercase">
            Booking Confirmation
        </div>

        <div class="py-4 px-6">
            <div class="flex justify-center items-center gap-10 bg-black">
                <div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="name">
                            Name
                        </label>
                        <p
                            class="shadow appearance-none border rounded py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.name }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="email">
                            Email
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.email }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="phone">
                            Phone Number
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.number }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="date">
                            Date
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.dateS }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="time">
                            Time
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.pickTime }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="service">
                            Service
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.typeS }}</p>
                    </div>
                </div>
                <div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="name">
                            Name
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.name }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="email">
                            Email
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.email }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="phone">
                            Phone Number
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.number }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="date">
                            Date
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.dateS }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="time">
                            Time
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.pickTime }}</p>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-700 font-bold mb-2" for="service">
                            Service
                        </label>
                        <p
                            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                            {{ con.typeS }}</p>
                    </div>
                </div>
            </div>
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="message">
                    Message
                </label>
                <textarea
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="message" rows="4" placeholder="Enter any additional information"></textarea>
            </div>
            <div class="flex items-center justify-center space-x-2 mb-4">
                <button
                    class="bg-orange-800 text-white py-2 px-4 rounded hover:bg-blue-400 focus:outline-none focus:shadow-outline"
                    type="submit">
                    Confirm
                </button>
                <button
                    class="bg-orange-800 text-white py-2 px-4 rounded hover:bg-red-600 focus:outline-none focus:shadow-outline"
                    type="submit">
                    Cancel
                </button>
            </div>

        </div>
    </div> -->


</template>