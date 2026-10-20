<script>


export default {
  data() {
    return {
      fullname: '',
      fulldate: '',
      fulltime: '',
      place: '',
      
    }
  },
  methods: {
    xbnt(i) {
      this.$emit('close', i);
    },
    confirmBtn() {
      if (this.fullname !== '' && this.fulldate !== '' && this.fulltime !== '' && this.place !== '') {
        this.$emit('confirmAppoint', { name: this.fullname, mydate: this.fulldate, mytime: this.fulltime, myplace: this.place, myservices: this.Services, },
          alert('successfully Booked'),);
          this.$emit('close', false);
      }
      else{
        alert('Fill up the ramaining details');
      }
    }
  }
}

</script>

<template>
  <div class="fixed inset-0 z-50 flex items-center justify-center bg-black/60 p-4">
    <div
      class="bg-gradient-to-br from-purple-50 to-indigo-50 rounded-xl max-w-lg w-full p-6 relative shadow-2xl border border-white">

      <button @click="xbnt(false)" class="absolute top-4 right-4 bg-gray-900 text-white w-7 h-7 rounded-full flex items-center justify-center
        text-xs font-bold hover:bg-gray-700">
        ✕
      </button>

      <div class="mb-5">
        <h3 class="text-xl font-serif font-bold text-[#1a1b4b]">Book Your Visit</h3>
        <p class="text-xs text-gray-600">Fill out details below to secure your beauty slot.</p>
      </div>

      <div class="space-y-4">
        <div>
          <label class="block text-xs font-bold text-gray-700 mb-1 uppercase">Full Name:</label>
          <input v-model="fullname" type="text" required
            class="w-full bg-white px-3 py-2 rounded border border-gray-300 text-sm focus:ring-2 focus:ring-[#1a1b4b] focus:outline-none"
            placeholder="Enter your full name" />
        </div>

        <div class="grid grid-cols-2 gap-4">
          <div>
            <label class="block text-xs font-bold text-gray-700 mb-1 uppercase">Appointment Date:</label>
            <input v-model="fulldate" type="date" required
              class="w-full bg-white px-3 py-2 rounded border border-gray-300 text-sm focus:outline-none" />
          </div>
          <div>
            <label class="block text-xs font-bold text-gray-700 mb-1 uppercase">Time Slot:</label>
            <select v-model="fulltime" required
              class="w-full bg-white px-3 py-2 rounded border border-gray-300 text-sm focus:outline-none">
              <option value="">Select Time</option>
              <option value="10:00 AM">10:00 AM</option>
              <option value="1:00 PM">1:00 PM</option>
              <option value="4:00 PM">4:00 PM</option>
            </select>
          </div>
        </div>

        <div>
          <h1 class="block text-xs font-bold text-gray-700 mb-1 uppercase">Choose Branch:</h1>
          <select v-model="place" required
            class="w-full bg-white px-3 py-2 rounded border border-gray-300 text-sm focus:outline-none">
            <option value="">Select Salon Location</option>
            <option value="Downtown">Downtown</option>
            <option value="Westside">Westside</option>
            <option value="North End">North End</option>
          </select>
        </div>

        <div>
          <h1 class="block text-xs font-bold text-gray-700 mb-1 uppercase">Select Services:</h1>
          <select v-model="services" 
            class="w-100 bg-white px-3 py-2 rounded border border-gray-300 text-sm focus:outline-none">
            <option value="Select Services">Select Services</option>
            <option value="Haircut & Styling">Haircut & Styling</option>
            <option value="Hair Coloring">Hair Coloring</option>
            <option value="Treatment">Treatment</option>
            <option value="Mani & Pedi">Shampoo & Blowdry </option>
            <option value="Mani & Pedi">Hair Color</option>
            <option value="Mani & Pedi">Treatment</option>
            <option value="Mani & Pedi">Rebonding</option>
            <option value="Mani & Pedi">Relaxing</option>
            <option value="Mani & Pedi">Perm</option>
            <option value="Mani & Pedi">Hair & Make-up</option>
            <option value="Mani & Pedi">Full Make-up</option>
            <option value="Mani & Pedi">Air Brush</option>
            <option value="Mani & Pedi">Elaborate Upstyle</option>
            <option value="Mani & Pedi">Upper Lip</option>
            <option value="Mani & Pedi">Lower Lip</option>
            <option value="Mani & Pedi">Bikini Wax</option>
            <option value="Mani & Pedi">Brazilian Wax</option>
            <option value="Mani & Pedi">Manicure</option>
            <option value="Mani & Pedi">Pedicure</option>
            <option value="Mani & Pedi">Gel Polish</option>
            <option value="Mani & Pedi">Gel Polish Removal</option>
            <option value="Mani & Pedi">Nail Extension</option>
            <option value="Mani & Pedi">Foot Spa</option>
            <option value="Mani & Pedi">Foot Reflex</option>s
          </select>
        </div>

        <div class="flex items-center justify-end space-x-3 pt-3">
          <button type="button" @click="$emit('close')"
            class="px-4 py-2 text-xs text-gray-600 hover:text-gray-800">Cancel</button>
          <button @click="confirmBtn"
            class="bg-pink-600 hover:bg-pink-700 text-white font-medium text-xs px-6 py-2.5 rounded shadow transition">Confirm
            Appointment</button>
        </div>
      </div>
    </div>
  </div>
</template>