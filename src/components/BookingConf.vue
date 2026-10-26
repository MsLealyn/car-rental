<script>


</script>
<template>
    <div class="max-w-md mx-auto mt-10 bg-white border border-orange-800 shadow-lg rounded-lg overflow-hidden">
        <div class="text-2xl py-4 px-6 bg-blue-400/20 text-orange-800 text-center font-bold uppercase">
            Booking Confirmation
        </div>

        <form class="py-4 px-6" action="" method="POST">
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="name">
                    Name
                </label>
                <input
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="name" type="text" placeholder="Enter your name">
            </div>
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="email">
                    Email
                </label>
                <input
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="email" type="email" placeholder="Enter your email">
            </div>
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="phone">
                    Phone Number
                </label>
                <input
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="phone" type="tel" placeholder="Enter your phone number">
            </div>
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="date">
                    Date
                </label>
                <input
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="date" type="date" placeholder="Select a date">
            </div>
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="time">
                    Time
                </label>
                <input
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="time" type="time" placeholder="Select a time">
            </div>
            <div class="mb-4">
                <label class="block text-gray-700 font-bold mb-2" for="service">
                    Service
                </label>
                <select
                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                    id="service" name="service">
                    <option value="">- Please Select -</option>
                    <option value="point-to-point">Point to Point</option>
                    <option value="hourly">Hourly Service</option>
                    <option value="airport-transfer">Airport Transfer</option>
                    <option value="wedding">Wedding Service</option>
                    <option value="corporate">Corporate Service</option>
                </select>
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

        </form>
    </div>


</template>