<script>

import Navbar from './components/Navbar.vue';
import HomeView from './components/HomeView.vue';
import AboutView from './components/AboutView.vue';
import ContactView from './components/ContactView.vue';
import MyBookingsView from './components/MyBookingsView.vue';
import CarCard from './components/CarCard.vue';
import CarDetailsModal from './components/CarDetailsModal.vue';
import BookingForm from './components/BookingForm.vue';
import BookingConf from './components/BookingConf.vue';
import Footer from './components/Footer.vue';


export default {
  components: {
    Navbar,
    HomeView,
    AboutView,
    ContactView,
    MyBookingsView,
    CarCard,
    CarDetailsModal,
    BookingForm,
    BookingConf,
    Footer
  },
  data() {
    return {
      array1: [
        {
          id: 1,
          name: "Fortuner",
          brand: "Toyota",
          price: 4000,
          image: "https://i.pinimg.com/736x/74/95/4b/74954b6069be2d5274c7a25a0a056cc7.jpg",
          type: "Mid-size 7-seater SUV",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "Spacious interior, powerful performance, modern styling, and top-tier safety."

        },
        {
          id: 2,
          name: "Tanto",
          brand: "Daihatsu ",
          price: 3500,
          image: "https://i.pinimg.com/1200x/00/cf/66/00cf66715afb3e6bf92daeeb3c228f7e.jpg",
          type: "Kei Car",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "Excellent fuel efficiency, easy maneuvering, high roofline with ample headroom, and convenient sliding side doors."
        },
        {
          id: 3,
          name: "LDV T60S",
          brand: "Maxus (SAIC Motor) ",
          price: 5000,
          image: "https://remunerator.com.au/uploads/media/LDV-eT60-1664547025.jpg",
          type: "Mid-size Pickup Truck / Ute",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "Spacious double-cab interior, large cargo bed, powerful engine performance, and durable, modern styling."
        },
        {
          id: 4,
          name: "Staria",
          brand: "Hyundai ",
          price: 6000,
          image: "https://www.topgear.com/sites/default/files/2021/12/STARIAHighlander2.2DAWD-01.jpg",
          type: "Minivan/ Passenger Van",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "High-capacity seating, futuristic design, spacious luxury cabin, advanced safety technology, and smooth highway performance."
        },
        {
          id: 5,
          name: "Elantra",
          brand: "Nissan ",
          price: 3000,
          image: "https://static0.carbuzzimages.com/wordpress/wp-content/uploads/gallery-images/original/1230000/700/1230700.jpg",
          type: "Compact Sedan",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "Excellent fuel economy, sleek aerodynamic design, comfortable seating for five, and advanced infotainment & safety features."
        },
        {
          id: 6,
          name: "SW4",
          brand: " Toyota",
          price: 4500,
          image: "https://i.pinimg.com/1200x/6f/6d/ff/6f6dff376fe0f3b9f600eaf297a5a49b.jpg",
          type: "Mid-size 7-seater SUV",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "High ground clearance, spacious cabin seating, powerful performance, and modern safety & convenience features."
        },
        {
          id: 7,
          name: "xDrive30 xLine",
          brand: " BMW",
          price: 4800,
          image: "https://assets.autoweek.nl/m/0ctylsvbxuv7_800.jpg",
          type: "Diesel Car",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "The BMW iX1 is an all-electric luxury SUV offering up to 313 horsepower, a 440 km range, and a curved digital interior display."

        },
        {
          id: 8,
          name: " Sprinter",
          brand: "Mercedes-Benz",
          price: 6500,
          image: "https://www.blessthisstuff.com/imagens/listagem/2023/thum_outside-van-mercedes-sprinter-camper.jpeg",
          type: "CamperVan",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "Off-Road Modifications: Heavy-duty front bumper with integrated winch, fog lights, cowl-mounted auxiliary pod lights, and all-terrain tires."
        },
        {
          id: 9,
          name: " Porsche 911 Cabriolet",
          brand: "Sports Car",
          price: 7000,
          image: "https://hips.hearstapps.com/hmg-prod/images/2025-porsche-911-hybrid-142-66560ae0be861.jpg",
          type: "Convertible / Cabriolet",
          status: "Available",
          seaters: "7",
          door: "5",
          gas: "Diesel",
          features: "Performance: Powered by a 3.0-liter twin-turbocharged flat-six rear-mounted engine paired with an 8-speed dual-clutch (PDK) automatic transmission."
        },
      ],
      details: [],
      currentPage: 'home',
      modal: false,
      booking: [],
      confirmedBooking: [],
      modalConfirm: true,
      forBookingFromPrice: [],
    }
  },
  methods: {
    section(menu) {
      this.currentPage = menu;
      this.modal = false
    },

    openModalAct(name, brand, price, image, status, type, seaters, door, gas, features) {
      // this.modal = mod
      this.details.push({ ...name, ...brand, ...price, ...image, ...status, ...type, ...seaters, ...door, ...gas, ...features })
      this.forBookingFromPrice = []
    },
    closeModalAct(i) {
      this.modal = i
    },
    closeModal(detail) {
      this.details.splice(detail, 1)
    },
    showFormAct(price, name, mod) {
      this.modal = mod
      this.closeModal()
      this.currentPage = false
      this.forBookingFromPrice.push({ ...price, ...name })
      this.modal = true
      this.modalConfirm = false
    },
    sendForm(name, number, email, PickLoc, droploc, dateS, pickTime, returnD, typeS, pass, amount, duration, price) {
      this.booking.push({ ...name, ...number, ...email, ...PickLoc, ...droploc, ...dateS, ...pickTime, ...returnD, ...typeS, ...pass, ...amount, ...duration, ...price })
      this.currentPage = false
      this.modal = false
      this.modalConfirm = true
    },
    receiveComplete(name, email, number, PickLoc, droploc, dateS, amount, duration, price) {
      this.confirmedBooking.push({ ...name, ...email, ...number, ...PickLoc, ...droploc, ...dateS, ...amount, ...duration, ...price })
      this.modalConfirm = false
      this.currentPage = 'MyBookingsView'
      this.modal = false

    },
    goToCars(page) {
      this.currentPage = page
    },
    goToModal(index) {
      this.modal = true;
      this.modalConfirm = false
      this.booking.splice(index,1)

    },
    cancelBooking(page) {
      this.currentPage = page
      this.modal = false
    }


  }
}

</script>


<template>
  <Navbar @goTo="section" />
  <HomeView v-if="currentPage == 'home'" />
  <AboutView v-if="currentPage == 'about'" @go-To="goToCars" />
  <ContactView v-if="currentPage == 'ContactView'" />
  <MyBookingsView v-if="currentPage == 'MyBookingsView'" :bookingconfirmed="confirmedBooking"
    :bookingView="forBookingFromPrice" />
  <CarCard v-if="currentPage == 'CarCard'" @openModal="openModalAct" :carsPicture="array1" />
  <CarDetailsModal @showForm="showFormAct" @closeToParent="closeModal" :carsPicture="details" />
  <BookingForm v-if="modal == true" @sent-to="sendForm" :sendPrice="forBookingFromPrice" @cancel="cancelBooking" />
  <BookingConf v-if="modalConfirm" :bookingConfirm="booking" :confirm="forBookingFromPrice" @complete="receiveComplete"
    @gotoModal="goToModal" />
  <Footer />
</template>
