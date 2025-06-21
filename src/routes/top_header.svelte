
    <header class="bg-white/80 backdrop-blur-md sticky top-0 z-50 shadow-sm">
    <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
        <div class="globe-container">
        <a href="/">
        <div class="flag-container">
        <img 
            src="https://tbilisi.hackclub.com/assets/transparent/flag.png" 
            alt="Tbilisi" 
            class="waving-flag"
        >
    </div>
        </a>
        </div>
        <div class="hidden md:flex space-x-8">
            <a href="/about" class="text-gray-600 hover:text-blue-500 transition-colors">About</a>
            <a href="/events" class="text-gray-600 hover:text-blue-500 transition-colors">Events</a>
            <a href="/join" class="text-gray-600 hover:text-blue-500 transition-colors">Join</a>
        </div>
        <a href="/about" class="md:hidden text-gray-600 hover:text-blue-500 transition-colors">About</a>
          <a href="/events" class="md:hidden  text-gray-600 hover:text-blue-500 transition-colors">Events</a> 
         <a href="/join" class="md:hidden bg-blue-500 text-white font-semibold py-2 px-4 rounded-lg hover:bg-blue-600 transition-colors">Join</a>
    </nav>
</header>

<style>



    .flag-container {
            text-align: center;
            border-radius: 1.5rem; /* More rounded corners */
        }
        
        /* The image element for the flag */
        .waving-flag {
            max-width: 100%;
            width: 100px;
            transition: transform 0.3s ease-in-out; /* Smooth transition for hover effect */
            transform-origin: bottom left; /* Set the origin for the wave effect */
    }
    .waving-flag:hover {
            animation: wave 1.5s infinite ease-in-out;
        }

        /* Keyframes for the wave animation */
        @keyframes wave {
            0%, 100% {
                transform: translateX(0);
                
            }
            25% {
                transform: translateX(-10px); /* Move left */
                transform: rotateX(-20deg);
            }
            75% {
                transform: translateX(10px); /* Move right */
                transform: rotateX(20deg);
            }
        }
/* .globe-container {
    perspective: 800px;
  }

  .globe-button {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    position: relative;
    transform-style: preserve-3d; /* This is key for 3D children 
    transition: transform 0.3s ease-out;
    cursor: pointer;
  }

  
  .globe-container:hover .globe-button {
    animation: spin 12s linear infinite;
  }

    .globe-button::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    
    
    background: url('https://avatars.githubusercontent.com/u/213840567?s=200&v=4');
    background-size: 200% 100%; 
    background-repeat: repeat-x;
    
    
    animation: move-map 12s linear infinite;
  }
  
  
  .globe-button::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    box-shadow: inset 0 0 25px 10px rgba(0, 0, 0, 0.7);
  }
  @keyframes spin {
    from {
      transform: rotateY(0deg);
    }
    to {
      transform: rotateY(360deg);
    }
  }

  
  @keyframes move-map {
    from {
      background-position: 0% 0;
    }
    to {
      background-position: -200% 0; 
    }
  } */
</style>