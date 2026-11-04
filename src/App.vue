<script setup>
import avatar1x from '../avatar-152.jpg'
import avatar2x from '../avatar-304.jpg'
import PageIcon from './components/PageIcon.vue'
import ThemeSwitcher from './components/ThemeSwitcher.vue'

const facts = [
  { label: 'Stack', value: 'TypeScript · Python · Astro · Cloudflare Workers · Node.js' },
  { label: 'Focus', value: 'Developer tools, coding agents & automation' },
  { label: 'Based in', value: 'Shenzhen, China' },
]

const updates = [
  'Shipping dsh-go-mac, a native macOS client for DeepSeek Harness.',
  'Making contextlint smarter at catching stale and conflicting agent rules.',
  "Being a lazzzzz’y dev, occasionally.",
]

const links = [
  { label: 'GitHub', href: 'https://github.com/BillWGong' },
  { label: '𝕏 / Twitter', href: 'https://x.com/yankaxh1207' },
  { label: 'Zhihu', href: 'https://www.zhihu.com/people/bnv-80' },
  { label: 'Email', href: 'mailto:banlangencn@gmail.com' },
  { label: 'Discord', href: 'https://discord.com/users/1257990809811161161' },
]

const projects = [
  {
    name: 'dsh-go-mac',
    href: 'https://github.com/BillWGong/dsh-go-mac',
    site: 'https://dsh.billw.top',
    siteLabel: 'dsh.billw.top',
    description: 'A native macOS client for DeepSeek Harness — same engine, zero migration, with live run views, notification approvals and native animations. Ported from DSH Go to Apple Silicon.',
    note: 'Open source · Flutter + Swift · AGPL-3.0',
    featured: true,
  },
  {
    name: 'contextlint',
    href: 'https://github.com/BillWGong/contextlint',
    description: 'A second pair of eyes for coding-agent instructions. Source evidence, conflict checks, and bilingual offline reports.',
    note: 'Open source · Developer tooling',
  },
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
          <img class="avatar" :src="avatar1x" :srcset="`${avatar1x} 1x, ${avatar2x} 2x`" width="152" height="152" alt="BillW Gong" fetchpriority="high" />
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
          <div v-for="project in projects" :key="project.name" class="project" :class="{ 'project-featured': project.featured }">
            <a class="project-link" :href="project.href">
              <span>{{ project.name }}</span><PageIcon name="external" />
            </a>
            <p class="project-description">{{ project.description }}</p>
            <p v-if="project.site" class="project-links">
              <a class="project-site" :href="project.site">{{ project.siteLabel }}<PageIcon name="external" /></a>
              <a :href="project.href">GitHub<PageIcon name="external" /></a>
            </p>
            <span class="project-note">{{ project.note }}</span>
          </div>
        </div>
      </section>

      <section class="section-row" aria-labelledby="now-title">
        <h2 id="now-title">now</h2>
        <ul class="updates">
          <li v-for="update in updates" :key="update">{{ update }}</li>
        </ul>
      </section>

      <section class="section-row" aria-labelledby="github-title">
        <h2 id="github-title">on github</h2>
        <div>
          <a class="gh-card" href="https://ghfind.com/u/billwgong?ref=badge">
            <img class="gh-card-light" src="https://ghfind.com/api/card/mini/billwgong?theme=light&amp;lang=en" alt="GitHub Roast score card" width="440" height="200" loading="lazy" />
            <img class="gh-card-dark" src="https://ghfind.com/api/card/mini/billwgong?theme=dark&amp;lang=en" alt="GitHub Roast score card" width="440" height="200" loading="lazy" />
          </a>
        </div>
      </section>

      <section class="section-row contact-section" aria-labelledby="contact-title">
        <h2 id="contact-title">find me</h2>
        <div>
          <ul class="social-links">
            <li v-for="link in links" :key="link.label">
              <a :href="link.href">{{ link.label }}<PageIcon name="external" /></a>
            </li>
          </ul>
          <p class="contact-note">Building in public. Come say hi <span role="img" aria-label="love">♡</span></p>
        </div>
      </section>
    </main>

    <footer>
      <span>© {{ new Date().getFullYear() }} BillW Gong</span>
      <a href="https://billw.top">billw.top<PageIcon name="external" /></a>
    </footer>
  </div>
</template>
