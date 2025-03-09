<template>
  <div class="landing-page" >
    <section class="hero">
      <div class="hero-overlay">
        <h1>Transform Your Body Today!</h1>
        <p>Customized training programs to achieve real results.</p>
        <button @click="scrollToSignup">Get Started</button>
      </div>
    </section>
    
    <header class="header">
      <h1 class="title">Elevate Your Training</h1>
      <p class="subtitle">Professional coaching tailored to your goals</p>
    </header>
    
    <section class="showcase">
      <h2>Sample Videos</h2>
      <div class="gallery">
    <div class="video-card">
        <video src="../assets/1.mp4" autoplay loop muted playsinline></video>
    </div>
    <div class="video-card">
        <video src="../assets/6.mp4" autoplay loop muted playsinline></video>
    </div>
    
       
        <img src="../assets/p2.jpg" style="object-fit: cover; border-radius: 10px ; " alt="Description of image" class="video-card" />

   
    <div class="video-card">
        <video src="../assets/4.mp4" autoplay loop muted playsinline></video>
    </div>
    <img src="../assets/p1.jpg" style="object-fit: cover; border-radius: 10px ; " alt="Description of image" class="video-card" />
    <div class="video-card">
        <video src="../assets/5.mp4" autoplay loop muted playsinline></video>
    </div>
    <img src="../assets/p3.jpg" style="object-fit: cover; border-radius: 10px ; " alt="Description of image" class="video-card" />

</div>

    </section>
    <h2>What We Do </h2>
    <div class="services-section">
    <div class="services-container">
        <div class="service-card">
            <div class="card-header"> Strength Training</div>
            <div class="card-body">Build muscle, increase endurance, and enhance overall strength with targeted resistance training. My strength programs are designed to improve muscle definition, boost metabolism, and help you achieve a powerful, toned physique. Whether you're a beginner or an experienced lifter, I'll guide you through effective techniques to maximize results safely and efficiently.
            </div>
        </div>
        <div class="service-card">
            <div class="card-header"> Fat Loss Programs</div>
            <div class="card-body">Burn fat, boost metabolism, and achieve a leaner physique with my specialized fat loss programs. Through a combination of high-intensity workouts, strength training, and tailored nutrition guidance, I’ll help you shed excess weight effectively. My approach ensures sustainable results, keeping you motivated and energized while reaching your fitness goals.</div>
        </div>
        <div class="service-card">
            <div class="card-header"> Endurance Training</div>
            <div class="card-body">Enhance your stamina, improve cardiovascular health, and build lasting energy with my endurance training programs. Through a mix of aerobic exercises, interval training, and strength conditioning, I’ll help you increase your physical resilience and sustain peak performance for longer durations. Whether you're training for a sport or just looking to boost your overall fitness, my tailored approach will push your limits and keep you progressing.</div>
        </div>
        <div class="service-card">
            <div class="card-header"> Nutrition Guidance</div>
            <div class="card-body">Fuel your body the right way with personalized nutrition guidance tailored to your fitness goals. Whether you're aiming for fat loss, muscle gain, or improved endurance, I’ll help you make smart food choices that support your progress. My approach focuses on balanced meals, portion control, and sustainable habits to ensure long-term success without restrictive dieting.</div>
        </div>
    </div>
</div>

