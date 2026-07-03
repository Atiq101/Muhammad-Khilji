<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muhammad Khilji — Cloud Networks & DevOps Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #0A0F1E;
    --panel: #101A30;
    --panel-2: #0D1526;
    --line: #1E2C48;
    --text: #DCE4F5;
    --muted: #7C8CB0;
    --accent: #3DA9FC;
    --accent-2: #45E0C8;
    --accent-dim: rgba(61,169,252,0.12);
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter',sans-serif;
    line-height:1.6;
    overflow-x:hidden;
  }
  ::selection{background:var(--accent);color:#000;}

  .grid-bg{
    position:fixed; inset:0; z-index:0; pointer-events:none;
    background-image:
      linear-gradient(var(--line) 1px, transparent 1px),
      linear-gradient(90deg, var(--line) 1px, transparent 1px);
    background-size:48px 48px;
    opacity:0.35;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 20%, black 40%, transparent 90%);
  }

  header, section, footer{position:relative; z-index:1;}

  nav{
    position:fixed; top:0; left:0; right:0; z-index:50;
    display:flex; justify-content:space-between; align-items:center;
    padding:18px 6vw;
    backdrop-filter:blur(10px);
    background:rgba(10,15,30,0.75);
    border-bottom:1px solid var(--line);
  }
  .logo{
    font-family:'JetBrains Mono',monospace;
    font-weight:600; font-size:15px; color:var(--accent-2);
    letter-spacing:0.5px;
  }
  .logo span{color:var(--muted);}
  nav ul{display:flex; gap:28px; list-style:none;}
  nav a{
    color:var(--muted); text-decoration:none; font-size:13px;
    font-family:'JetBrains Mono',monospace;
    transition:color 0.2s;
  }
  nav a:hover{color:var(--accent-2);}

  .hero{
    min-height:100vh;
    display:flex; flex-direction:column; justify-content:center;
    padding:130px 6vw 60px;
    max-width:1100px;
  }
  .hero-top{
    display:flex; align-items:center; gap:22px;
    margin-bottom:26px;
  }
  .profile-pic{
    width:110px; height:110px; border-radius:50%;
    padding:4px;
    background:linear-gradient(135deg, var(--accent), var(--accent-2));
    flex-shrink:0;
    box-shadow:0 10px 40px rgba(61,169,252,0.2);
  }
  .profile-pic img{
    width:100%; height:100%; border-radius:50%;
    object-fit:cover; display:block;
    border:4px solid var(--bg);
  }
  .eyebrow{
    font-family:'JetBrains Mono',monospace;
    color:var(--accent-2);
    font-size:13px;
    letter-spacing:2px;
    text-transform:uppercase;
    display:flex; align-items:center; gap:10px;
    margin-bottom:6px;
  }
  .eyebrow::before{
    content:''; width:8px; height:8px; border-radius:50%;
    background:var(--accent-2); box-shadow:0 0 10px var(--accent-2);
    animation:pulse 2s infinite;
  }
  @keyframes pulse{0%,100%{opacity:1;} 50%{opacity:0.3;}}
  .hero-name{
    font-family:'Space Grotesk',sans-serif;
    font-size:1.5rem; font-weight:600; color:var(--text);
  }
  .hero-loc{
    font-family:'JetBrains Mono',monospace; font-size:13px; color:var(--muted); margin-top:2px;
  }

  .terminal{
    background:var(--panel);
    border:1px solid var(--line);
    border-radius:10px;
    max-width:660px;
    margin-bottom:32px;
    overflow:hidden;
    box-shadow:0 20px 60px rgba(0,0,0,0.4);
  }
  .terminal-bar{
    display:flex; align-items:center; gap:8px;
    padding:10px 14px;
    background:var(--panel-2);
    border-bottom:1px solid var(--line);
  }
  .dot{width:10px;height:10px;border-radius:50%;}
  .dot.r{background:#FF5F57;} .dot.y{background:#FEBC2E;} .dot.g{background:#28C840;}
  .terminal-title{
    margin-left:auto; margin-right:auto;
    font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--muted);
    transform:translateX(-14px);
  }
  .terminal-body{
    padding:20px 22px 26px;
    font-family:'JetBrains Mono',monospace;
    font-size:13.5px;
    color:var(--text);
  }
  .terminal-body .cmd{color:var(--accent-2);}
  .out-line{margin-top:6px; color:var(--muted);}
  .out-line b{color:var(--text); font-weight:500;}
  .cursor{
    display:inline-block; width:8px; height:16px; background:var(--accent-2);
    vertical-align:middle; margin-left:4px;
    animation:blink 1s steps(1) infinite;
  }
  @keyframes blink{50%{opacity:0;}}

  h1{
    font-family:'Space Grotesk',sans-serif;
    font-size:clamp(2.2rem, 5.5vw, 3.8rem);
    font-weight:700;
    line-height:1.08;
    letter-spacing:-0.02em;
    margin-bottom:20px;
  }
  h1 .grad{
    background:linear-gradient(90deg, var(--accent), var(--accent-2));
    -webkit-background-clip:text; background-clip:text; color:transparent;
  }
  .hero p.lead{
    max-width:680px; color:var(--muted); font-size:16.5px; margin-bottom:34px;
  }
  .hero-actions{display:flex; gap:16px; flex-wrap:wrap;}
  .btn{
    font-family:'JetBrains Mono',monospace;
    font-size:14px;
    padding:13px 26px;
    border-radius:8px;
    text-decoration:none;
    display:inline-flex; align-items:center; gap:8px;
    transition:transform 0.2s, box-shadow 0.2s;
    border:none; cursor:pointer;
  }
  .btn-primary{
    background:linear-gradient(90deg, var(--accent), var(--accent-2));
    color:#04101F; font-weight:600;
  }
  .btn-primary:hover{transform:translateY(-2px); box-shadow:0 10px 30px var(--accent-dim);}
  .btn-ghost{
    border:1px solid var(--line); color:var(--text);
  }
  .btn-ghost:hover{border-color:var(--accent); color:var(--accent-2); transform:translateY(-2px);}

  .stats{
    display:grid; grid-template-columns:repeat(4,1fr);
    max-width:1100px; margin:0 6vw 100px;
    border:1px solid var(--line); border-radius:12px; overflow:hidden;
  }
  .stat{
    padding:26px 16px; text-align:center;
    border-right:1px solid var(--line);
    background:var(--panel);
  }
  .stat:last-child{border-right:none;}
  .stat .num{
    font-family:'Space Grotesk',sans-serif; font-size:1.8rem; font-weight:700;
    color:var(--accent-2);
  }
  .stat .lbl{font-size:11px; color:var(--muted); margin-top:6px; font-family:'JetBrains Mono',monospace; letter-spacing:0.5px;}

  section{padding:90px 6vw; max-width:1200px; margin:0 auto;}
  .section-head{margin-bottom:46px;}
  .section-tag{
    font-family:'JetBrains Mono',monospace; color:var(--accent); font-size:13px;
    letter-spacing:2px; text-transform:uppercase; margin-bottom:10px; display:block;
  }
  .section-title{
    font-family:'Space Grotesk',sans-serif; font-size:2.1rem; font-weight:700;
  }

  .about-grid{display:grid; grid-template-columns:1.15fr 0.85fr; gap:60px; align-items:start;}
  .about-grid p{color:var(--muted); margin-bottom:18px; font-size:16px;}
  .about-grid p b{color:var(--text);}
  .focus-list{display:flex; flex-direction:column; gap:10px;}
  .focus-item{
    background:var(--panel); border:1px solid var(--line); border-radius:10px;
    padding:14px 18px; font-size:14px; color:var(--text);
    display:flex; align-items:center; gap:10px;
  }
  .focus-item::before{content:'▹'; color:var(--accent);}

  .skills-grid{
    display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:16px;
  }
  .skill-card{
    background:var(--panel); border:1px solid var(--line); border-radius:10px;
    padding:22px; transition:border-color 0.2s, transform 0.2s;
  }
  .skill-card:hover{border-color:var(--accent); transform:translateY(-3px);}
  .skill-card .cat{
    font-family:'JetBrains Mono',monospace; color:var(--accent-2); font-size:12px;
    letter-spacing:1px; text-transform:uppercase; margin-bottom:10px; display:block;
  }
  .skill-card ul{list-style:none; color:var(--muted); font-size:13.5px;}
  .skill-card li{padding:4px 0; display:flex; align-items:flex-start; gap:8px; line-height:1.4;}
  .skill-card li::before{content:'▹'; color:var(--accent); flex-shrink:0;}

  .cert-grid{display:grid; grid-template-columns:repeat(auto-fit,minmax(240px,1fr)); gap:16px;}
  .cert-card{
    background:var(--panel); border:1px solid var(--line); border-radius:10px;
    padding:22px; text-align:center;
  }
  .cert-card .cert-icon{
    width:44px; height:44px; border-radius:50%; margin:0 auto 14px;
    background:var(--accent-dim); display:flex; align-items:center; justify-content:center;
    color:var(--accent-2); font-family:'JetBrains Mono',monospace; font-weight:600; font-size:13px;
  }
  .cert-card h4{font-family:'Space Grotesk',sans-serif; font-size:15px; margin-bottom:4px;}
  .cert-card span{font-size:12px; color:var(--muted); font-family:'JetBrains Mono',monospace;}

  .exp-list{border-left:2px solid var(--line); padding-left:32px; display:flex; flex-direction:column; gap:36px;}
  .exp-item{position:relative;}
  .exp-item::before{
    content:''; position:absolute; left:-39px; top:4px;
    width:12px; height:12px; border-radius:50%;
    background:var(--accent-2); box-shadow:0 0 0 5px var(--accent-dim);
  }
  .exp-item.current::before{background:var(--accent); box-shadow:0 0 0 5px rgba(61,169,252,0.18);}
  .exp-dates{font-family:'JetBrains Mono',monospace; color:var(--accent-2); font-size:12.5px; margin-bottom:4px;}
  .exp-role{font-family:'Space Grotesk',sans-serif; font-weight:600; font-size:19px;}
  .exp-company{color:var(--muted); font-size:14px; margin-bottom:12px;}
  .exp-item ul{color:var(--muted); font-size:14.5px; padding-left:18px;}
  .exp-item li{margin-bottom:6px;}
  .exp-item li::marker{color:var(--accent);}

  .project-grid{display:grid; grid-template-columns:repeat(auto-fit,minmax(320px,1fr)); gap:20px;}
  .project-card{
    background:var(--panel); border:1px solid var(--line); border-radius:12px;
    padding:26px; transition:border-color 0.2s, transform 0.2s;
  }
  .project-card:hover{border-color:var(--accent); transform:translateY(-3px);}
  .project-card h3{font-family:'Space Grotesk',sans-serif; font-size:17px; margin-bottom:10px; line-height:1.35;}
  .project-card p{color:var(--muted); font-size:14px; margin-bottom:14px;}
  .project-metrics{display:flex; gap:8px; flex-wrap:wrap;}
  .metric{
    font-family:'JetBrains Mono',monospace; font-size:11.5px; color:var(--accent-2);
    background:var(--accent-dim); padding:5px 11px; border-radius:20px; white-space:nowrap;
  }

  .edu-grid{display:grid; grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); gap:16px;}
  .edu-card{
    background:var(--panel); border:1px solid var(--line); border-radius:10px; padding:22px;
  }
  .edu-card .yrs{font-family:'JetBrains Mono',monospace; color:var(--accent-2); font-size:12.5px;}
  .edu-card h4{font-family:'Space Grotesk',sans-serif; font-size:16px; margin:4px 0;}
  .edu-card span{color:var(--muted); font-size:13.5px;}

  .contact-box{
    background:linear-gradient(135deg, var(--panel), var(--panel-2));
    border:1px solid var(--line); border-radius:16px;
    padding:60px 6vw; text-align:center;
  }
  .contact-box h2{font-family:'Space Grotesk',sans-serif; font-size:2.2rem; margin-bottom:14px;}
  .contact-box p{color:var(--muted); margin-bottom:30px;}
  .contact-info{
    display:flex; justify-content:center; gap:24px; flex-wrap:wrap; margin-bottom:30px;
    font-family:'JetBrains Mono',monospace; font-size:13.5px; color:var(--muted);
  }
  .contact-info span{color:var(--accent-2);}

  footer{
    text-align:center; padding:36px; color:var(--muted);
    font-family:'JetBrains Mono',monospace; font-size:13px;
    border-top:1px solid var(--line);
  }

  @media(max-width:768px){
    .about-grid{grid-template-columns:1fr;}
    .stats{grid-template-columns:repeat(2,1fr);}
    .stat:nth-child(2){border-right:none;}
    nav ul{display:none;}
    .exp-list{padding-left:24px;}
    .exp-item::before{left:-31px;}
  }
