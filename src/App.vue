<script setup>
import { ref, onMounted } from 'vue'

const showProfile = ref(false)

onMounted(() => {
  showProfile.value = true
})
</script>

<template>
  <div class="app">
    <!-- Profile Picture Animation -->
    <transition name="fade-slide">
      <div v-if="showProfile" class="profile">
        <a href="#" class="profile-container">
          <img src="/pfp.jpg" alt="Profile Picture" />
          <div class="menu">
            <a href="#about">About</a>
            <a href ="#contact">Links</a>
            <a href="#gaming">Gaming</a>
          </div>
        </a>
      </div>
    </transition>

    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-card">
        <h1>Hello, World !</h1>
        <p> My name is BliinD, or N7xT ! </p>
        <p> I'm a competitive gamer and developer in formation.</p>
        <div class="hero-buttons">
          <a href="#about">More about myself</a>
          <a href ="#contact">Socials and links</a>
          <a href="#gaming">Gaming</a>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
      <h2>About Me</h2>
      <div class="card">
        <p>I'm a 21 yo french (young?) man who's really into competitive games, aim and peripherals. 
          I also like to code, especially in software dev, and I'm learning cybersecurity aside.</p>
      </div>
    </section>

    <!-- Contact/Social Section -->
    <section id="contact" class="section contact">
      <h2>Connect With Me</h2>
      <div class="card">
        <p>Follow me on social media for more gaming content, updates, and let's connect!</p>
        <ul class="social-list">
          <li>
            <a href="https://x.com/bliindwashere" target="_blank" rel="noopener">
              <img src="https://avatars.fastly.steamstatic.com/5b53bbfa3dc6894c35154162abadbdda328e053c_full.jpg" alt="Twitter Profile" />
              Twitter
            </a>
          </li>
          <li>
            <a href="https://open.spotify.com/user/crruky6vetxb8uw0tqlbkxoeh?si=06b3252e46a446d7" target="_blank" rel="noopener">
              <img src="https://unavatar.io/spotify" alt="Spotify" />
              Spotify
            </a>
          </li>
          <li>
            <a href="https://steamcommunity.com/id/anotherBliinD/" target="_blank" rel="noopener">
              <img src="https://avatars.fastly.steamstatic.com/5b53bbfa3dc6894c35154162abadbdda328e053c_full.jpg" alt="Steam Profile 1" />
              Steam 1
            </a>
          </li>
          <li>
            <a href="https://steamcommunity.com/id/blinisan" target="_blank" rel="noopener">
              <img src="https://avatars.fastly.steamstatic.com/713baf11c21d77ed511ea0e6e246c014ce7af92f_full.jpg" alt="Steam Profile 2" />
              Steam 2
            </a>
          </li>
          <li>
            <a href="https://github.com/ab-x-cd" target="_blank" rel="noopener">
              <img src="https://unavatar.io/github/ab-x-cd" alt="GitHub Profile" />
              GitHub
            </a>
          </li>
          <li>
            <span>
              <img src="https://avatars.fastly.steamstatic.com/713baf11c21d77ed511ea0e6e246c014ce7af92f_full.jpg" alt="Discord profile" />
              Discord: bliindwashere
            </span>
          </li>
        </ul>
      </div>
    </section>

    <!-- Gaming Section -->
    <section id="gaming" class="section gaming">
      <h2>Gaming Experiences</h2>
      <div class="game-grid">

        <div class ="card game-card">
          <h3>Still building :(</h3>
          <p>I'm still working on this, I swear it'll be done one day.</p>
        </div>  

        <!-- Game Card 1
        <div class="card game-card">
          <h3>Game Title 1</h3>
          <p>My experiences and highlights from this game. Achievements, favorite moments, etc.</p>
          <div class="game-links">
            <a href="#">Twitch Clips</a>
            <a href="#">YouTube</a>
            <a href="#">Discord</a>
          </div>
        </div>

         Game Card 2 
        <div class="card game-card">
          <h3>Game Title 2</h3>
          <p>Another gaming experience with links to social media and clips.</p>
          <div class="game-links">
            <a href="#">Twitch</a>
            <a href="#">Twitter</a>
          </div>
        </div>

         Game Card 3 
        <div class="card game-card">
          <h3>Game Title 3</h3>
          <p>More gaming content and links.</p>
          <div class="game-links">
            <a href="#">Steam</a>
            <a href="#">TikTok</a>
          </div>
        </div>-->
      </div> 
    </section>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2025 BliinD. All rights reserved.</p>
    </footer>
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  background: linear-gradient(to bottom right, #0f172a, #581c87, #0f172a);
  color: white;
}

.profile {
  position: fixed;
  top: 1rem;
  left: 1rem;
  z-index: 10;
}

.profile-container {
  width: 4rem;
  height: 4rem;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  position: relative;
}

.profile img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  transition: transform 1s ease;
}

