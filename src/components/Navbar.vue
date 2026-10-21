<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        setActiveTab(page) {
            this.$emit('change-tab', page);
        },
        openModal(i) {
            this.$emit('showMod', i);
        },
        openappointment(e) {
            this.$emit('showappoint', e);
        }
    }
}
</script>

<template>
    <header class="sticky top-0 z-50 bg-[#D9D9D9]  shadow-md justify-between">
        <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8 h-20 flex items-center justify-around ">

            <!-- Logo -->
            <div class="flex items-center space-x-2 cursor-pointer" @click="$emit('change-tab', 'home')">
                <div class="text-center">
                    <img src="../assets/Jurald-logo.png" alt="David's Salon Logo" class="h-25 w-auto animate-pulse" />
                </div>
            </div>

            <!-- Navigation Links -->
            <nav class="hidden md:flex items-center space-x-8 text-sm font-medium text-gray-700">
                <button @click="setActiveTab('home')"
                    :class="{ 'text-purple-900 font-bold border-b-2 border-purple-900 pb-1': activeTab === 'home' }">HOME</button>
                <button @click="setActiveTab('about')"
                    :class="{ 'text-purple-900 font-bold border-b-2 border-purple-900 pb-1': activeTab === 'about' }">ABOUT</button>
                <button @click="setActiveTab('shop')"
                    :class="{ 'text-purple-900 font-bold border-b-2 border-purple-900 pb-1': activeTab === 'shop' }">SHOP</button>
                <button @click="setActiveTab('services')"
                    :class="{ 'text-purple-900 font-bold border-b-2 border-purple-900 pb-1': activeTab === 'services' }">SERVICES</button>
                <button @click="setActiveTab('promos')"
                    :class="{ 'text-purple-900 font-bold border-b-2 border-purple-900 pb-1': activeTab === 'promos' }">PROMOS</button>
                <button @click="setActiveTab('contact')"
                    :class="{ 'text-purple-900 font-bold border-b-2 border-purple-900 pb-1': activeTab === 'contact' }">CONTACT</button>
            </nav>
            <div>
                <button @click="openappointment(true)"
                    class="bg-linear-to-r/increasing from-indigo-500 to-teal-400 hover:bg-pink-700 text-black font-medium px-6 py-2.5 rounded-full shadow transition-all">
                    My Appointment
                </button>
            </div>
            <div>
                <button @click="openModal(true)"
                    class="bg-linear-to-r/increasing from-indigo-500 to-teal-400 hover:bg-pink-700 text-black font-medium px-6 py-2.5 rounded-full shadow transition-all">
                    Book Now
                </button>
            </div>
        </div>
    </header>
</template>