</style>
</head>
<body>

<div class="grid-bg"></div>

<nav>
  <div class="logo">khilji<span>@cloud</span>:~$</div>
  <ul>
    <li><a href="#about">about</a></li>
    <li><a href="#experience">experience</a></li>
    <li><a href="#skills">stack</a></li>
    <li><a href="#certifications">certs</a></li>
    <li><a href="#projects">projects</a></li>
    <li><a href="#contact">contact</a></li>
  </ul>
</nav>

<header class="hero">
  <div class="hero-top">
    <div class="profile-pic">
      <img src="profile.png" alt="Muhammad Khilji" />
    </div>
    <div>
      <div class="eyebrow">Open to new opportunities</div>
      <div class="hero-name">Muhammad Khilji</div>
      <div class="hero-loc">Manchester, UK</div>
    </div>
  </div>

  <div class="terminal">
    <div class="terminal-bar">
      <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
      <div class="terminal-title">whoami.sh</div>
    </div>
    <div class="terminal-body">
      <div><span class="cmd">$</span> whoami</div>
      <div class="out-line"><b>Muhammad Khilji</b> — Cloud Networks & DevOps Engineer</div>
      <div style="margin-top:14px;"><span class="cmd">$</span> cat experience.log</div>
      <div class="out-line">7+ years across Azure & AWS · Terraform · AKS · Zero Trust<span class="cursor"></span></div>
    </div>
  </div>

  <h1>Designing <span class="grad">secure, scalable</span><br>cloud & network architectures.</h1>
  <p class="lead">Cloud Networks & DevOps Engineer with 7+ years of experience delivering secure, scalable, and highly available solutions across Microsoft Azure and AWS — spanning hybrid connectivity, enterprise networking, Infrastructure as Code, and CI/CD automation.</p>

  <div class="hero-actions">
    <a href="#experience" class="btn btn-primary">View experience →</a>
    <a href="#contact" class="btn btn-ghost">Get in touch</a>
  </div>
