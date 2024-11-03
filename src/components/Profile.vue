<template>
  <div class="profile-page">
    <p>Currently Not Support For Mobile View. 😭</p>
    <!-- Header cho pfp -->
    <header class="profile-header">
      <div class="profile-info">
        <img :src="user.image" alt="Profile Picture" class="profile-picture" />
        <h1>{{ user.name }}</h1>
        <p class="user-title">{{ user.title }}</p>
      </div>

      <!-- Right Side: Programming Language Icons -->
      <div class="programming-icons">
        <p class="programming-title">Programming Languages</p>
        <div class="icons">
          <i class="fab fa-java" title="Java"></i>
          <i class="fab fa-js" title="JavaScript"></i>
          <i class="fab fa-vuejs" title="Vue.js"></i>
          <i class="fab fa-html5" title="HTML5"></i>
          <i class="fab fa-css3-alt" title="CSS3"></i>
        </div>
      </div>
    </header>

    <!-- Phan gioi thieu -->
    <section class="bio">
      <h2>About Me</h2>
      <p>{{ user.bio }}</p>
    </section>

    <!-- Link cho MXH -->
    <section class="social-links">
      <h2>My Social Links</h2>
      <ul>
        <li v-for="link in user.socialLinks" :key="link.platform">
          <a :href="link.url" target="_blank">
            <i :class="link.icon" aria-hidden="true"></i> {{ link.platform }}
          </a>
        </li>
      </ul>
    </section>
    <section class="media-section">
      <video v-if="user.mediaType === 'video'" :src="user.media" controls></video>
      <img v-else-if="user.mediaType === 'gif'" :src="user.media" alt="Profile Media" />
    </section>
  </div>
</template>

<script>
export default {
  name: "Profile",
  data() {
    return {
      user: {
        name: "Aixlusion",
        title: "Also khown as FZVN",
        bio: "I do coding when inspired, currently progressing in C++/Java/VueJS/HTML/CSS",
        image: "../src/assets/pfp.jpg", // Placeholder image
        socialLinks: [
          { platform: "Discord", url: "https://discord.com/users/422016649793765377", icon: "fa-brands fa-discord" },
          { platform: "GitHub", url: "https://github.com/Aixlusion", icon: "fab fa-github" },
          { platform: "Twitter", url: "https://twitter.com/Aixlusion", icon: "fab fa-x-twitter" },
        ],
        media: "./src/assets/gif1.gif", // Example video link
        mediaType: "gif", // Set to "video" or "gif"
      },
    };
  },
};
</script>
