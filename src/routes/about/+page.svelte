<script lang="js">
  // Data for Sponsors and Team members
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

  let team = [
    {
      Name: "Drew",
      Avatar: "https://tbilisi.hackclub.com/drew/avatar.png",
      Url: "https://tbilisi.hackclub.com/drew/",
    },
    {
      Name: "Boris Mirakov",
      Avatar: "https://tbilisi.hackclub.com/bormir/avatar.png",
      Url: "https://tbilisi.hackclub.com/bormir/",
    },
    {
      Name: "Zlata Chernova",
      Avatar: "https://tbilisi.hackclub.com/zlataponchikk/avatar.png",
      Url: "https://tbilisi.hackclub.com/zlataponchikk",
    },
  ];

  // Fallback image handler
  function handleImgError(event, name) {
    event.target.src = `https://placehold.co/96x96/e2e8f0/64748b?text=${name.charAt(0)}`;
  }
</script>

<svelte:head>
  <title>Tbilisi Hack Club</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800;900&display=swap"
    rel="stylesheet"
  />
</svelte:head>

<main>
  <!-- Hero Section -->
  <section class="hero-bg text-white py-20 md:py-32">
    <div class="container mx-auto px-6 text-center">
      <h1 class="text-4xl md:text-6xl font-black mb-4 leading-tight">
        Welcome to Tbilisi Hack Club: <br class="hidden md:block" />
        <span class="text-blue-200">Where Your Ideas Take Flight</span> 🚀
      </h1>
      <p class="text-lg md:text-xl max-w-3xl mx-auto mb-8 text-blue-100">
        In a city buzzing with ancient history and a vibrant, emerging tech
        scene, a new chapter is unfolding. Welcome to Tbilisi Hack Club, a space
        for young creators, coders, and innovators to come together, learn, and
        build amazing things.
      </p>
      <a
        href="#join"
        class="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg shadow-lg transform transition-transform duration-300 hover:scale-105 hover:bg-gray-100"
        >Get Involved</a
      >
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="py-16 md:py-24 bg-white">
    <div class="container mx-auto px-6">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-8">
          What is a <span class="text-blue-600">Hack Club?</span>
        </h2>
        <p class="text-lg text-gray-600 leading-relaxed mb-4">
          Forget the stereotypes of stuffy classrooms and rigid curriculums. A
          Hack Club is a dynamic, hands-on environment where you learn by doing.
          It's a place to tinker, to experiment, to break things and then build
          them back better. Here, you'll find a supportive community of peers
          who share your passion for technology.
        </p>
        <p class="text-lg text-gray-600 leading-relaxed">
          Our club is for <strong class="text-gray-900">everyone</strong>, from
          absolute beginners to seasoned young developers. We believe that the
          most powerful learning happens when you're driven by curiosity. We're
          part of a worldwide network of student-led coding clubs, all fueled by
          the same philosophy:
          <strong class="text-gray-900"
            >learning to code is like gaining a superpower.</strong
          >
        </p>
      </div>
    </div>
  </section>

  <!-- Mission Section -->
  <section id="mission" class="py-16 md:py-24 bg-gray-50">
    <div class="container mx-auto px-6 text-center">
      <h2 class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-4">
        Our Mission: Empowering Georgia's Next Innovators 💡
      </h2>
      <p class="text-lg text-gray-600 max-w-4xl mx-auto mb-12">
        Tbilisi is a city on the rise, and we see incredible potential within
        our city's youth. Our mission is to provide a platform for you to
        develop the skills, mindset, and network to thrive in this exciting
        landscape.
      </p>
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div
          class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800 mb-2">
            Culture of Creation
          </h3>
          <p class="text-gray-600">
            Foster a generation of makers unafraid to experiment and bring ideas
            to life.
          </p>
        </div>
        <div
          class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800 mb-2">Inclusive Space</h3>
          <p class="text-gray-600">
            Find your tribe, collaborate on projects, and learn from one
            another.
          </p>
        </div>
        <div
          class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800 mb-2">
            Global Connection
          </h3>
          <p class="text-gray-600">
            Access a worldwide community of young innovators and resources.
          </p>
        </div>
        <div
          class="bg-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800 mb-2">
            21st-Century Skills
          </h3>
          <p class="text-gray-600">
            Learn problem-solving, critical thinking, teamwork, and more.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- What We Do Section -->
  <section id="events" class="py-16 md:py-24 bg-white">
    <div class="container mx-auto px-6">
      <h2
        class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-12 text-center"
      >
        What We Do: It's All About <span class="text-blue-600">Building</span> 🛠️
      </h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          class="bg-gray-50 rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800">Workshops</h3>
          <p class="text-gray-600 mt-2">
            Dive into practical, hands-on workshops on web dev, Python game
            creation, hardware design, and more.
          </p>
        </div>
        <div
          class="bg-gray-50 rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800">
            Project-Based Learning
          </h3>
          <p class="text-gray-600 mt-2">
            Got an idea? We provide the freedom and support to work on projects
            you're passionate about.
          </p>
        </div>
        <div
          class="bg-gray-50 rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800">Hackathons & Events</h3>
          <p class="text-gray-600 mt-2">
            Test your skills and create amazing things in local and global
            competitions.
          </p>
        </div>
        <div
          class="bg-gray-50 rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800">Guest Speakers</h3>
          <p class="text-gray-600 mt-2">
            Connect with professionals from Tbilisi's tech scene who will share
            their experiences.
          </p>
        </div>
        <div
          class="bg-gray-50 rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2"
        >
          <h3 class="text-xl font-bold text-gray-800">Global Collaboration</h3>
          <p class="text-gray-600 mt-2">
            Work on projects with members from other Hack Clubs around the
            world.
          </p>
        </div>
        <div
          class="bg-blue-500 text-white rounded-xl shadow-lg p-6 md:p-8 transition-transform duration-300 hover:-translate-y-2 flex items-center justify-center"
        >
          <p class="font-bold text-xl text-center">
            Our meetings are hands-on, not lectures!
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Team Section -->
  <section id="team" class="py-16 md:py-24 bg-gray-50">
    <h2
      class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-12 text-center"
    >
      Get to know our team!
    </h2>
    <div
      class="container flex flex-row flex-wrap justify-center items-center gap-12 mx-auto px-6"
    >
      {#each team as teamMember}
        <a
          href={teamMember.Url}
          target="_blank"
          rel="noopener noreferrer"
          class="text-center transition-transform duration-300 hover:scale-110"
        >
          <img
            src={teamMember.Avatar}
            alt={teamMember.Name}
            class="bg-center bg-no-repeat aspect-square bg-cover rounded-full h-24 w-24 sm:h-32 sm:w-32 mb-2 shadow-lg mx-auto object-fill"
            on:error={(e) => handleImgError(e, teamMember.Name)}
          />
          <p class="font-bold text-gray-700">{teamMember.Name}</p>
        </a>
      {/each}
    </div>
  </section>

  <!-- Sponsors Section -->
  <section id="sponsors" class="py-16 md:py-24 bg-white">
    <div class="container mx-auto px-6 text-center">
      <h2 class="text-3xl md:text-4xl font-extrabold text-gray-800 mb-4">
        Sponsors
      </h2>
      <p class="text-lg text-gray-600 mb-10">
        We are a 501(c)(3) non-profit organization and, thanks to them, we
        exist.
      </p>
      <div class="flex flex-row flex-wrap justify-center items-center gap-12">
        {#each sponsors as sponsor}
          <a
            href={sponsor.Url}
            target="_blank"
            rel="noopener noreferrer"
            class="text-center transition-transform duration-300 hover:scale-110"
          >
            <img
              src={sponsor.Logo}
              alt={sponsor.Name}
              class="bg-center bg-no-repeat aspect-square bg-cover rounded-full h-24 w-24 sm:h-32 sm:w-32 mb-2 shadow-lg mx-auto object-fill"
              on:error={(e) => handleImgError(e, sponsor.Name)}
            />
            <p class="font-bold text-gray-700">{sponsor.Name}</p>
          </a>
        {/each}
      </div>
      <div class="text-center mt-12">
        <a href="/sponsor" class="text-blue-600 hover:text-blue-800 underline"
          >Want to sponsor us?</a
        >
      </div>
    </div>
  </section>

  <!-- Final CTA Section -->
  <section id="join" class="hero-bg">
    <div class="container mx-auto px-6 py-16 md:py-24 text-center text-white">
      <h2 class="text-3xl md:text-4xl font-extrabold mb-4">
        The Future Is In Your Hands
      </h2>
      <p class="max-w-3xl mx-auto text-lg text-blue-100 mb-8">
        Tbilisi has a long and proud history of ingenuity and creativity. As we
        embrace the digital age, the spirit of innovation continues to thrive.
        Whether you dream of building the next great Georgian startup,
        developing cutting-edge technology, or simply want to learn a new skill
        and have fun, Tbilisi Hack Club is the place for you.
      </p>
      <a
        href="#about"
        class="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg shadow-lg transform transition-transform duration-300 hover:scale-105 hover:bg-gray-100;"
        >Learn More</a
      >
    </div>
  </section>
</main>

<style>
  /* Global styles defined using the :global pseudo-selector */
  :global(body) {
    font-family: "Inter", sans-serif;
    background-color: #f7fafc; /* Tailwind's bg-gray-100 */
  }

  .hero-bg {
    /* A vibrant gradient for hero sections */
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

  .container {
    max-width: 1140px;
  }
</style>