<section class="signup" ref="signup">
    <h2>Join Now</h2>
    <form @submit.prevent="submitForm">
      <input type="text" v-model="form.name" placeholder="Full Name" required />
      <input type="email" v-model="form.email" placeholder="Email Address" required />
      <textarea v-model="form.message" placeholder="Tell us about your fitness goals" required></textarea>

      <!-- Choose between Online or Physical using toggle buttons -->
      <div>
       
        <div class="session-type-buttons">
          <button
            type="button"
            class="session-button online-button"
            :class="{ active: sessionType === 'online' }"
            @click="sessionType = 'online'"
          >
            Online
          </button>
          <button
            type="button"
            class="session-button physical-button"
            :class="{ active: sessionType === 'physical' }"
            @click="sessionType = 'physical'"
          >
            Physical
          </button>
        </div>
      </div>

      <!-- Set session length -->
      <div>
        
        <div class="session-length-controls">
          <button type="button" @click="decreaseLength" >-</button>
          <span>{{ sessionLength }} hour(s)</span>
          <button type="button" @click="increaseLength">+</button>
        </div>
      </div>
      <!-- Hidden bill section, shows up when session length is set -->
      <div v-if="sessionLength > 0">
        <p>Bill: £{{ calculateBill }} ({{ sessionLength }} hour(s) at £30 per hour)</p>
      </div>

      <button type="submit">Sign Up</button>
    </form>
  </section>
    
    <footer class="contact-info">
  <div class="contact-container">
    <div class="contact-item">
      <span><i class="fas fa-map-marker-alt"></i>
      </span> <span class="info">🇬🇧 
        Swansea, UK</span>
    </div>
    <div class="contact-item">
      <span><i class="fas fa-phone"></i>
      </span> <span class="info">+44 785 268 4508</span>
    </div>
    
    <div class="contact-item">
      <span><i class="fab fa-tiktok"></i>
      </span> <span class="info"><a href="https://www.tiktok.com/@coachcyrusmosh?_t=ZS-8uViCT30N8s&_r=1">tiktok.com/coachcyrus</a></span>
    </div>
    
    <div class="contact-item">
      <span><i class="fab fa-facebook"></i>
      </span> <span class="info"><a href="https://www.facebook.com/cyrus.akabwayi.5">facebook.com/coachcyrus </a></span>
    </div>
   
    <div class="contact-item">
  <span><i class="fab fa-instagram"></i>
  </span> <span class="info" ><a href="https://www.instagram.com/coachcyruscoachcyrus?igsh=Z2kwM2I1eGxvM2pn">instagram.com/coachcyrus</a></span>
</div>
<div class="contact-item">
      <span><i class="fas fa-envelope"></i>
      </span> <span class="info">mugwanyabraham2021@gmail.com</span>
    </div>
  </div>
  <div class="footer-divider"></div>
  <h2 style="text-align: center; padding-top: 1rem; padding-bottom: -0.3rem;">About Me</h2>
  <div class="about" style=" margin: auto; width: 100%;">
    <p >With over 9 years of experience as a certified personal trainer, I have transformed countless clients through expert fitness coaching, tailored training programs, and in-depth nutritional guidance. My career spans across Dubai and London, including key areas such as Mayfair, Kensington, and Canary Wharf, where I have worked with high-profile individuals, athletes, and fitness enthusiasts. I specialize in strength training, weight management, and functional fitness, ensuring each client achieves sustainable results. My expertise, combined with a passion for health and performance, makes me a sought-after trainer in the industry.</p>
  </div>
  <div class="footer-links" style="margin: auto;">
    <p style="text-align: center; color: #E5B700;;">© 2025 Cyrus Fitness. All rights reserved.</p>
  </div>
</footer>

  </div>
</template>

<script>
export default {
  data() {
    return {
      sessionLength:0,
      sessionType: 'physical',
      form: {
        name: '',
        email: '',
        message: '',
        
        
      }
    };
  },
  computed: {
    // Calculate the total bill based on the session length
    calculateBill() {
      if(this.sessionType === 'physical'){
        return this.sessionLength * 30
      }else{
        return this.sessionLength * 20
      } // Each hour costs £30
    },
  },
  methods: {
    submitForm() {
      //console.log("Form submitted:", this.form);
      alert("Thank you! We’ll get in touch soon.");
      this.form = { name: '', email: '', message: '' };
    },
    scrollToSignup() {
      this.$refs.signup.scrollIntoView({ behavior: 'smooth' });
    },
    increaseLength() {
      this.sessionLength++; // Increase session length by 1 hour
     
    },
    decreaseLength() {
     // if (this.sessionLength > 1) {
        this.sessionLength -= 1; // Decrease session length by 1 hour, minimum 1
      //}
    },
  },
  
 
    
};
</script>

