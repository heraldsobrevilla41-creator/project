<script>
import About from './components/About.vue';
import BookNow from './components/BookNow.vue';
import Home from './components/Home.vue';
import Navbar from './components/Navbar.vue';
import Services from './components/Services.vue';
import Shop from './components/Shop.vue';
import Myappointment from './components/Myappointment.vue';
import Promos from './components/Promos.vue';
import Contact from './components/Contact.vue';

export default {
    components: {
        Navbar,
        Home,
        About,
        Shop,
        BookNow,
        Services,
        Myappointment,
        Promos,
        Contact,

    },
    data() {
        return {
            currentTab: 'home',
            showModal: false,
            showappointment: false,
            appointments: [],
            indexofAppointment: 0,
        }
    },
    methods: {
        GoTo(page) {
            this.currentTab = page;
        },
        closeModal(i) {
            this.showModal = i
        },
        openModal(i) {
            this.showModal = i
        }, closeappointment(e) {
            this.showappointment = e
        },
        openappointment(e) {
            this.showappointment = e
        },
        addAppointment(name, mydate, mytime, myplace, myservices) {
            this.appointments.push({ ...name, ...mydate, ...mytime, ...myplace, ...myservices});

        },
        changeIndex(i){
            this.indexofAppointment = i;
        }
    }
}
</script>

<template>
    <Navbar @change-tab="GoTo" @showMod="openModal" @showappoint="openappointment" />
    <Home v-if="currentTab === 'home'" />
    <About v-if="currentTab === 'about'" />
    <Shop v-if="currentTab === 'shop'" />
    <Services v-if="currentTab === 'services'" />
    <Promos v-if="currentTab === 'promos'"/>
    <Contact v-if="currentTab === 'contact'"/>
    <Myappointment v-if="showappointment === true" @close="closeappointment" :appointArray="this.appointments" @appointmentIndex="changeIndex" />
    <BookNow v-if="showModal === true" @close="closeModal" @confirmAppoint="addAppointment" />
</template>
