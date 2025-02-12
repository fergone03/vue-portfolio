<template>
  <div class="projects-container">
    <div v-for="project in PROJECTS" :key="project.title" class="project-item">
      <div class="project-image-container">
        <div class="project-image-wrapper">
          <img
            :alt="`imagen del proyecto ${project.title}`"
            class="project-image"
            :src="project.image"
          />
        </div>
      </div>

      <div class="project-details">
        <h3 class="project-title">
          {{ project.title }}
        </h3>
        <div class="project-tags">
          <ul class="tags-list">
            <li v-for="tag in project.tags" :key="tag.name">
              <span :class="`tag ${tag.class}`">
                <component :is="tag.icon" class="tag-icon" />
                {{ tag.name }}
              </span>
            </li>
          </ul>
        </div>
        <footer class="project-links">
          <a v-if="project.github" :href="project.github" target="_blank" class="project-button">
            <FaviconPortfolio class="link-icon" />
            Code
          </a>
          <a v-if="project.link" :href="project.link" target="_blank" class="project-button">
            <FaviconPortfolio class="link-icon" />
            Preview
          </a>
        </footer>
      </div>
      <div class="project-description">
        {{ project.description }}
      </div>
    </div>
  </div>
</template>

<script>
import FaviconPortfolio from './icons/FaviconPortfolio.vue'

const TAGS = {
  HTML: {
    name: 'HTML',
    class: 'tag-html',
    icon: FaviconPortfolio,
  },
  CSS: {
    name: 'CSS',
    class: 'tag-css',
    icon: FaviconPortfolio,
  },
  JavaScript: {
    name: 'JavaScript',
    class: 'tag-js',
    icon: FaviconPortfolio,
  },
  React: {
    name: 'React',
    class: 'tag-react',
    icon: FaviconPortfolio,
  },
}

const PROJECTS = [
  {
    title: '49% -  Página de agencia con formulario de contacto funcional',
    description:
      'La página de la agencia cuenta con un diseño responsivo y una estructura clara. Incluye un formulario de contacto funcional. El código es modular y reutilizable, utilizando hooks personalizados y componentes estilizados con CSS Modules.',
    link: 'https://49percent.netlify.app',
    github: 'https://github.com/fergone03/pag-agencia',
    image: './projects/svgl.webp',
    tags: [TAGS.HTML, TAGS.CSS, TAGS.JavaScript, TAGS.React],
  },
]

export default {
  components: {
    FaviconPortfolio,
  },
  data() {
    return {
      PROJECTS,
    }
  },
}
</script>

<style>
ul {
  list-style-type: none;
}
.projects-container {
  display: flex;
  flex-direction: column;
  gap: 4rem;
}

.project-item {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.project-image-container {
  width: 100%;
}

.project-image-wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
  border-radius: 1rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition:
    transform 0.5s ease-in-out,
    box-shadow 0.5s ease-in-out;
}

.project-image {
  width: 100%;
  height: 14rem;
  object-fit: cover;
  transition: transform 0.5s ease-in-out;
}

.project-details {
  width: 100%;
  max-width: 40rem;
}

.project-title {
  font-size: 2rem;
  font-weight: bold;
  color: #f3f4f6;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  margin-top: 0.5rem;
}

.tags-list {
  display: flex;
  flex-direction: row;
  gap: 0.5rem;
  margin-bottom: 0.5rem;
}

.tag {
  display: flex;
  gap: 0.5rem;
  border-radius: 9999px;
  font-size: 0.75rem;
  padding: 0.25rem 0.5rem;
}

.tag-html {
  background-color: #1f2937;
  color: #e44d26;
}

.tag-css {
  background-color: #1f2937;
  color: #3b82f6;
}

.tag-js {
  background-color: #1f2937;
  color: #d1b400;
}

.tag-react {
  background-color: #1f2937;
  color: #61dafb;
}

.project-links {
  display: flex;
  align-items: flex-end;
  justify-content: flex-start;
  margin-top: 1rem;
  gap: 1rem;
}

.link-icon {
  width: 1.5rem;
  height: 1.5rem;
}

.project-description {
  margin-top: 0.5rem;
  color: #d1d5db;
}
.project-button {
  background-color: #1f2937;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
}

.project-button:hover {
  background-color: #ffffff;
  color: #1f2937;
}
</style>
