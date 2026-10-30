<script>

export default {
    props: ['sendPrice'],
    emits: ['sent-to', 'cancel'],
    data() {
        return {
            fullname: '',
            phoneNumber: '',
            emailAdd: '',
            pickUpLocation: '',
            dropOffLocation: '',
            DateOfService: '',
            PickUptime: '',
            ReturnDate: '',
            returnTime: '',
            typeOfService: '',
            Passenger: '',
            AmountPayable: '',
            Duration: ''
        }
    },
    methods: {
        submitNa() {
            this.$emit('sent-to', {
                name: this.fullname,
                number: this.phoneNumber,
                email: this.emailAdd,
                PickLoc: this.pickUpLocation,
                droploc: this.dropOffLocation,
                dateS: this.DateOfService,
                pickTime: this.PickUptime,
                returnD: this.ReturnDate,
                returnT: this.returnTime,
                typeS: this.typeOfService,
                pass: this.Passenger,
                amount: this.AmountPayable,
                duration: this.Duration,
            })
            alert('submitted');

        },
        cancelNa(page) {
            this.$emit('cancel', page)
        }
    }
}

</script>

<template>
    <div
        class="mx-auto py-6 sm:py-10 w-full h-fit z-10 flex justify-center items-center px-4 sm:px-6 lg:px-8 bg-sky-50">
        <div class="bg-white w-full max-w-4xl rounded-lg border-2 border-blue-400/20 p-5 sm:p-8 lg:p-10 shadow-lg">
            <div class="space-y-6">

                <div class="text-center">
                    <h1 class="text-xl sm:text-2xl md:text-3xl font-semibold text-orange-800 uppercase">
                        Car Rental Booking Form
                    </h1>
                    <p class="font-small italic text-sm sm:text-base mt-2 text-gray-600">
                        Please complete all sections to confirm your vehicle reservation. Return this form prior to
                        pick-up.
                    </p>
                </div>

                <div class="border-t border-gray-200 pt-6 space-y-6">
                    <h3 class="text-lg font-semibold text-gray-800">1. Renter Information</h3>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="space-y-3">
                            <p class="text-gray-700 font-medium block">Full Name:</p>
                            <input v-model="fullname" type="text" placeholder="Enter your full name"
                                class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                        </div>

                        <div class="space-y-3">
                            <p class="text-gray-700 font-medium block">Phone Number:</p>
                            <input v-model="phoneNumber" type="tel" placeholder="Enter phone number"
                                class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                        </div>
                    </div>

                    <div class="space-y-3">
                        <p class="text-gray-700 font-medium block">Email Address:</p>
                        <input v-model="emailAdd" type="email" placeholder="Enter email address"
                            class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                    </div>
                </div>

                <div class="space-y-3">
                    <label class="text-gray-700 font-medium block">2. RENTAL PERIOD & LOCATION</label>
                    <p class="text-gray-700 font-medium block">Pick Up Location:</p>

                    <input v-model="pickUpLocation" type="text"
                        placeholder="Enter Address, Point of Interest, or Airport Code"
                        class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                </div>


                <div class="space-y-3">
                    <p class="text-gray-700 font-medium block">Drop Off Location:</p>
                    <input v-model="dropOffLocation" type="text"
                        placeholder="Enter Address, Point of Interest, or Airport Code"
                        class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                </div>


                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="space-y-3">
                        <label class="text-gray-700 font-medium block">Date of Service:</label>
                        <input v-model="DateOfService" type="date" placeholder="Pick Up Date"
                            class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors cursor-pointer" />
                    </div>

                    <div class="space-y-3">
                        <label class="text-gray-700 font-medium block">Pick Up Time:</label>
                        <select v-model="PickUptime"
                            class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors">
                            <option value="">- Please Select -</option>
                            <option value="00:00">12:00 AM</option>
                            <option value="00:30">12:30 AM</option>
                            <option value="01:00">1:00 AM</option>
                            <option value="01:30">1:30 AM</option>
                            <option value="02:00">2:00 AM</option>
                            <option value="02:30">2:30 AM</option>
                        </select>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="space-y-3">
                        <h1 class="text-gray-700 font-medium block">Return Date of Service:</h1>
                        <input v-model="ReturnDate" type="date" placeholder="Return Date"
                            class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors cursor-pointer" />
                    </div>

                    <div class="space-y-3">
                        <label class="text-gray-700 font-medium block">Return Time:</label>
                        <select v-model="returnTime"
                            class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors">
                            <option value="">- Please Select -</option>
                            <option value="00:00">12:00 AM</option>
                            <option value="00:30">12:30 AM</option>
                            <option value="01:00">1:00 AM</option>
                            <option value="01:30">1:30 AM</option>
                            <option value="02:00">2:00 AM</option>
                            <option value="02:30">2:30 AM</option>
                        </select>
                    </div>
                </div>
                <div v-for="(item, index) in sendPrice" :key="index">
                    <div class="space-y-6">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div class="space-y-3">
                                <label class="text-gray-700 font-medium block">Amount Payable:</label>
                                <div
                                    class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 flex items-center transition-colors">
                                    <p class="text-gray-900">₱{{ item.price }}</p>
                                </div>
                            </div>

                            <div class="space-y-3">
                                <label class="text-gray-700 font-medium block">Duration:</label>
                                <select v-model="Duration"
                                    class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors">
                                    <option value="">- Please Select -</option>
                                    <option value="6 hours">6 hours</option>
                                    <option value="12 hours">12 hours</option>
                                    <option value="24 hours">24 hours</option>
                                    <option value="32 hours">32 hours</option>
                                    <option value="48 hours">48 hours</option>
                                    <option value="60 hours">60 hours</option>
                                    <option value="72 hours">72 hours</option>
                                </select>
                            </div>
                        </div>

                        <div class="border-t border-gray-200 pt-6 space-y-6">
                            <h3 class="text-lg font-semibold text-gray-800">3. VEHICLE PREFERENCE/SELECTED CAR</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div class="space-y-3">
                                    <label class="text-gray-700 font-medium block">Type of Service:</label>
                                    <div
                                        class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 flex items-center transition-colors">
                                        <p class="text-gray-900 truncate">{{ item.name }}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="pt-6 space-y-5">
                    <button @click="submitNa"
                        class="w-full bg-orange-800 cursor-pointer hover:bg-orange-600 text-white font-semibold h-14 text-lg rounded-md transition-colors duration-200 shadow-md hover:shadow-lg">
                        Submit
                    </button>
                    <button @click="cancelNa('CarCard')"
                        class="w-full bg-orange-800 cursor-pointer hover:bg-orange-600 text-white font-semibold h-14 text-lg rounded-md transition-colors duration-200 shadow-md hover:shadow-lg">
                        Cancel
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>