<style scoped>
.landing-page {
  margin: -7px;
  font-family: 'Poppins', sans-serif;
  text-align: center;
  padding: 20px;
  background: #1E1E1E;
  color: #ffffff;
}
.hero {
  background: url('../assets/gym.jpg') center/cover no-repeat;
  height: 70vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: relative;
}
.hero-overlay {
  background: rgba(0, 0, 0, 0.7);
  padding: 40px;
  border-radius: 10px;
}
.hero h1 {
  font-size: 3em;
  font-weight: 700;
  margin-bottom: 15px;
}
.hero p {
  font-size: 1.4em;
  margin-bottom: 20px;
}
.hero button {
  background: #FFCC00;
  color: #1E1E1E;
  border: none;
  padding: 15px 30px;
  font-size: 1.2em;
  cursor: pointer;
  border-radius: 5px;
  font-weight: bold;
}
.hero button:hover {
  background: #E5B700;
}
.header {
  margin-top: 30px;
}
.showcase {
  margin: 40px 0;
}
/* .gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
} */
.video-card {
    flex-shrink: 0;
    width: 250px; /* Adjust width as needed */
    height: 400px; /* Fixed height for all videos */
    position: relative;
    overflow: hidden; /* Ensures the video doesn't overflow */
    border-radius: 10px; /* Optional: Rounded corners */
}

.video-card video {
    width: 100%; /* Full width of the card */
    height: 100%; /* Full height of the card */
    object-fit: cover; /* Maintains aspect ratio while covering the area */
}
video {
  width: 100%;
  max-width: 400px;
  height: auto;
  border-radius: 10px;
  transition: transform 0.3s ease-in-out;
}
video:hover {
  transform: scale(1.05);
}
.signup form {
  display: flex;
  flex-direction: column;
  max-width: 450px;
  margin: auto;
  background: #2C2C2C;
  padding: 25px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(208, 207, 205, 0.2);
}
input, textarea, button {
  margin: 10px 0;
  padding: 12px;
  font-size: 16px;
  width: 100%;
  box-sizing: border-box;
  border: 2px solid #FFCC00;
  border-radius: 5px;
  background: transparent;
  color: white;
}
button {
  background: #FFCC00;
  color: #1E1E1E;
  font-weight: bold;
  transition: background 0.3s;
}
button:hover {
  background: #E5B700;
}
.contact-info {
  background: #222;
  padding: 20px;
  text-align: center;
  color: #FFCC00;
  margin-top: 30px;
  border-top: 3px solid #FFCC00;
}
.contact-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}
.contact-item {
  display: flex;
  align-items: center;

  gap: 10px;
  font-size: 1.2em;
}