</header>

<div class="stats">
  <div class="stat"><div class="num">7+</div><div class="lbl">YEARS EXPERIENCE</div></div>
  <div class="stat"><div class="num">2</div><div class="lbl">CLOUD PLATFORMS</div></div>
  <div class="stat"><div class="num">4</div><div class="lbl">CERTIFICATIONS</div></div>
  <div class="stat"><div class="num">10</div><div class="lbl">ROLES DELIVERED</div></div>
</div>

<section id="about">
  <div class="section-head">
    <span class="section-tag">01 · About</span>
    <h2 class="section-title">Profile summary.</h2>
  </div>
  <div class="about-grid">
    <div>
      <p>Cloud Networks & DevOps Engineer with <b>7+ years of experience</b> designing and delivering secure, scalable, and highly available cloud solutions across <b>Microsoft Azure and AWS</b>. Strong expertise in cloud architecture design, hybrid connectivity, and enterprise networking, combined with hands-on implementation of <b>Infrastructure as Code (Terraform)</b> and <b>Azure DevOps CI/CD pipelines</b>.</p>
      <p>Proven track record leading cloud migration initiatives, modernizing legacy applications to <b>Azure Kubernetes Service (AKS)</b> using Docker, Helm, and GitOps (Argo CD), and embedding <b>SAST/DAST security controls</b> into automated delivery pipelines.</p>
      <p>Experienced in building resilient multi-region architectures, hub-and-spoke networking models, and implementing advanced monitoring and observability using <b>Azure Monitor, Prometheus, and Grafana</b> to ensure performance, reliability, and operational excellence.</p>
    </div>
    <div class="focus-list">
      <div class="focus-item">Cloud Infrastructure & Services</div>
      <div class="focus-item">Project Implementation & Migration</div>
      <div class="focus-item">Automation & Infrastructure as Code</div>
      <div class="focus-item">Monitoring & Performance</div>
      <div class="focus-item">Security & Access Management</div>
    </div>
  </div>
