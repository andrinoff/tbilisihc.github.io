<script>
  // State variables for the form
  let githubUsername = '';
  let isLoading = false;
  let successMessage = '';
  let errorMessage = '';

  // Function to handle form submission
  async function handleInvite() {
    // Reset state before the new request
    isLoading = true;
    successMessage = '';
    errorMessage = '';

    try {
      // Make a POST request to your Vercel serverless function
      const response = await fetch('https://org-invite-git.vercel.app/api/github', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ github: githubUsername }),
      });

      // Get the JSON response from the API
      const result = await response.json();

      if (!response.ok) {
        // If the response is not successful, throw an error to be caught below
        throw new Error(result.message || 'An unknown error occurred.');
      }

      // Set the success message from the API response
      successMessage = result.message;
      githubUsername = ''; // Clear the input field on success

    } catch (err) {
      // Set the error message if the fetch fails or response is not ok
      errorMessage = typeof err === 'object' && err && 'message' in err ? (/** @type {{ message?: string }} */ (err).message ?? 'An unknown error occurred.') : 'An unknown error occurred.';

    } finally {
      // Always stop loading, regardless of outcome
      isLoading = false;
    }
  }
</script>

<main class = "flex flex-col justify-center items-center">
  <div class="container">
    <h1>Invite to GitHub Team</h1>
    <p>Enter a GitHub username to send a team invitation.</p>
    
    <form on:submit|preventDefault={handleInvite}>
      <div class="form-group">
        <label for="github-username">GitHub Username</label>
        <input
          id="github-username"
          type="text"
          bind:value={githubUsername}
          placeholder="e.g., octocat"
          required
          disabled={isLoading}
        />
      </div>
      
      <button type="submit" disabled={isLoading}>
        {#if isLoading}
          <span>Sending...</span>
        {:else}
          <span>Send Invitation</span>
        {/if}
      </button>
    </form>

    <!-- Display success or error messages -->
    {#if successMessage}
      <div class="message success">
        <p>{successMessage}</p>
      </div>
    {/if}

    {#if errorMessage}
      <div class="message error">
        <p>{errorMessage}</p>
      </div>
    {/if}
  </div>
</main>

<style>
  :global(body) {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  .container {
    background-color: #ffffff;
	margin-top: 50px;
    padding: 2rem 3rem;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
    text-align: center;
    max-width: 400px;
    width: 100%;
    margin-bottom: 100px;
  }

  h1 {
    font-size: 1.75rem;
    margin-bottom: 0.5rem;
  }

  p {
    color: #606770;
    margin-bottom: 2rem;
  }

  .form-group {
    text-align: left;
    margin-bottom: 1.5rem;
  }

  label {
    display: block;
    font-weight: 600;
    margin-bottom: 0.5rem;
  }

  input {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #dddfe2;
    border-radius: 8px;
    font-size: 1rem;
    box-sizing: border-box;
    transition: border-color 0.2s;
  }

  input:focus {
    outline: none;
    border-color: #1877f2;
    box-shadow: 0 0 0 2px rgba(24, 119, 242, 0.2);
  }
  
  input:disabled {
    background-color: #f0f2f5;
    cursor: not-allowed;
  }

  button {
    width: 100%;
    padding: 0.85rem;
    background-color: #1877f2;
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.2s;
  }

  button:hover:not(:disabled) {
    background-color: #166fe5;
  }
  
  button:disabled {
    background-color: #a0bdf5;
    cursor: not-allowed;
  }

  .message {
    margin-top: 1.5rem;
    padding: 0.75rem;
    border-radius: 8px;
    font-weight: 500;
  }

  .message.success {
    background-color: #eaf6ec;
    color: #2b6b3b;
    border: 1px solid #a3d9b4;
  }

  .message.error {
    background-color: #fdeeee;
    color: #a33a3a;
    border: 1px solid #f8c6c6;
  }
</style>