.profile:hover img {
  transform: rotate(360deg);
}

.menu {
  opacity: 0;
  transform: scaleX(0);
  transform-origin: left;
  position: absolute;
  top: 0;
  left: 4rem;
  height: 4rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 2rem;
  padding: 0 0.5rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s ease;
}

.profile:hover .menu {
  opacity: 1;
  transform: scaleX(1);
}

.menu a {
  padding: 0.5rem 1rem;
  border-radius: 5rem;
  text-decoration: none;
  color: white;
  transition: background 0.3s;
}

.menu a:hover {
  background: rgba(255, 255, 255, 0.048);
}

.hero {
  display: flex;
  min-height: 100vh;
  align-items: center;
  justify-content: center;
  padding: 1rem;
}

.hero-card {
  text-align: center;
  backdrop-filter: blur(10px);
  background: rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
  padding: 2rem;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.hero h1 {
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1rem;
  background: linear-gradient(to right, #60a5fa, #a855f7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero p {
  font-size: 1.25rem;
  color: #d1d5db;
  margin-bottom: 2rem;
  max-width: 42rem;
  margin-left: auto;
  margin-right: auto;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.hero a {
  padding: 0.75rem 1.5rem;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border-radius: 9999px;
  transition: all 0.3s;
  text-decoration: none;
  color: white;
}

.hero a:hover {
  background: rgba(255, 255, 255, 0.3);
}

.section {
  padding: 2rem 1rem;
}

.section h2 {
  font-size: 2.5rem;
  font-weight: bold;
  text-align: center;
  margin-bottom: 3rem;
  background: linear-gradient(to right, #34d399, #3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.card {
  backdrop-filter: blur(10px);
  background: rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
  padding: 2rem;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s;
}

.card:hover {
  background: rgba(255, 255, 255, 0.15);
}

.about {
  max-width: 56rem;
  margin: 0 auto;
}

.about p {
  font-size: 1.125rem;
  line-height: 1.75;
  color: #d1d5db;
}

.gaming {
  max-width: 72rem;
  margin: 0 auto;
}

.game-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.game-card h3 {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.game-card p {
  color: #d1d5db;
  margin-bottom: 1rem;
}

.game-links {
  display: flex;
  gap: 0.5rem;
}

.game-links a {
  color: #60a5fa;
  text-decoration: none;
}

.game-links a:hover {
  color: #93c5fd;
}

.contact {
  max-width: 56rem;
  margin: 0 auto;
  text-align: center;
}

.social-list {
  list-style: none;
  padding: 0;
  margin-top: 2rem;
}

.social-list li {
  margin-bottom: 1rem;
}

.social-list a {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.75rem 1.5rem;
  background: rgba(59, 130, 246, 0.2);
  backdrop-filter: blur(10px);
  border-radius: 9999px;
  transition: all 0.3s;
  text-decoration: none;
  color: white;
}

.social-list a:hover {
  background: rgba(59, 130, 246, 0.3);
}

.social-list img {
  width: 2rem;
  height: 2rem;
  border-radius: 50%;
  object-fit: cover;
}

.social-list span {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.75rem 1.5rem;
  background: rgba(59, 130, 246, 0.2);
  backdrop-filter: blur(10px);
  border-radius: 9999px;
  color: white;
}

.footer {
  padding: 2rem 1rem;
  text-align: center;
  color: #9ca3af;
}

.fade-slide-enter-active {
  transition: all 1s ease-out;
}

.fade-slide-enter-from {
  opacity: 0;
  transform: translateY(-20px);
}

.fade-slide-enter-to {
  opacity: 1;
  transform: translateY(0);
}

@media (min-width: 768px) {
  .hero h1 {
    font-size: 3.75rem;
  }
  .hero p {
    font-size: 1.5rem;
  }
  .section h2 {
    font-size: 3rem;
  }
}
</style>
