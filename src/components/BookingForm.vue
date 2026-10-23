<script>



</script>

<template>
    <div class="max-w-4xl mx-auto py-10">
        <div class="bg-white rounded-lg border-2 border-blue-400/20 p-6 md:p-8 lg:p-10 shadow-lg">
            <div class="space-y-6">
                <!-- Header -->
                <div class="text-center">
                    <h1 class="text-2xl md:text-3xl font-semibold text-orange-800 uppercase">Car Rental Booking Form</h1><br>
                    <p class="font-small italic">Please complete all sections to confirm your vehicle reservation. Return this form prior to
                        pick-up.</p>
                </div>
                <!-- Personal Information Section -->
                <div class="border-t border-gray-200 pt-6 space-y-6">
                    <h3 class="text-lg font-semibold text-gray-800">1. Renter Information</h3>

                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="space-y-3">
                            <p class="text-gray-700 font-medium block">Full Name:</p>
                            <input type="text" placeholder="Enter your full name"
                                class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                        </div>

                        <div class="space-y-3">
                            <p class="text-gray-700 font-medium block">Phone Number:</p>
                            <input type="tel" placeholder="Enter phone number"
                                class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                        </div>
                    </div>

                    <div class="space-y-3">
                        <p class="text-gray-700 font-medium block">Email Address:</p>
                        <input type="email" placeholder="Enter email address"
                            class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                    </div>
                </div>


                <!-- Pick Up Location -->
                <div class="space-y-3">
                    <label class="text-gray-700 font-medium block">2. RENTAL PERIOD & LOCATION</label><br>
                    <p class="text-gray-700 font-medium block">Pick Up Location:</p>

                    <input type="text" placeholder="Enter Address, Point of Interest, or Airport Code"
                        class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                </div>


                <!-- Drop Off Location -->
                <div class="space-y-3">
                    <p class="text-gray-700 font-medium block">Drop Off Location:</p>
                    <input type="text" placeholder="Enter Address, Point of Interest, or Airport Code"
                        class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors" />
                </div>

                <!-- Date and Time Row -->
                <div class="grid md:grid-cols-2 gap-6">
                    <div class="space-y-3">
                        <label class="text-gray-700 font-medium block">Date of Service:</label>
                        <input type="date" placeholder="Pick Up Date"
                            class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors cursor-pointer" />
                    </div>

                    <div class="space-y-3">
                        <label class="text-gray-700 font-medium block">Pick Up Time:</label>
                        <select
                            class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none appearance-none transition-colors">
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
                <div class="grid md:grid-cols-2 gap-6">
                    <div class="space-y-3">
                        <h1 class="text-gray-700 font-medium block"> Return Date of Service:</h1>
                        <input type="date" placeholder="Return Date"
                            class="bg-gray-50 border border-gray-300 text-gray-900 h-12 w-full rounded-md px-4 placeholder:text-gray-400 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none transition-colors cursor-pointer" />
                    </div>

                    <div class="space-y-3">
                        <label class="text-gray-700 font-medium block">Return Time:</label>
                        <select
                            class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none appearance-none transition-colors">
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







                <div class="border-t border-gray-200 pt-6 space-y-6">
                    <h3 class="text-lg font-semibold text-gray-800">3. VEHICLE PREFERENCE/SELECTED CAR</h3>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="space-y-3">
                            <label class="text-gray-700 font-medium block">Type of Service:</label>
                            <select
                                class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none appearance-none transition-colors">
                                <option value="">- Please Select -</option>
                                <option value="point-to-point">Point to Point</option>
                                <option value="hourly">Hourly Service</option>
                                <option value="airport-transfer">Airport Transfer</option>
                                <option value="wedding">Wedding Service</option>
                                <option value="corporate">Corporate Service</option>
                            </select>
                        </div>

                        <div class="space-y-3">
                            <label class="text-gray-700 font-medium block">Passengers:</label>
                            <select
                                class="bg-gray-50 border border-gray-300 text-gray-700 h-12 w-full rounded-md px-4 focus:border-orange-400 focus:ring-2 focus:ring-orange-200 focus:outline-none appearance-none transition-colors">
                                <option value="">- Please Choose -</option>
                                <option value="1">1 Passenger</option>
                                <option value="2">2 Passengers</option>
                                <option value="3">3 Passengers</option>
                                <option value="4">4 Passengers</option>
                                <option value="5">5 Passengers</option>
                                <option value="6">6 Passengers</option>
                                <option value="7">7 Passengers</option>
                                <option value="8">8 Passengers</option>
                                <option value="9">9+ Passengers</option>
                            </select>
                        </div>
                    </div>


                </div>

                <!-- Submit Button -->
                <div class="pt-6">
                    <button
                        class="w-full bg-orange-800 cursor-pointer hover:bg-orange-600 text-white font-semibold h-14 text-lg rounded-md transition-colors duration-200 shadow-md hover:shadow-lg">
                         Submit
                    </button>
                </div>
            </div>
        </div>
    </div>



</template>