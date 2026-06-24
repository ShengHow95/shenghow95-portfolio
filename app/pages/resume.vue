<template>
  <div class="container section">
    <div class="mb-8 terminal-window back-nav">
      <NuxtLink to="/" class="btn-back font-mono">
        <span class="comment"># Return to Home</span>
        <span class="command"><span class="prompt">$</span> cd ../</span>
      </NuxtLink>
    </div>

    <div class="grid md:grid-cols-3 gap-8 resume-grid">
      <div class="col-main md:col-span-2">
        <h2 class="mb-6">cat ./experience.log</h2>
        <div class="timeline">
          <ExperienceCard 
            v-for="(job, index) in experience" 
            :key="index"
            :role="job.role"
            :company="job.company"
            :duration="job.duration"
            :location="job.location"
            :responsibilities="job.responsibilities"
          />
        </div>
      </div>

      <div class="col-sidebar">
        <div class="mb-6 terminal-window sidebar-section">
          <h2 class="mb-4">cat ./education.txt</h2>
          <div class="education-item" v-for="(edu, index) in education" :key="index">
            <h4 class="edu-degree font-mono">{{ edu.degree }}</h4>
            <div class="edu-school">{{ edu.school }}</div>
            <div class="edu-year font-mono">{{ edu.year }}</div>
          </div>
        </div>

        <div class="terminal-window sidebar-section">
          <h2 class="mb-4">ping contact</h2>
          <ul class="contact-list font-mono">
            <li>> email: <a href="mailto:shenghow95@gmail.com">shenghow95@gmail.com</a></li>
            <li>> linkedin: <a href="https://www.linkedin.com/in/sheng-how-kong" target="_blank">Profile</a></li>
            <li>> github: <a href="https://github.com/ShengHow95" target="_blank">ShengHow95</a></li>
            <li>> location: Singapore</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const experience = [
  {
    role: 'Senior Software Engineer',
    company: 'Horangi Cyber Security - a Bitdefender company',
    duration: 'April 2024 - Present',
    location: 'Singapore',
    responsibilities: []
  },
  {
    role: 'Backend Engineer',
    company: 'Horangi Cyber Security',
    duration: 'September 2022 - March 2024',
    location: 'Singapore',
    responsibilities: []
  },
  {
    role: 'Solutions Architect',
    company: 'Axrail Pte Ltd',
    duration: 'April 2021 - August 2022',
    location: 'Singapore',
    responsibilities: [
      'Design Scalable and Secure Applications on AWS',
      'Perform POC on New Technology Stacks or Designs',
      'Develop Cloud Native Applications on AWS'
    ]
  },
  {
    role: 'Software Engineer',
    company: 'Syion',
    duration: 'August 2020 - March 2021',
    location: 'Singapore',
    responsibilities: [
      'Develop Web Apps with Python, Nodejs and Vuejs',
      'Solution implementation with AWS Serverless Architecture'
    ]
  },
  {
    role: 'Research Development Software Engineer',
    company: 'Keysight Technologies',
    duration: 'August 2019 - July 2020',
    location: 'Penang, Malaysia',
    responsibilities: [
      'Develop Desktop Apps with Angular & Modern C++',
      'Develop API using gRPC',
      'Develop Test Plan using C# (OpenTAP)'
    ]
  },
  {
    role: 'Test Engineer',
    company: 'Keysight Technologies',
    duration: 'January 2018 - August 2019',
    location: 'Penang, Malaysia',
    responsibilities: [
      'Test Program Development and Automation using C#, VB6 and VEE Pro',
      'Product Quality Compliance with ISO17025 and ISO9001 Standards'
    ]
  },
  {
    role: 'Research Development Test Engineer',
    company: 'Keysight Technologies',
    duration: 'December 2016 - March 2017',
    location: 'Penang, Malaysia',
    responsibilities: [
      'Test Program Development using VEE pro',
      'Test Automation using VEE Pro'
    ]
  }
];

const education = [
  {
    school: 'Universiti Sains Malaysia',
    degree: 'Master of Science - MS, Data Science And Analytics',
    year: '2019 - 2020'
  },
  {
    school: 'Curtin University Malaysia',
    degree: 'Bachelor of Electrical Power Engineering',
    year: '2014 - 2017'
  },
  {
    school: 'Curtin University Malaysia',
    degree: 'Foundation degree, Science and Engineering',
    year: '2013 - 2014'
  }
];
</script>

<style scoped>
.btn-back {
  display: flex;
  flex-direction: column;
  color: var(--color-text);
  font-weight: 500;
  transition: var(--transition);
  text-decoration: none;
}
.btn-back:hover .command {
  color: var(--color-primary);
}
.btn-back .comment {
  color: var(--color-text-muted);
  font-size: 0.85rem;
  margin-bottom: 0.25rem;
}
.btn-back .prompt {
  color: var(--color-terminal);
  margin-right: 0.5rem;
}
/* Back nav & sidebar boxes */
.back-nav {
  padding: 0.75rem 1rem;
}
@media (min-width: 480px) {
  .back-nav {
    padding: 1rem 1.5rem;
  }
}
@media (min-width: 768px) {
  .back-nav {
    padding: 1rem 2rem;
  }
}
.sidebar-section {
  padding: 1rem;
}
@media (min-width: 768px) {
  .sidebar-section {
    padding: 1.5rem;
  }
}
.md\:col-span-2 {
  grid-column: span 2 / span 2;
}
.education-item {
  margin-bottom: 1.5rem;
  border-left: 2px solid rgba(88, 166, 255, 0.3);
  padding-left: 1rem;
}
.edu-degree {
  margin-bottom: 0.25rem;
  font-size: 1rem;
  color: var(--color-text);
}
@media (min-width: 768px) {
  .edu-degree {
    font-size: 1.1rem;
  }
}
.edu-school {
  color: var(--color-primary);
  font-size: 0.9rem;
}
.edu-year {
  font-size: 0.8rem;
  color: var(--color-text-muted);
  margin-top: 0.25rem;
}
.contact-list {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
.contact-list li {
  margin-bottom: 0.75rem;
  color: var(--color-text-muted);
  font-size: 0.85rem;
  word-break: break-word;
}
.contact-list a {
  color: var(--color-primary);
}
.contact-list a:hover {
  color: var(--color-primary-glow);
}
@media (max-width: 768px) {
  .resume-grid {
    grid-template-columns: 1fr;
  }
  .md\:col-span-2 {
    grid-column: span 1 / span 1;
  }
}
</style>
