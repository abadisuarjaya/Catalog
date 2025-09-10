<template>
  <div>
    <!-- Hero Section -->
    <section
      class="relative bg-gray-100 min-w-screen lg:min-h-screen flex justify-center items-center flex-col overflow-hidden"
    >
      <div
        class="w-full h-full absolute overflow-hidden flex justify-center items-center bg-cover bg-[url(https://media.johnlewiscontent.com/i/johnlewis/Small-space-furniture-lead)]"
      ></div>
      <UContainer
        class="py-5 text-center z-10 rounded-xl backdrop-blur-xs lg:backdrop-blur-sm text-white flex justify-center items-center flex-col"
      >
        <img src="/images/logo/asj.png" alt="Abadi Suar Jaya" class="w-48" />
        <h1 class="text-3xl md:text-5xl font-bold mb-4">Furniture Elegan, Nyaman, & Berkualitas</h1>
        <p class="mb-6">
          Kami menyediakan berbagai pilihan meubel untuk rumah dan kantor dengan desain modern dan harga bersahabat.
        </p>
        <UButton size="lg" to="/catalog" variant="solid" color="primary"> Lihat Katalog </UButton>
      </UContainer>
    </section>

    <!-- Language switch -->
    <div class="flex w-full h-max mt-10 justify-center items-center gap-2 text-sm">
      <div class="flex gap-2 w-max justify-center items-center">
        <div class="w-24 text-end">English</div>
        <USwitch v-model="indonesian" />
        <div class="w-24 text-start">Indonesian</div>
      </div>
    </div>

    <!-- Tentang Usaha -->
    <section id="tentang" class="py-10">
      <UContainer>
        <h2 v-if="indonesian" class="text-2xl font-semibold mb-4 text-center">Tentang Kami</h2>
        <h2 v-else class="text-2xl font-semibold mb-4 text-center">About Us</h2>
        <div v-if="indonesian" class="max-w-3xl mx-auto text-center flex flex-col gap-2">
          <div class="font-bold text-xl">Salah satu meubel furniture terbaik di Kabupaten Banyuwangi.</div>
          <div>
            Meubel Abadi Suar Jaya berdiri sejak Tahun 2010,berkomitmen menyediakan semua produk furniture berkualitas
            tinggi dengan harga terjangkau seperti set meja makan, meja kantor, berbagai macam kursi dan kita siap
            menerima berbagai pesanan sesuai kebutuhan anda. Dengan tenaga kerja profesional, kami memastikan setiap
            produk dibuat dengan teliti. Kenyamanan dan Kepuasan Anda adalah Prioritas Kami.
          </div>
          <div>
            Oleh karena itu, kami berkomitmen untuk memberikan layanan terbaik. Segera kunjungi toko kami, Dapatkan
            penawaran promo terbaik untuk Anda.
          </div>
        </div>
        <div v-else class="max-w-3xl mx-auto text-center flex flex-col gap-2 mt-10">
          <div class="font-bold text-xl">One of the best furniture manufacturers in Banyuwangi Regency.</div>
          <div>
            Meubel Abadi Suar Jaya, established in 2010, is committed to providing high-quality furniture at affordable
            prices, including dining table sets, office desks, and a variety of chairs. We are ready to accept various
            orders according to your needs. With a professional workforce, we ensure that each product is meticulously
            crafted. Your comfort and satisfaction are our priority.
          </div>
          <div>
            Therefore, we are committed to providing the best service. Visit our store now and Get the Best Promotional
            Offers.
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Keunggulan Usaha -->
    <section class="bg-gray-50 py-16">
      <UContainer>
        <h2 v-if="indonesian" class="text-2xl font-semibold mb-10 text-center">Kenapa Memilih Kami?</h2>
        <h2 v-else class="text-2xl font-semibold mb-10 text-center">Why Choose Us?</h2>
        <div
          v-for="item in indonesian ? kelebihan : advantages"
          :key="item.title"
          class="p-6 my-2 bg-white backdrop-blur-lg rounded-lg shadow text-center"
        >
          <div class="text-4xl mb-4">{{ item.icon }}</div>
          <h3 class="font-bold mb-2">{{ item.title }}</h3>
          <p class="text-gray-600">{{ item.description }}</p>
        </div>
      </UContainer>
    </section>
  </div>
</template>

<script setup>
definePageMeta({
  layout: "home",
});

const indonesian = ref(false);

const kelebihan = ref([
  {
    icon: "🪵",
    title: "Bahan Berkualitas",
    description: "Menggunakan kayu pilihan dan material terbaik.",
  },
  {
    icon: "🎨",
    title: "Desain Modern",
    description: "Mengikuti tren terbaru untuk keindahan rumah Anda.",
  },
  {
    icon: "⚡",
    title: "Pengiriman Cepat",
    description: "Proses pengiriman aman dan tepat waktu.",
  },
]);
const advantages = ref([
  {
    icon: "🪵",
    title: "High Quality",
    description: "Crafted from selected wood and premium materials.",
  },
  {
    icon: "🎨",
    title: "Modern Design",
    description: "Always following the latest trends to beautify your home.",
  },
  {
    icon: "⚡",
    title: "Fast Delivery",
    description: "Safe, reliable, and on-time shipping process.",
  },
]);
</script>

<style scoped>
.bg-primary-500 {
  background-color: #1e88e5;
}
.text-primary-500 {
  color: #1e88e5;
}
</style>