</section>

<section id="experience">
  <div class="section-head">
    <span class="section-tag">02 · Experience</span>
    <h2 class="section-title">Where I've delivered.</h2>
  </div>
  <div class="exp-list">

    <div class="exp-item current">
      <div class="exp-dates">MARCH 2026 — PRESENT</div>
      <div class="exp-role">Cloud Networks Engineer</div>
      <div class="exp-company">Zeroplus Ltd · Azure · AWS · Terraform · Zero Trust · Hybrid & Multi-Cloud</div>
      <ul>
        <li>Designed and implemented secure Hub-and-Spoke network architectures across Azure and AWS, integrating VNets, VPCs, Transit Gateway, VPN Gateway, Private Endpoints, Load Balancers, and Firewalls.</li>
        <li>Delivered Zero Trust networking using Zscaler Zero Trust Exchange (ZPA), configuring App Connectors for secure private access to enterprise applications.</li>
        <li>Designed hybrid and multi-cloud connectivity between Azure, AWS, and on-premises using ExpressRoute, Site-to-Site VPN, and private networking.</li>
        <li>Configured and managed Fortinet FortiGate Firewalls — policies, NAT rules, security profiles, IPsec VPNs, and HA.</li>
        <li>Leading migration of enterprise applications from Docker to Azure Kubernetes Service (AKS) using cloud-native architecture.</li>
        <li>Implemented secure private AKS connectivity using Zscaler App Connectors, Private Link, Private DNS Zones, and Internal Load Balancers.</li>
        <li>Automated Azure and AWS deployments using Terraform, Azure CLI, AWS CLI, and PowerShell — building reusable IaC modules.</li>
        <li>Developed CI/CD pipelines using Azure DevOps and GitHub, configuring Application Gateway (WAF), Load Balancers, and AWS ALB/NLB.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">MARCH 2024 — JAN 2026</div>
      <div class="exp-role">DevOps / Cloud Engineer</div>
      <div class="exp-company">CMS</div>
      <ul>
        <li>Designed and maintained scalable cloud infrastructure using Azure services.</li>
        <li>Automated infrastructure deployment with Terraform to ensure high availability.</li>
        <li>Built Azure CI/CD pipelines with embedded SAST/DAST security scanning.</li>
        <li>Containerized applications with Docker, deployed on AKS, and implemented GitOps-based delivery using Argo CD.</li>
        <li>Monitored performance and security using Azure Monitor, Prometheus, and Grafana.</li>
        <li>Automated Azure resource management using PowerShell, reducing manual intervention.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">NOV 2022 — JAN 2024</div>
      <div class="exp-role">Cloud Engineer</div>
      <div class="exp-company">Frasers Group</div>
      <ul>
        <li>Upgraded Cisco devices and resolved network faults with a structured, methodical approach.</li>
        <li>Configured Cisco ASA / Firepower firewalls, managing access rules for users.</li>
        <li>Monitored and troubleshot network performance using SolarWinds, minimizing downtime.</li>
        <li>Deployed and managed AWS infrastructure — Compute, S3, VPC, Route 53, Load Balancers.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">APR 2022 — OCT 2022</div>
      <div class="exp-role">Network Deployment Engineer</div>
      <div class="exp-company">Circle Health Group</div>
      <ul>
        <li>Replaced legacy Cisco hardware with Extreme Networks devices across multiple sites.</li>
        <li>Provided post-upgrade support and monitoring for stable network performance.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">JUN 2021 — MAR 2022</div>
      <div class="exp-role">Field Network Engineer</div>
      <div class="exp-company">NSC Global</div>
      <ul>
        <li>Deployed and staged Cisco equipment for enterprise clients, handling documentation and logistics.</li>
        <li>Evaluated network infrastructure, identified bottlenecks, and proposed design improvements.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">NOV 2019 — JUN 2021</div>
      <div class="exp-role">Cloud / Service Desk Engineer</div>
      <div class="exp-company">Tech Data</div>
      <ul>
        <li>Provided L1/L2 cloud and service desk support for Azure-hosted environments globally.</li>
        <li>Monitored Azure-hosted servers and services, acting within SLA and runbook requirements.</li>
        <li>Supported Azure, IBM Cloud, and Check Point platforms following ITIL-based processes.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">FEB 2017 — OCT 2019</div>
      <div class="exp-role">Network Support Engineer</div>
      <div class="exp-company">Prime Technology</div>
      <ul>
        <li>Maintained Cisco routers, switches, and firewalls; ensured network performance and uptime.</li>
        <li>Managed Active Directory, DNS, and DHCP, contributing to enterprise-level network stability.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">JAN 2016 — NOV 2016</div>
      <div class="exp-role">NOC Engineer</div>
      <div class="exp-company">Data Centre (SunGard)</div>
      <ul>
        <li>Delivered 1st/2nd line technical support to global clients via phone and email.</li>
        <li>Monitored critical network systems and maintained up-to-date technical documentation.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">MAY 2014 — JAN 2016</div>
      <div class="exp-role">Network Engineer / System Engineer</div>
      <div class="exp-company">Future Technologies</div>
      <ul>
        <li>Provided frontline network support to global customers, maintaining high service standards.</li>
        <li>Deployed and configured network environments using EIGRP and OSPF protocols.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-dates">NOV 2013 — APR 2014</div>
      <div class="exp-role">Infrastructure Support</div>
      <div class="exp-company">BHF (London)</div>
      <ul>
        <li>Delivered 1st/2nd line desktop and network support, resolving hardware and software issues.</li>
        <li>Managed software licensing and supported remote users via VPN.</li>
      </ul>
    </div>

  </div>
