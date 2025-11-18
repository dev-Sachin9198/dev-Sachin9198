<h1>Hi Sachin yadav</h1>
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Animated Personal Portfolio</title>
  <meta name="description" content="Animated personal portfolio - HTML, CSS, JS single file" />

  <!-- Google Fonts (optional) -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg1:#0f172a; --bg2:#071029; --accent:#7c3aed; --muted:#94a3b8; --glass: rgba(255,255,255,0.06);
      --card: rgba(255,255,255,0.03);
      --glass-2: rgba(255,255,255,0.03);
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter,system-ui,Segoe UI,Roboto,'Helvetica Neue',Arial;color:#e6eef8;background:linear-gradient(135deg,var(--bg1),var(--bg2));-webkit-font-smoothing:antialiased}

    /* Page layout */
    .container{max-width:1100px;margin:0 auto;padding:40px 20px}
    header{display:flex;align-items:center;justify-content:space-between;gap:16px}

    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:46px;height:46px;border-radius:10px;background:linear-gradient(135deg,#8b5cf6,#06b6d4);display:flex;align-items:center;justify-content:center;font-weight:700;color:white}
    .nav{display:flex;gap:12px;align-items:center}
    .nav a{color:var(--muted);text-decoration:none;padding:8px 12px;border-radius:8px;font-weight:600}
    .nav a:hover{color:white;background:rgba(255,255,255,0.03)}

    /* hero */
    .hero{display:grid;grid-template-columns:1fr 380px;gap:28px;align-items:center;padding:60px 0}
    .hero-left h1{font-size:36px;margin:0 0 8px;line-height:1.05}
    .focus{background:linear-gradient(90deg,var(--accent),#06b6d4);-webkit-background-clip:text;background-clip:text;color:transparent}
    .typing{height:28px;margin:6px 0;color:var(--muted);font-weight:600}

    .cta{display:flex;gap:12px;margin-top:18px}
    .btn{padding:10px 16px;border-radius:10px;border:0;font-weight:700;cursor:pointer}
    .btn-primary{background:linear-gradient(90deg,var(--accent),#06b6d4);color:white;box-shadow:0 6px 20px rgba(124,58,237,0.18);}
    .btn-ghost{background:transparent;color:var(--muted);border:1px solid rgba(255,255,255,0.04)}

    /* hero right card */
    .profile-card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:20px;border-radius:14px;backdrop-filter:blur(6px);box-shadow:0 8px 30px rgba(2,6,23,0.5);}
    .avatar{width:100%;border-radius:10px;overflow:hidden}
    .avatar img{width:100%;display:block}
    .skills-row{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
    .chip{padding:6px 8px;border-radius:999px;font-weight:700;background:var(--card);color:var(--muted);font-size:13px}

    /* sections */
    section{padding:48px 0;border-top:1px solid rgba(255,255,255,0.02)}
    h2.section-title{font-size:20px;margin:0 0 18px}

    .about{display:flex;gap:20px;align-items:center}
    .about p{color:var(--muted);line-height:1.6}

    /* skills bars */
    .skill{margin-bottom:12px}
    .skill .label{display:flex;justify-content:space-between;font-weight:700;color:#dbeafe}
    .bar{height:10px;background:rgba(255,255,255,0.03);border-radius:999px;margin-top:6px;overflow:hidden}
    .bar > i{display:block;height:100%;border-radius:999px;background:linear-gradient(90deg,var(--accent),#06b6d4);width:0%;transition:width 1.2s cubic-bezier(.2,.9,.3,1)}

    /* projects grid */
    .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:16px;border-radius:12px;transition:transform .35s, box-shadow .35s;cursor:pointer}
    .card:hover{transform:translateY(-8px);box-shadow:0 20px 40px rgba(2,6,23,0.6)}
    .card h3{margin:0 0 8px}
    .card p{color:var(--muted);margin:0 0 12px}

    /* contact form */
    .contact-grid{display:grid;grid-template-columns:1fr 320px;gap:18px}
    .form-input{width:100%;padding:12px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:#e6eef8}

    footer{padding:24px 0;text-align:center;color:var(--muted)}

    /* small screens */
    @media (max-width:880px){
      .hero{grid-template-columns:1fr;}
      .contact-grid{grid-template-columns:1fr}
      .nav{display:none}
    }

    /* subtle animated background */
    .bg-orb{position:fixed;right:-120px;top:-120px;width:420px;height:420px;border-radius:50%;background:radial-gradient(circle at 30% 30%, rgba(124,58,237,0.18), transparent 35%);filter:blur(40px);pointer-events:none;mix-blend-mode:screen;animation:float 12s ease-in-out infinite}
    .bg-orb.two{left:-140px;bottom:-140px;background:radial-gradient(circle at 30% 30%, rgba(6,182,212,0.12), transparent 35%);animation-duration:16s}
    @keyframes float{0%{transform:translateY(0) rotate(0)}50%{transform:translateY(18px) rotate(10deg)}100%{transform:translateY(0) rotate(0)}}

    /* reveal animation */
    .reveal{opacity:0;transform:translateY(18px);transition:all .8s cubic-bezier(.2,.9,.3,1)}
    .reveal.visible{opacity:1;transform:none}

    /* tiny utilities */
    .muted{color:var(--muted)}
    .center{display:flex;align-items:center;justify-content:center}
  </style>
</head>
<body>

  <div class="bg-orb"></div>
  <div class="bg-orb two"></div>

  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">SY</div>
        <div>
          <div style="font-weight:800">Sachin Yadav</div>
          <div class="muted" style="font-size:12px;margin-top:2px">Full Stack Web Developer</div>
        </div>
      </div>

      <nav class="nav">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main>
      <section class="hero">
        <div class="hero-left">
          <h1 class="reveal">Hey, I'm <span class="focus">Sachin</span> — I build beautiful web apps.</h1>
          <div class="typing reveal" id="typing"></div>
          <p class="muted reveal">I design and develop responsive single-page applications and fast websites. I love clean UI, micro-interactions, and writing maintainable code.</p>

          <div class="cta reveal">
            <button class="btn btn-primary" id="hireBtn">Hire Me</button>
            <button class="btn btn-ghost" id="viewResume">Download Resume</button>
          </div>

          <div style="margin-top:20px" class="reveal">
            <strong class="muted">Tech I use:</strong>
            <div class="skills-row" style="margin-top:10px">
              <span class="chip">HTML</span>
              <span class="chip">CSS</span>
              <span class="chip">JavaScript</span>
              <span class="chip">React</span>
              <span class="chip">Node.js</span>
              <span class="chip">Python</span>
            </div>
          </div>
        </div>

        <aside class="profile-card reveal">
          <div class="avatar">
            <!-- Replace with your image -->
            <img src="2.jpg" alt="avatar">
          </div>

          <div style="margin-top:12px;display:flex;justify-content:space-between;align-items:center">
            <div>
              <div style="font-weight:800">Full Stack Developer</div>
              <div class="muted" style="font-size:13px">Based in India • Open to freelance</div>
            </div>
            <div style="text-align:right">
              <div style="font-weight:800;font-size:18px">5+</div>
              <div class="muted" style="font-size:12px">Years exp</div>
            </div>
          </div>

          <div class="skills-row" style="margin-top:14px">
            <span class="chip">Vue</span>
            <span class="chip">Django</span>
            <span class="chip">SQL</span>
            <span class="chip">Git</span>
          </div>
        </aside>
      </section>

      <section id="about">
        <h2 class="section-title reveal">About Me</h2>
        <div class="about">
          <div style="flex:1">
            <p class="reveal">I'm a passionate full-stack web developer who builds performant and accessible websites. I enjoy converting ideas into polished products — from prototyping to deployment. I specialize in building SPA's, REST APIs and interactive UIs.</p>
            <p class="muted reveal">Outside work I love reading, open-source contributions, and experimenting with subtle UI animations.</p>
          </div>
          <div style="width:260px" class="reveal">
            <div class="card">
              <div style="font-weight:700">Contact</div>
              <div class="muted" style="font-size:13px;margin-top:6px">sachin@example.com</div>
              <div style="margin-top:8px"><button class="btn btn-primary" style="width:100%;">Email me</button></div>
            </div>
          </div>
        </div>
      </section>

      <section id="skills">
        <h2 class="section-title reveal">Skills</h2>
        <div style="display:grid;grid-template-columns:1fr 1fr;gap:20px;align-items:start">
          <div>
            <div class="skill reveal"><div class="label">HTML <span class="muted">95%</span></div><div class="bar"><i data-width="95"></i></div></div>
            <div class="skill reveal"><div class="label">CSS <span class="muted">92%</span></div><div class="bar"><i data-width="92"></i></div></div>
            <div class="skill reveal"><div class="label">JavaScript <span class="muted">88%</span></div><div class="bar"><i data-width="88"></i></div></div>
            <div class="skill reveal"><div class="label">React <span class="muted">84%</span></div><div class="bar"><i data-width="84"></i></div></div>
          </div>

          <div>
            <div class="skill reveal"><div class="label">Node.js <span class="muted">80%</span></div><div class="bar"><i data-width="80"></i></div></div>
            <div class="skill reveal"><div class="label">Python <span class="muted">78%</span></div><div class="bar"><i data-width="78"></i></div></div>
            <div class="skill reveal"><div class="label">SQL <span class="muted">72%</span></div><div class="bar"><i data-width="72"></i></div></div>
            <div class="skill reveal"><div class="label">UI/UX <span class="muted">70%</span></div><div class="bar"><i data-width="70"></i></div></div>
          </div>
        </div>
      </section>

      <section id="projects">
        <h2 class="section-title reveal">Projects</h2>
        <div class="projects-grid">
          <article class="card reveal">
            <h3>Calculator App</h3>
            <p class="muted">A minimal calculator with keyboard support and nice animations.</p>
            <div style="display:flex;gap:8px;margin-top:10px">
              <button class="btn btn-ghost">View</button>
              <button class="btn btn-primary">Code</button>
            </div>
          </article>

          <article class="card reveal">
            <h3>Portfolio Template</h3>
            <p class="muted">This very template — responsive, single file, easy to customize.</p>
            <div style="display:flex;gap:8px;margin-top:10px">
              <button class="btn btn-ghost">Preview</button>
              <button class="btn btn-primary">Fork</button>
            </div>
          </article>

          <article class="card reveal">
            <h3>Chat Application</h3>
            <p class="muted">Realtime chat using WebSockets and a simple Node backend.</p>
            <div style="display:flex;gap:8px;margin-top:10px">
              <button class="btn btn-ghost">Demo</button>
              <button class="btn btn-primary">Source</button>
            </div>
          </article>

          <article class="card reveal">
            <h3>Task Manager</h3>
            <p class="muted">A productivity app with drag & drop and offline support.</p>
            <div style="display:flex;gap:8px;margin-top:10px">
              <button class="btn btn-ghost">Open</button>
              <button class="btn btn-primary">GitHub</button>
            </div>
          </article>
        </div>
      </section>

      <section id="contact">
        <h2 class="section-title reveal">Contact</h2>
        <div class="contact-grid">
          <form id="contactForm" class="reveal" onsubmit="return false;">
            <input class="form-input" placeholder="Your name" id="name" required style="margin-bottom:10px">
            <input class="form-input" placeholder="Email" id="email" required style="margin-bottom:10px">
            <textarea class="form-input" placeholder="Message" id="message" rows="6" required></textarea>
            <div style="margin-top:10px"><button class="btn btn-primary" id="sendBtn">Send Message</button></div>
          </form>

          <div class="reveal" style="padding:14px;border-radius:12px;background:var(--glass-2);">
            <h3 style="margin:0 0 8px">Get in touch</h3>
            <p class="muted">Feel free to email me or connect on LinkedIn. I typically respond within a few business days.</p>
            <div style="margin-top:10px;display:flex;gap:8px">
              <a class="btn btn-ghost">LinkedIn</a>
              <a class="btn btn-ghost">GitHub</a>
            </div>
          </div>
        </div>
      </section>

    </main>

    <footer>
      <div class="muted">© <span id="year"></span> </div>
    </footer>
  </div>

  <script>
    // small helpers and interactions
    document.getElementById('year').innerText = new Date().getFullYear();

    // typing effect (simple)
    const phrases = ['Hey, Im Sachin yadav', 'Frontend • Backend • Full Stack Developer', 'Accessible, fast websites'];
    const typingEl = document.getElementById('typing');
    let pIndex = 0, chIndex = 0, back = false;
    function tick(){
      const txt = phrases[pIndex];
      if(!back){
        chIndex++;
        typingEl.innerText = txt.slice(0,chIndex);
        if(chIndex >= txt.length){ back = true; setTimeout(tick,1200); return }
      } else {
        chIndex--;
        typingEl.innerText = txt.slice(0,chIndex);
        if(chIndex <= 0){ back=false; pIndex = (pIndex+1)%phrases.length }
      }
      setTimeout(tick,80 + Math.random()*60);
    }
    tick();

    // reveal on scroll + animate skill bars
    const reveals = document.querySelectorAll('.reveal');
    const skillBars = document.querySelectorAll('.bar > i');

    const io = new IntersectionObserver((entries)=>{
      entries.forEach(entry=>{
        if(entry.isIntersecting){
          entry.target.classList.add('visible');
          // animate skill bars when their container is visible
          skillBars.forEach(b=>{ const w = b.getAttribute('data-width'); b.style.width = w + '%'; });
        }
      });
    },{threshold:0.12});
    reveals.forEach(r=>io.observe(r));

    // small 'Hire me' action
    document.getElementById('hireBtn').addEventListener('click', ()=>{
      document.getElementById('contact').scrollIntoView({behavior:'smooth'});
      document.getElementById('name').focus();
    });

    // resume button (download dummy file)
    document.getElementById('viewResume').addEventListener('click', ()=>{
      const blob = new Blob([`Resume - Sachin Yadav\n\nExperience:\n- Full Stack Developer`],{type:'text/plain'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href = url; a.download = 'Sachin_Yadav_Resume.txt'; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
    });

    // contact form (demo only)
    document.getElementById('sendBtn').addEventListener('click', ()=>{
      const n = document.getElementById('name').value.trim();
      const e = document.getElementById('email').value.trim();
      const m = document.getElementById('message').value.trim();
      if(!n||!e||!m){alert('Please fill all fields');return}
      alert('Thanks '+n+' — message sent (demo)')
      document.getElementById('contactForm').reset();
    });

    // small accessibility: keyboard focus styles
    document.addEventListener('keydown', (e)=>{
      if(e.key === 'Tab') document.body.classList.add('user-tab');
    });

    // bonus: simple keyboard shortcut to jump to projects (press P)
    document.addEventListener('keyup', (e)=>{ if(e.key.toLowerCase()==='p'){document.getElementById('projects').scrollIntoView({behavior:'smooth'})}})
  </script>
</body>
</html>


studying Information Technology
💻 Learning Full Stack Web Development (Front-end + Back-end)
🔐 Exploring Cybersecurity fundamentals and secure development practices
🗄️ Practicing Databases (SQL & NoSQL) and data modeling
🛠️ Skills
Front-end
HTML5 · CSS3 · JavaScript (ES6+) · React · Tailwind CSS · Responsive Design
Back-end
Node.js · Express.js · RESTful APIs · JWT Authentication
Databases
MongoDB · Mongoose · MySQL · PostgreSQL · SQL
Security & DevOps Basics
OWASP fundamentals · HTTPS · CORS · Environment variables · Git & GitHub · Basic Docker
Tools & Others
Git · GitHub · VS Code · Postman · npm · Linux basics
