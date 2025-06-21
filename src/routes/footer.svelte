<script>
  import Link from "../link.svelte";
</script>

<footer class="bg-gradient-to-br from-slate-900 to-slate-800 text-white">
  <div class="mx-auto max-w-4xl px-6 py-16">
    <div class="text-center">
      <h2 class="text-3xl font-bold tracking-tight sm:text-4xl">
        Get in touch
      </h2>
      <p class="mt-4 text-lg leading-8 text-slate-300">
        Connect with us on social media or send us an email.
      </p>
    </div>

    <div class="mt-12 flex flex-wrap justify-center gap-x-6 gap-y-4">
      <Link
        link="https://www.facebook.com/tbilisihc"
        logo="https://cdn.simpleicons.org/facebook/grey"
        text=""
      />
      <Link
        link="mailto:tbilisihc@yahoo.com"
        logo="https://cdn.simpleicons.org/gmail/grey"
        text=""
      />
      <Link
        link="https://t.me/tbilisihc"
        logo="https://cdn.simpleicons.org/telegram/grey"
      />
      <Link
        link="https://instagram.com/tbilisihc"
        logo="https://cdn.simpleicons.org/instagram/grey"
      />
      <Link
        link="https://github.com/tbilisihc"
        logo="https://cdn.simpleicons.org/github/grey"
      />
      <Link
        link="https://x.com/tbilisi_hc"
        logo="https://cdn.simpleicons.org/x/grey"
      />
    </div>

    <div
      class="mt-16 border-t border-slate-700 pt-8 flex flex-col items-center justify-between gap-y-4 md:flex-row"
    >
      <div
        class="flex flex-wrap items-center justify-center gap-x-6 gap-y-2 md:justify-start"
      >
        <a
          href="https://tbilisi.hackclub.com/privacy-policy"
          class="text-sm leading-6 text-slate-400 transition-colors duration-300 hover:text-blue-400"
          >Privacy Policy</a
        >
        <a
          href="https://tbilisi.hackclub.com/terms-and-conditions"
          class="text-sm leading-6 text-slate-400 transition-colors duration-300 hover:text-blue-400"
          >Terms of Service</a
        >
      </div>

      <p class="text-center text-xs leading-5 text-slate-500">
        &copy; 2025 Tbilisi Hack Club. All rights reserved.
      </p>
    </div>
  </div>
</footer>

<style>
  footer {
    width: 100%;
  }
</style>