</section>

<section id="skills">
  <div class="section-head">
    <span class="section-tag">03 · Technical Skills</span>
    <h2 class="section-title">Tools I reach for.</h2>
  </div>
  <div class="skills-grid">
    <div class="skill-card">
      <span class="cat">Cloud Platforms</span>
      <ul><li>Microsoft Azure & AWS</li><li>Hybrid & multi-cloud architecture</li><li>Cost Management, Reserved Instances</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Azure Networking</span>
      <ul><li>VNets, NSGs, Load Balancer</li><li>Application Gateway, VPN, ExpressRoute</li><li>DNS</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Identity & Security</span>
      <ul><li>Azure AD — RBAC, MFA, Conditional Access</li><li>Privileged Identity Management (JIT)</li><li>Key Vault, Encryption</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Infrastructure as Code</span>
      <ul><li>Terraform for automated deployments</li><li>Azure CLI, AWS CLI, PowerShell</li><li>Reusable IaC modules</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Containers & Orchestration</span>
      <ul><li>Docker, Kubernetes (AKS)</li><li>Helm, GitOps (Argo CD)</li><li>RBAC & namespace isolation</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">CI/CD & DevOps</span>
      <ul><li>Azure DevOps pipelines, GitHub</li><li>SAST / DAST security scanning</li><li>Git version control</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Monitoring & Observability</span>
      <ul><li>Azure Monitor, Log Analytics</li><li>Prometheus & Grafana</li><li>SolarWinds, PRTG, Application Insights</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Routing & Switching</span>
      <ul><li>OSPF, EIGRP, BGP, RIP</li><li>Spanning Tree, RSTP, VRRP, HSRP, GLBP</li><li>Cisco 6500, Port Security</li></ul>
    </div>
    <div class="skill-card">
      <span class="cat">Firewalls & Security</span>
      <ul><li>Cisco ASA / Firepower, Palo Alto</li><li>Check Point, Cisco ISE</li><li>Fortinet FortiGate</li></ul>
    </div>
  </div>
