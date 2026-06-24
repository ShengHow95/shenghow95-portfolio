<template>
  <div class="container section flex flex-col items-center justify-center" style="min-height: 80vh;">
    <div class="terminal-window w-full max-w-3xl">
      <div class="terminal-header">
        <div class="terminal-dots">
          <div class="terminal-dot dot-red"></div>
          <div class="terminal-dot dot-yellow"></div>
          <div class="terminal-dot dot-green"></div>
        </div>
        <div class="terminal-title">guest@shenghow-portfolio ~</div>
      </div>
      
      <div class="terminal-body">
        <h2 class="mb-2">whoami</h2>
        <h1 class="mb-2 typing-cursor">Sheng How Kong</h1>
        <h3 class="text-muted font-mono mb-6">// I Create Bugs</h3>
        
        <p class="summary-text mb-8 font-mono" style="color: var(--color-text-muted);">
          > Passionate about designing scalable and secure cloud-native applications.<br/>
          > Focusing on backend systems, cloud infrastructure, and solution architecting.<br/>
          > I also enjoy exploring new technologies and playing board games.
        </p>

        <h2 class="mb-4">ls ./skills</h2>
        
        <div class="skills-grid mb-8">
          <div class="skill-category">
            <h4 class="category-title">Backend</h4>
            <div class="flex gap-2" style="flex-wrap: wrap;">
              <SkillBadge v-for="skill in skills.backend" :key="skill" :name="skill" />
            </div>
          </div>
          
          <div class="skill-category">
            <h4 class="category-title">Cloud / DevOps</h4>
            <div class="flex gap-2" style="flex-wrap: wrap;">
              <SkillBadge v-for="skill in skills.cloud" :key="skill" :name="skill" />
            </div>
          </div>
          
          <div class="skill-category">
            <h4 class="category-title">Architecture</h4>
            <div class="flex gap-2" style="flex-wrap: wrap;">
              <SkillBadge v-for="skill in skills.architecture" :key="skill" :name="skill" />
            </div>
          </div>
        </div>

        <div class="cta-buttons mt-8">
          <NuxtLink to="/resume" class="btn btn-primary">cat ./resume.md</NuxtLink>
          <a href="https://github.com/ShengHow95" target="_blank" class="btn btn-secondary">curl ./github</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const skills = {
  backend: ['Python', 'Rust'],
  cloud: ['AWS', 'GCP', 'Kubernetes'],
  architecture: ['Spec Driven Development', 'Solution Architecting']
}
</script>

<style scoped>
.text-muted {
  color: var(--color-text-muted);
}
.summary-text {
  font-size: 0.9rem;
  line-height: 1.8;
}
.skills-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}
@media (min-width: 480px) {
  .skills-grid {
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 2rem;
  }
}
.category-title {
  color: var(--color-accent);
  font-family: var(--font-mono);
  font-size: 0.9rem;
  margin-bottom: 1rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
/* CTA buttons */
.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}
@media (min-width: 420px) {
  .cta-buttons {
    flex-direction: row;
    flex-wrap: wrap;
  }
}
.btn-secondary {
  border: 1px solid var(--color-text-muted);
  color: var(--color-text);
  background: transparent;
}
.btn-secondary:hover {
  border-color: var(--color-primary);
  color: var(--color-primary);
  text-decoration: none;
}
</style>