.about {
  margin-top: 20px;
  padding: 10px;
  font-size: 1em;
  color: #fff;
}
/* @media (max-width: 768px) {
  .gallery {
    flex-direction: column;
    
   
  }
  video {
    max-width: 100%;
  }
  .hero h1 {
    font-size: 2.5em;
  }
  .hero p {
    font-size: 1.2em;
  }
  .contact-container {
    flex-direction: column;
  }
} */
@media (max-width: 768px) {
  .contact-info {

   
    background: #1E1E1E;
    padding: 30px 15px;
    text-align: left;
    border-top: 1px solid rgba(255, 255, 255, 0.2);
    font-size: 14px;
    color: rgba(255, 255, 255, 0.7);
  }

  .contact-container {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .contact-item {
    display: flex;
    align-items: start;
    justify-content: start;
    gap: 8px;
    font-size: 0.9em;
  }

  .contact-item span {
    font-size: 1.2em;
    opacity: 0.7;
  }

  .contact-item .info{
    font-size: 1.2em;
    opacity: 0.7;
    margin-left: .3rem;

  }

  
  .about {
    margin-top: 20px;
    font-size: 0.8em;
    color: rgba(255, 255, 255, 0.6);
    max-width: 100%;
    padding:0 -10px;
    line-height: 1.5;
  }

  .footer-divider {
    width: 100%;
    height: 1px;
    background: rgba(255, 255, 255, 0.2);
    margin: 15px 0;
  }

  .footer-links {
    font-size: 0.8em;
    color: rgba(255, 255, 255, 0.5);
  }
}
/* Default styling for the gallery */
.gallery {
    display: flex;
    overflow: hidden; /* Hide the scrollbar */
    gap: 16px; /* Space between cards */
}

/* Card styling */
.video-card {
    flex-shrink: 0; /* Prevents videos from shrinking */
    width: 250px; /* Adjust width of the card */
    height: 400px; /* Adjust height of the card */
    position: relative;
}

/* Media query for small screens */
@media (max-width: 768px) {
    .gallery {
        overflow-x: scroll; /* Enable horizontal scrolling */
        scroll-snap-type: x mandatory; /* Ensures smooth snapping */
    }

    .video-card {
        scroll-snap-align: start; /* Make sure the video card aligns at the start */
    }

    .gallery::-webkit-scrollbar {
        display: none; /* Hide scrollbar */
    }

    /* Slightly visible second video */
    .video-card:nth-child(1) {
        margin-left: -50px; /* Slightly shift the second video for visibility */
    }
}

/* Services Section */
.services-section {
    width: 100%;
   
    overflow: hidden; /* Ensures no extra scrolling on larger screens */
}

/* Horizontal Scrollable Container */
.services-container {
  
    display: flex;
    overflow-x: auto; /* Enables horizontal scrolling */
    gap: 16px; /* Space between cards */
    scroll-snap-type: x mandatory;
    padding-bottom: 10px;
}

/* Hide Scrollbar */
.services-container::-webkit-scrollbar {
    display: none;
}

/* Service Card */
.service-card {
    flex-shrink: 0;
    width: 280px;
    border: 1px solid white;
     /* Orange background */
    color: #fff; /* White text */
    border-radius: 10px;
    padding: 15px;
    scroll-snap-align: start;
    margin-right: 1rem;
}

/* Card Header */
.card-header {
    background:  #E5B700; /* White background */
    color: #fff; /* Orange text */
    font-weight: bold;
    padding: 10px;
    border-radius: 8px;
    text-align: center;
    margin-bottom: 10px;
}

/* Card Body */
.card-body {
    font-size: 14px;
}

/* Responsive Scroll Effect */
@media (max-width: 768px) {
    .services-container {
        overflow-x: scroll;
    }
    .service-card{
      width: 230px;
    }

    /* Ensure next card is slightly visible */
    .service-card:nth-child(2) {
        margin-left: -20px;
    }
}
a{
  color: inherit;
 
}
i{
  color:#E5B700; ;
}
.session-type-buttons {
  display: flex;
  gap: 10px;
  
}

.session-button {
  padding: 10px 20px;
  border: 2px solid white; /* Black border */
  background-color: #fff; /* White background */
  color: #2a2a2a; /* Black text */
  cursor: pointer;
  transition: background-color 0.3s, color 0.3s, border-color 0.3s;
  font-size: 16px;
}

.session-button.active {
  background-color: #E5B700; /* Orange background when active */
  color: white; /* White text when active */
  border-color: #E5B700; /* Orange border when active */
}

.session-button:hover {
  background-color: #E5B700; /* Lighter orange on hover */
  border-color: #E5B700; /* Lighter orange border on hover */
}

.online-button {
  background-color: #fff;
}

.physical-button {
  background-color: #fff;
}

.session-length-controls {
  display: flex;
  align-items: center;
  gap: 10px;
}

.session-length-controls button {
  padding: 5px 15px;
  font-size: 20px;
  background-color: #fff; /* White background */
  border: 2px solid white; /* Black border */
  color: #424141; /* Black text */
  cursor: pointer;
  transition: background-color 0.1s, color 0.1s, border-color 0.1s;
}

.session-length-controls button:disabled {
  background-color: #f4f4f4; /* Light gray for disabled button */
  color: #ccc; /* Gray text when disabled */
  cursor: not-allowed;
}

.session-length-controls button:hover {
  background-color: #ff5733; /* Orange background on hover */
  border-color: #ff5733; /* Orange border on hover */
  color: white; /* White text when hovered */
}

.session-length-controls span {
  font-size: 18px;
  color: white; /* Black text */
}
</style>