</section>

<section id="certifications">
  <div class="section-head">
    <span class="section-tag">04 · Certifications</span>
    <h2 class="section-title">Credentials.</h2>
  </div>
  <div class="cert-grid">
    <div class="cert-card">
      <div class="cert-icon">AZ</div>
      <h4>Azure Administrator Associate</h4>
      <span>AZ-104 · 2025</span>
    </div>
    <div class="cert-card">
      <div class="cert-icon">AWS</div>
      <h4>AWS Solutions Architect</h4>
      <span>Associate · 2024</span>
    </div>
    <div class="cert-card">
      <div class="cert-icon">CC</div>
      <h4>CCNA / CCNP / JNCIA</h4>
      <span>Networking</span>
    </div>
    <div class="cert-card">
      <div class="cert-icon">MS</div>
      <h4>MCSA / MCSE</h4>
      <span>Microsoft Systems</span>
    </div>
  </div>
</section>

<section id="projects">
  <div class="section-head">
    <span class="section-tag">05 · Projects</span>
    <h2 class="section-title">Selected work.</h2>
  </div>
  <div class="project-grid">
    <div class="project-card">
      <h3>Secure hybrid cloud connectivity</h3>
      <p>Configured Site-to-Site VPN between Microsoft Azure and AWS, enabling encrypted cross-cloud communication and a resilient multi-cloud architecture.</p>
      <div class="project-metrics"><span class="metric">Azure</span><span class="metric">AWS</span><span class="metric">VPN</span></div>
    </div>
    <div class="project-card">
      <h3>Multi-region high availability</h3>
      <p>Architected highly available multi-region Azure infrastructure using Traffic Manager and Application Gateway for global load balancing and disaster recovery.</p>
      <div class="project-metrics"><span class="metric">Traffic Manager</span><span class="metric">DR Ready</span></div>
    </div>
    <div class="project-card">
      <h3>Hub-and-spoke network topology</h3>
      <p>Built scalable hub-and-spoke topology in Azure using VNet Peering and VPN Gateway for secure inter-region communication and centralized governance.</p>
      <div class="project-metrics"><span class="metric">VNet Peering</span><span class="metric">Governance</span></div>
    </div>
    <div class="project-card">
      <h3>IaC-driven CI/CD automation</h3>
      <p>Implemented Terraform integrated with Azure DevOps pipelines, enabling automated provisioning and consistent multi-environment deployments.</p>
      <div class="project-metrics"><span class="metric">Terraform</span><span class="metric">Azure DevOps</span></div>
    </div>
    <div class="project-card">
      <h3>Legacy-to-AKS modernization</h3>
      <p>Led modernization of legacy microservices by containerizing with Docker and migrating to AKS; implemented GitOps CI/CD with Argo CD and Helm, RBAC, and Prometheus/Grafana monitoring.</p>
      <div class="project-metrics"><span class="metric">Zero downtime</span><span class="metric">60% faster deploys</span></div>
    </div>
    <div class="project-card">
      <h3>On-prem to Azure migration</h3>
      <p>Directed end-to-end cloud migration of on-premises servers and databases to Azure IaaS and PaaS, including Azure SQL Managed Instance and SQL Database.</p>
      <div class="project-metrics"><span class="metric">35% cost reduction</span><span class="metric">99.95% availability</span></div>
    </div>
  </div>
