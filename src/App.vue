<script>

import Navbar from './components/Navbar.vue';
import HomeView from './components/HomeView.vue';
import AboutView from './components/AboutView.vue';
import ContactView from './components/ContactView.vue';
import MyBookingsView from './components/MyBookingsView.vue';
import CarCard from './components/CarCard.vue';
import CarDetailsModal from './components/CarDetailsModal.vue';


export default {
  components: {
    Navbar,
    HomeView,
    AboutView,
    ContactView,
    MyBookingsView,
    CarCard,
    CarDetailsModal
  },
  data() {
    return {
      array1: [
        {
          id: 1,
          name: "Fortuner",
          brand: "Toyota",
          price: 900,
          image: "https://i.pinimg.com/736x/74/95/4b/74954b6069be2d5274c7a25a0a056cc7.jpg",
          type: "Mid-size 7-seater SUV",
          status: "Available",
          description: "Experience ultimate comfort, style, and reliability on your next trip with this premium white Toyota Fortuner SUV. Perfect for family vacations, city driving, or long road trips, offering spacious seating and a smooth ride against any backdrop.",
          features: "Spacious interior, powerful performance, modern styling, and top-tier safety."

        },
        {
          id: 2,
          name: "Tanto",
          brand: "Daihatsu ",
          price: 3000,
          image: "https://i.pinimg.com/1200x/00/cf/66/00cf66715afb3e6bf92daeeb3c228f7e.jpg",
          type: "Kei Car",
          status: "Available",
          description: "Enjoy effortless city driving with this compact yet surprisingly spacious Daihatsu Tanto. Designed for maximum practical convenience, high fuel efficiency, and easy parking, it is the ideal choice for quick city errands, daily commutes, or budget-friendly travel.",
          features:"Excellent fuel efficiency, easy maneuvering, high roofline with ample headroom, and convenient sliding side doors."

        },
        {
          id: 3,
          name: "LDV T60S",
          brand: "LDV / Maxus (SAIC Motor) ",
          price: 900,
          image: "https://remunerator.com.au/uploads/media/LDV-eT60-1664547025.jpg",
          type: "Mid-size Pickup Truck / Ute",
          status: "Available",
          description: "Power through any terrain or tackle heavy loads with this rugged, double-cab Maxus T60 pickup truck. Offering a strong combination of utility, performance, and modern comfort, it is the perfect rental for off-road adventures, hauling gear, or long road trips.",
          features: "Spacious double-cab interior, large cargo bed, powerful engine performance, and durable, modern styling."

        },
        {
          id: 4,
          name: "Staria",
          brand: "Hyundai ",
          price: 900,
          image: "https://www.topgear.com/sites/default/files/2021/12/STARIAHighlander2.2DAWD-01.jpg",
          type: "Minivan/ Passenger Van",
          status: "Available",
          description:"Travel in futuristic style and premium comfort with this spacious Hyundai Staria. Designed for large families, group outings, or executive transport, it offers unmatched interior space, panoramic visibility, and a ultra-smooth ride for long journeys.",
          features:"High-capacity seating, futuristic design, spacious luxury cabin, advanced safety technology, and smooth highway performance."
        },
        {
          id: 5,
          name: "Elantra",
          brand: "Nissan ",
          price: 900,
          image: "https://static0.carbuzzimages.com/wordpress/wp-content/uploads/gallery-images/original/1230000/700/1230700.jpg",
          type: "Compact Sedan",
          status: "Available",
          description:"Enjoy a sleek, modern ride with this stylish grey Hyundai Elantra sedan. Offering a perfect blend of fuel efficiency, cutting-edge tech, and premium interior comfort, it is an ideal choice for business trips, weekend getaways, or everyday city driving.",
          features:"Excellent fuel economy, sleek aerodynamic design, comfortable seating for five, and advanced infotainment & safety features."
        },
        {
          id: 6,
          name: "SW4",
          brand: " Toyota",
          price: 900,
          image: "https://i.pinimg.com/1200x/6f/6d/ff/6f6dff376fe0f3b9f600eaf297a5a49b.jpg",
          type: "Mid-size 7-seater SUV",
          status: "Available",
          description:"Experience premium comfort, rugged reliability, and commanding style with this dark metallic Toyota SW4 SUV. Designed for smooth highway cruising as well as challenging off-road terrains, it provides a spacious and refined ride for family road trips, group travel, or executive rental.",
          features:"High ground clearance, spacious cabin seating, powerful performance, and modern safety & convenience features."

        }
      ],
      details: [],
      currentPage: 'home',
      // modal: true
    }
  },
  methods: {
     section(menu) {
      this.currentPage = menu;
    },
 
    openModalAct(service) {
      // this.modal = mod
      this.details.push(service)
    },
    closeModalAct(i) {
      this.modal = i
    },
    closeModal(detail) {
      this.details.splice(detail, 1)
    }

  }


}

</script>


<template>
  <Navbar @goTo="section"  />
  <HomeView v-if="currentPage == 'home'" />
  <AboutView v-if="currentPage == 'about'" />
  <ContactView v-if="currentPage == 'ContactView'" />
  <MyBookingsView v-if="currentPage == 'MyBookingsView'" />
  <CarCard v-if="currentPage == 'CarCard'" :carsPicture="array1" @openModal="openModalAct" />
  <CarDetailsModal @closeToParent="closeModal" :carsPicture="details" />
</template>
