<script>
  let sponsors = [
    {
      Name: "Hack Club",
      Logo: "https://assets.hackclub.com/icon-rounded.png",
      Url: "https://hackclub.com",
    },
    {
      Name: "Drew",
      Logo: "https://tbilisi.hackclub.com/drew/avatar.png",
      Url: "https://tbilisi.hackclub.com/drew/",
    },
  ];
</script>

<div id="root">
  <div>
    <main class="mt-50">
      <section class="hero-bg text-white py-20 md:py-32 mt-50">
        <div class="container mx-auto px-6 text-center">
          <h2 class="text-4xl md:text-6xl font-black mb-4 leading-tight">
            It's time to build in Tbilisi.
          </h2>
          <p class="text-lg md:text-xl max-w-3xl mx-auto mb-8 text-blue-100">
            A club for students who love to code, create, and launch their
            ideas. Welcome to the first Hack Club in Tbilisi, where you learn to
            code by building things you're passionate about.
          </p>
          <a
            href="/join"
            class="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg shadow-lg transform transition-transform duration-300 hover:scale-105 hover:bg-gray-100;"
            >Become a Member</a
          >
        </div>
      </section>

      <!-- About Section -->
      <section id="about" class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-6">
          <div class="max-w-4xl mx-auto text-center">
            <h3
              class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-8 text-center;"
            >
              This is your club.
            </h3>
            <p class="text-lg text-gray-600 leading-relaxed">
              Tbilisi Hack Club is a community of young makers, coders, and
              creators . Our philosophy is simple: the best way to learn is by
              doing. We provide the space, community, and support. You bring
              your curiosity and ideas. No experience required.
            </p>
          </div>
        </div>
      </section>

      <!-- What We Do Section -->
      <section id="events" class="py-16 md:py-24">
        <div class="container mx-auto px-6">
          <h1
            class="bg-blue-500 text-white font-bold py-3 px-8 rounded-lg shadow-md transform transition-transform duration-300 hover:scale-105 hover:bg-blue-600;"
            id="whats"
          >
            What's Happening?
          </h1>
          <div class="grid md:grid-cols-3 gap-8">
            <!-- Card 1: Workshops -->
            <div
              class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2;"
            >
              <div class="flex items-center mb-4">
                <svg
                  class="w-12 h-12 text-blue-500 mr-4"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                  ><path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M15 15l-2 5L9 9l11 4-5 2zm0 0l5 5M7.188 2.239l.777 2.897M5.136 7.965l-2.898-.777M13.95 4.05l-2.122 2.122m-5.657 5.656l-2.12 2.122"
                  ></path></svg
                >
                <h4 class="text-xl font-bold text-gray-800">Workshops</h4>
              </div>
              <p class="text-gray-600">
                Dive into new technologies with hands-on, project-based
                workshops. From building your first website to exploring AI and
                game development.
              </p>
            </div>
            <!-- Card 2: Club Meetings -->
            <div
              class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2;"
            >
              <div class="flex items-center mb-4">
                <svg
                  class="w-12 h-12 text-blue-500 mr-4"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                  ><path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"
                  ></path></svg
                >
                <h4 class="text-xl font-bold text-gray-800">Club Meetings</h4>
              </div>
              <p class="text-gray-600">
                Our regular meetups are the heart of the club. Share what you're
                working on, get help from peers, and find collaborators for new
                projects.
              </p>
            </div>
            <!-- Card 3: Hackathons -->
            <div
              class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2;"
            >
              <div class="flex items-center mb-4">
                <svg
                  class="w-12 h-12 text-blue-500 mr-4"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                  ><path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M13 10V3L4 14h7v7l9-11h-7z"
                  ></path></svg
                >
                <h4 class="text-xl font-bold text-gray-800">Hackathons</h4>
              </div>
              <p class="text-gray-600">
                Join high-energy coding events where we'll build amazing
                projects in a single weekend. Food, fun, and friends included.
              </p>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</div>

<style>
  #root {
    display: grid;
    place-content: center;
    height: 100%;
    margin: 0px;
  }
  .hero-bg {
    background: linear-gradient(
      45deg,
      rgb(10, 74, 89) 0%,
      rgb(11, 82, 124) 8.333%,
      rgb(13, 92, 159) 16.667%,
      rgb(16, 104, 194) 25%,
      rgb(18, 118, 227) 33.333%,
      rgb(21, 133, 255) 41.667%,
      rgb(24, 150, 255) 50%,
      rgb(28, 169, 255) 58.333%,
      rgb(31, 188, 255) 66.667%,
      rgb(35, 209, 255) 75%,
      rgb(39, 230, 255) 83.333%,
      rgb(43, 251, 255) 91.667%,
      rgb(47, 255, 255) 100%
    );
  }
  #whats {
    background: linear-gradient(
      45deg,
      rgb(10, 74, 89) 0%,
      rgb(11, 82, 124) 8.333%,
      rgb(13, 92, 159) 16.667%,
      rgb(16, 104, 194) 25%,
      rgb(18, 118, 227) 33.333%,
      rgb(21, 133, 255) 41.667%,
      rgb(24, 150, 255) 50%,
      rgb(28, 169, 255) 58.333%,
      rgb(31, 188, 255) 66.667%,
      rgb(35, 209, 255) 75%,
      rgb(39, 230, 255) 83.333%,
      rgb(43, 251, 255) 91.667%,
      rgb(47, 255, 255) 100%
    );
  }
</style>