</section>

<section id="education">
  <div class="section-head">
    <span class="section-tag">06 · Education</span>
    <h2 class="section-title">Academic background.</h2>
  </div>
  <div class="edu-grid">
    <div class="edu-card">
      <div class="yrs">2007 — 2008</div>
      <h4>Postgraduate Diploma in Business Administration (MBA)</h4>
      <span>London Business Academy</span>
    </div>
    <div class="edu-card">
      <div class="yrs">2002 — 2005</div>
      <h4>Bachelor of Information Technology (B.S.I.T)</h4>
      <span>University of Sindh · 3.14 CGPA</span>
    </div>
  </div>
</section>

<section id="contact">
  <div class="contact-box">
    <h2>Let's build something reliable.</h2>
    <p>Open to new roles, contracts, and conversations about cloud & network infrastructure.</p>
    <div class="contact-info">
      <span>📍</span> Manchester, UK &nbsp; | &nbsp; <span>✉</span> khiljiatique@gmail.com &nbsp; | &nbsp; <span>☎</span> 07828 198863
    </div>
    <div class="hero-actions" style="justify-content:center;">
      <a href="mailto:khiljiatique@gmail.com" class="btn btn-primary">Email me →</a>
      <a href="https://www.linkedin.com/in/YOUR-LINKEDIN" class="btn btn-ghost">LinkedIn</a>
      <a href="https://github.com/Atiq101" class="btn btn-ghost">GitHub</a>
    </div>
  </div>
</section>

<footer>
  © 2026 Muhammad Khilji — Built with care, deployed with confidence.
</footer>

</body>
</html>
