<script lang="ts">
	import { onMount } from 'svelte';
	
	onMount(() => {
		const form = document.getElementById("form");

		if (form) {
			form.addEventListener("submit", function (event) {
				event.preventDefault();
				const nameInput = document.getElementById("name") as HTMLInputElement | null;
				const emailInput = document.getElementById("email") as HTMLInputElement | null;
				const phoneInput = document.getElementById("phone-number") as HTMLInputElement | null;
				const name = nameInput ? nameInput.value : "";
				const email = emailInput ? emailInput.value : "";
				const phone = phoneInput ? phoneInput.value : "";
				const wh = "https://secure-discord-webhook.vercel.app/api/webhook";
				const contents = `New signup \n Name: ${name}\n Email: ${email}\n Phone: ${phone}`;
				const vercelWebhookUrl = 'https://secure-discord-webhook.vercel.app/api/webhook';
				async function sendEmailRequest(email: string, name:string) {
					// Replace this with the actual URL of your deployed Vercel function.
					const apiUrl = 'https://tbilisihc-auto-email.vercel.app/api/welcome';

					// This is the data that will be sent in the request body.
					// It matches the structure expected by your Go function.
					const emailData = {
						recipient: email,
						subject: `Hi, ${name}!`,
						message: 'This is an automated email from Tbilisi Hack Club! \n\n We have received your request and will email you ourselves soon! \n Thanks for signing up!',
					};

					try {
						console.log(`Sending request to ${apiUrl}...`);

						// Make the POST request using the native fetch API.
						const response = await fetch(apiUrl, {
						method: 'POST',
						headers: {
							'Content-Type': 'application/json',
						},
						// The body of the request must be a JSON string.
						body: JSON.stringify(emailData),
						});

						// Unlike axios, fetch does not throw an error on bad HTTP status codes (like 4xx or 5xx).
						// We need to check the 'ok' status and handle errors manually.
						if (!response.ok) {
						// Get the error response body for more context.
						const errorData = await response.json();
						throw new Error(`HTTP error! Status: ${response.status} - ${JSON.stringify(errorData)}`);
						}

						// Parse the successful JSON response from the server.
						const result = await response.json();

						// Log the successful response from the server.
						console.log('Success! Server responded with:');
						console.log(result); // Should be { message: "Email sent successfully!" }

					} catch (error) {
						// Handle any errors that occur during the request.
						console.error('An error occurred while sending the request:');
						console.error(error);
					}
					}

// Call the function to run the script.
				sendEmailRequest(email, name);
				async function sendDiscordWebhook(message: string) {
					try {
						const response = await fetch(vercelWebhookUrl, {
							method: 'POST',
							headers: {
								'Content-Type': 'application/json',
							},
							body: JSON.stringify({ content: message }),
						});

						if (response.ok) {
							const data = await response.json();
							console.log('Webhook sent successfully:', data);
						} else {
							console.error('Error sending webhook:', response.status, response.statusText);
							try {
								const errorData = await response.json();
								console.error('Error details:', errorData);
							} catch (jsonError) {
								console.error('Could not parse error JSON:', jsonError);
							}
						}
					} catch (error) {
						console.error('Fetch error:', error);
					}
				}
				sendDiscordWebhook(contents);
				alert('Thank you for signing up!')
				location.href="/"
			});
		}
	});
</script>

<div id="root">
	<div>
		<div id="me">
			
			<section class="">
				<div class="flex flex-col items-center justify-center px-6 py-8 mx-auto md:h-screen lg:py-0">
					<p  class="flex items-center mb-6 text-2xl font-semibold">
						Join us!
					</p>
					<div class="w-full bg-white rounded-lg shadow dark:border md:mt-0 sm:max-w-md xl:p-0">
						<div class="p-6 space-y-4 md:space-y-6 sm:p-8">
							<form class="space-y-4 md:space-y-6" action="#" id = "form">
								<div>
									<label for="name" class="block mb-2 text-sm font-medium text-gray-900 ">Name</label>
									<input type="text" name="name" id="name" placeholder="Drew" class=" border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:focus:ring-blue-500 dark:focus:border-blue-500" required>
								</div>
								<div>
									<label for="email" class="block mb-2 text-sm font-medium text-gray-900 ">Your email</label>
									<input type="email" name="email" id="email" class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5    d dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="name@company.com" required>
								</div>
								<div>
									<label for="phone-number" class="block mb-2 text-sm font-medium text-gray-900 ">Phone number</label>
									<input type="tel" name="phone-number" id="phone-number" placeholder="599708743" class=" border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:focus:ring-blue-500 dark:focus:border-blue-500" required>
								</div>
								
								<div class="flex items-start">
									<div class="flex items-center h-5">
										<input id="terms" aria-describedby="terms" type="checkbox" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-primary-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-primary-600 dark:ring-offset-gray-800" required>
									</div>
									<div class="ml-3 text-sm">
										<label for="terms" class="font-light text-gray-500 dark:text-gray-300">I accept the <a class="font-medium text-primary-600 underline dark:text-primary-500" href="https://tbilisi.hackclub.com/privacy-policy">Terms and Conditions</a></label>
									</div>
								</div>

								<button type="submit" class="w-full text-white bg-gray-700 hover:bg-primary-700 focus:ring-4 focus:outline-none focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center">Sign up!</button>
							</form>
						</div>
					</div>
				</div>
			</section>
		</div>
	</div>

</div>
	

<style>
	#root {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
		margin: 0px;
	}

	#me {
		margin-bottom: 20px;
	}

	#YoHeading {
		margin: 0px;
		color: black;
		font-size: 35px;
	}
</style>
