<script setup>
import avatar from '../avatar-square.jpg'
import PageIcon from './components/PageIcon.vue'
import ThemeSwitcher from './components/ThemeSwitcher.vue'

const facts = [
  { label: 'Stack', value: 'TypeScript · Python · Astro · Cloudflare Workers · Node.js' },
  { label: 'Focus', value: 'Developer tools, coding agents & automation' },
  { label: 'Based in', value: 'Shenzhen, China' },
]

const updates = [
  'Making contextlint smarter at catching stale and conflicting agent rules.',
  'Building in public on 𝕏.',
  "Being a lazzzzz’y dev, occasionally.",
]

const links = [
  { label: 'GitHub', href: 'https://github.com/BillWGong' },
  { label: '𝕏 / Twitter', href: 'https://x.com/yankaxh1207' },
  { label: 'Email', href: 'mailto:banlangencn@gmail.com' },
  { label: 'Discord', href: 'https://discord.com/users/1257990809811161161' },
]
</script>

<template>
  <a class="skip-link" href="#main">Skip to content</a>
  <div class="page">
    <header class="masthead">
      <a class="wordmark" href="#main" aria-label="BillW Gong, home">billw<span>.</span></a>
      <ThemeSwitcher />
    </header>

    <main id="main" tabindex="-1">
      <section class="intro" aria-labelledby="intro-title">
        <div class="intro-heading">
          <img class="avatar" :src="avatar" width="76" height="76" alt="BillW Gong" fetchpriority="high" />
          <div>
            <h1 id="intro-title">hi! i'm BillW<span class="title-dot">.</span></h1>
            <p class="subtitle">Developer & open-source enthusiast</p>
          </div>
        </div>

        <div class="bio">
          <p>I'm <strong>BillW Gong</strong>, a 14-year-old developer based in <strong>Shenzhen, China</strong>. I build open-source tools for developers and creators.</p>
          <p>I found my way into programming through hackathons, as an early contributor at <span class="quiet-emphasis">PolarisHackathon</span>. These days, I’m exploring better tools and small ideas on the web.</p>
        </div>

        <dl class="facts">
          <div v-for="fact in facts" :key="fact.label" class="fact-row">
            <dt>{{ fact.label }}</dt>
            <dd>{{ fact.value }}</dd>
          </div>
        </dl>
      </section>

      <section class="section-row" aria-labelledby="work-title">
        <h2 id="work-title">things i've built</h2>
        <div>
          <a class="project-link" href="https://github.com/BillWGong/contextlint">
            <span>contextlint</span><PageIcon name="external" />
          </a>
          <p class="project-description">A second pair of eyes for coding-agent instructions. Source evidence, conflict checks, and bilingual offline reports.</p>
          <span class="project-note">Open source · Developer tooling</span>
        </div>
      </section>

      <section class="section-row" aria-labelledby="now-title">
        <h2 id="now-title">now</h2>
        <ul class="updates">
          <li v-for="update in updates" :key="update">{{ update }}</li>
        </ul>
      </section>

      <section class="section-row contact-section" aria-labelledby="contact-title">
        <h2 id="contact-title">find me</h2>
        <div>
          <ul class="social-links">
            <li v-for="link in links" :key="link.label">
              <a :href="link.href">{{ link.label }}<PageIcon name="external" /></a>
            </li>
          </ul>
          <p class="contact-note">Building in public. Come say hi <span aria-label="love">♡</span></p>
        </div>
      </section>
    </main>

    <footer>
      <span>© {{ new Date().getFullYear() }} BillW Gong</span>
      <a href="https://billw.top">billw.top<PageIcon name="external" /></a>
    </footer>
  </div>
</template>
