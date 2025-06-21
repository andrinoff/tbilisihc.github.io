<script>
	import Link from "./link.svelte";
	import LinkMob from "./link Mob.svelte";
</script>

<div id="yes" >
	<div style="margin-right: auto;"> 
	<Link
		link="/"
		text="Home"
		logo="https://avatars.githubusercontent.com/u/213840567?s=200&v=4"
		
	/>
	</div>
	<Link
		link="/about"
		text="About"
		logo="https://img.icons8.com/?size=100&id=82742&format=png&color=000000"
	/>
	
	<Link
		link="/events"
		text="Events"
		logo="https://img.icons8.com/?size=100&id=4LZxtKlARvqr&format=png&color=000000"
	/>
	<Link
		link="https://github.com/tbilisihc"
		text="Github"
		logo="https://img.icons8.com/?size=100&id=62856&format=png&color=000000"
	/>
	<button
			onclick={() => {window.location.href = '/join';}}
            class="flex min-w-[50px] max-w-[480px] cursor-pointer items-center justify-center overflow-hidden rounded-xl h-8 px-2 bg-[#3f7fbf] text-gray-50 text-sm font-bold leading-normal tracking-[0.015em]"
            >
            <span class="truncate">Join Now</span>
		</button>
	
</div>
<div id="no">
	<LinkMob
		link="/"
		logo="https://avatars.githubusercontent.com/u/213840567?s=200&v=4"
		/>
	<LinkMob
		link="/about"
		logo="https://img.icons8.com/?size=100&id=82742&format=png&color=000000"
	/>
	<LinkMob
		link="/join"
		logo="https://img.icons8.com/?size=100&id=oW6M35lNE3pB&format=png&color=000000"
	/>
	<LinkMob
		link="/events"
		logo="https://img.icons8.com/?size=100&id=4LZxtKlARvqr&format=png&color=000000"
	/>
	<LinkMob
		link="https://github.com/tbilisihc"
		logo="https://img.icons8.com/?size=100&id=62856&format=png&color=000000"
	/>
</div>

<style>
	@import "https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css";
	#yes {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	#no {
		display: none;
	}

	@media screen and (max-width: 800px) {
		#yes {
			display: none;
		}

		#no {
			display: flex;
		}
	}
</style>
