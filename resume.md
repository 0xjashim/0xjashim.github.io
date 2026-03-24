---
layout: page
title: Resume
permalink: /resume/
---

<style>
  .cv { font-family: 'Courier New', monospace; max-width: 860px; margin: 0 auto; }

  .cv-header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 2rem;
    border: 1px solid #00ff4133;
    border-radius: 8px;
    padding: 1.5rem;
    background: #050f05;
    margin-bottom: 1.5rem;
    flex-wrap: wrap;
  }
  .cv-name {
    font-size: 1.6rem;
    font-weight: 700;
    color: #00ff41;
    margin-bottom: 0.3rem;
    letter-spacing: 1px;
  }
  .cv-title {
    font-size: 13px;
    color: #4a7a4a;
    margin-bottom: 1rem;
  }
  .cv-contact { font-size: 12px; color: #4a7a4a; line-height: 2; }
  .cv-contact span { color: #00ff41; margin-right: 6px; }
  .cv-contact a { color: #00ff41; text-decoration: none; }
  .cv-contact a:hover { text-decoration: underline; }

  .cv-section {
    margin-bottom: 1.5rem;
    border: 1px solid #00ff4122;
    border-radius: 6px;
    overflow: hidden;
  }
  .cv-section-title {
    background: #0a1a0a;
    border-bottom: 1px solid #00ff4133;
    padding: 8px 14px;
    font-size: 11px;
    color: #00ff41;
    letter-spacing: 3px;
    text-transform: uppercase;
    font-weight: 700;
  }
  .cv-section-title::before { content: "// "; color: #4a7a4a; }
  .cv-section-body { padding: 1.2rem 1.4rem; background: #050f05; font-size: 13px; color: #c9d1d9; line-height: 1.8; }

  .cv-job { margin-bottom: 1.4rem; padding-bottom: 1.4rem; border-bottom: 1px solid #00ff4111; }
  .cv-job:last-child { margin-bottom: 0; padding-bottom: 0; border-bottom: none; }
  .cv-job-title { color: #00ff41; font-weight: 700; font-size: 14px; }
  .cv-job-meta { color: #4a7a4a; font-size: 12px; margin: 2px 0 6px; }
  .cv-job-company { color: #c9d1d9; font-size: 13px; font-weight: 600; }
  .cv-job-area { color: #4a7a4a; font-size: 12px; margin-bottom: 6px; }
  .cv-job ul { margin: 6px 0 0 0; padding: 0; list-style: none; }
  .cv-job ul li { padding-left: 16px; position: relative; margin-bottom: 3px; font-size: 12px; color: #aaa; }
  .cv-job ul li::before { content: "▸"; color: #00ff41; position: absolute; left: 0; }

  .cv-table { width: 100%; border-collapse: collapse; font-size: 12px; }
  .cv-table th { background: #0a1a0a; color: #00ff41; padding: 8px 10px; text-align: left; font-size: 11px; letter-spacing: 1px; border: 1px solid #00ff4122; }
  .cv-table td { padding: 8px 10px; border: 1px solid #00ff4111; color: #aaa; vertical-align: top; }
  .cv-table tr:nth-child(even) td { background: #0a1a0a; }

  .cv-cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 8px; }
  .cv-cert {
    background: #0a1a0a;
    border: 1px solid #00ff4122;
    border-radius: 4px;
    padding: 8px 12px;
    font-size: 12px;
  }
  .cv-cert-name { color: #00ff41; font-size: 12px; margin-bottom: 2px; }
  .cv-cert-meta { color: #4a7a4a; font-size: 11px; }

  .cv-skills { display: flex; flex-wrap: wrap; gap: 8px; }
  .cv-skill-tag {
    background: #0a1a0a;
    border: 1px solid #00ff4133;
    color: #00ff41;
    padding: 4px 12px;
    border-radius: 3px;
    font-size: 12px;
    letter-spacing: 0.5px;
  }

  .cv-award { margin-bottom: 10px; }
  .cv-award-title { color: #00ff41; font-size: 13px; font-weight: 700; }
  .cv-award-desc { color: #aaa; font-size: 12px; margin-top: 3px; }

  .cv-two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  @media (max-width: 600px) { .cv-two-col { grid-template-columns: 1fr; } .cv-header { flex-direction: column; } }

  .download-btn {
    display: inline-block;
    background: #00ff41;
    color: #000 !important;
    font-family: 'Courier New', monospace;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 1px;
    padding: 0.6rem 1.6rem;
    border-radius: 4px;
    text-decoration: none !important;
    float: right;
    transition: opacity 0.15s;
  }
  .download-btn:hover { opacity: 0.85; }
</style>

<div class="cv">

<!-- HEADER -->
<div class="cv-header">
  <div>
    <div class="cv-name">Jashim Uddin Bhuiyan</div>
    <div class="cv-title">Senior Officer — Cybersecurity | SOC | Penetration Testing | Pubali Bank Ltd.</div>
    <div class="cv-contact">
      <span>📍</span> 26 Dilkusha C/A, Pubali Bank Ltd. HO, Security Operation Center, Dhaka 1223<br>
      <span>📞</span> 01920561166, 01710433584<br>
      <span>✉</span> <a href="mailto:jashimcmt@gmail.com">jashimcmt@gmail.com</a> · <a href="mailto:jashim_cse@live.com">jashim_cse@live.com</a><br>
      <span>🔗</span>
        <a href="https://github.com/0xjashim" target="_blank">GitHub</a> ·
        <a href="https://www.linkedin.com/in/jashim/" target="_blank">LinkedIn</a> ·
        <a href="https://twitter.com/0xJ4shim" target="_blank">Twitter</a> ·
        <a href="https://app.hackthebox.com/profile/5674" target="_blank">HackTheBox</a>
    </div>
  </div>
</div>

<!-- CAREER OBJECTIVE -->
<div class="cv-section">
  <div class="cv-section-title">Career Objective</div>
  <div class="cv-section-body">
    Cybersecurity professional with 14 years in banking IT and 8 years in cybersecurity seeking a SOC Manager role. Experienced in leading SOC operations, SIEM monitoring, threat detection, incident response, vulnerability management, and PCI DSS &amp; ISO compliance.
  </div>
</div>

<!-- SKILLS -->
<div class="cv-section">
  <div class="cv-section-title">Skills</div>
  <div class="cv-section-body">
    <div class="cv-skills">
      <span class="cv-skill-tag">Penetration Testing</span>
      <span class="cv-skill-tag">Cyber Security</span>
      <span class="cv-skill-tag">Information Security</span>
      <span class="cv-skill-tag">Security Operations</span>
      <span class="cv-skill-tag">SIEM / QRadar</span>
      <span class="cv-skill-tag">SOAR</span>
      <span class="cv-skill-tag">EDR / PAM</span>
      <span class="cv-skill-tag">Incident Response</span>
      <span class="cv-skill-tag">Vulnerability Assessment</span>
      <span class="cv-skill-tag">Red Teaming</span>
      <span class="cv-skill-tag">PCI DSS v4</span>
      <span class="cv-skill-tag">ISO 27001</span>
      <span class="cv-skill-tag">Malware Analysis</span>
      <span class="cv-skill-tag">Bug Bounty</span>
    </div>
  </div>
</div>

<!-- EXPERIENCE -->
<div class="cv-section">
  <div class="cv-section-title">Experience — 15.2 years total</div>
  <div class="cv-section-body">

    <div class="cv-job">
      <div class="cv-job-title">Senior Officer <span style="color:#4a7a4a;font-weight:normal;font-size:12px;">(4.7 yrs)</span></div>
      <div class="cv-job-meta">01 Jul, 2021 – Continuing</div>
      <div class="cv-job-company">Pubali Bank Ltd.</div>
      <div class="cv-job-area">Cyber Security · Penetration Testing · Security Operations Center</div>
      <ul>
        <li>Lead SOC operations — managing teams, monitoring, and incident response to proactively detect and mitigate cyber threats</li>
        <li>Perform Vulnerability Assessment and Penetration Testing for infrastructure and applications</li>
        <li>Hunt for vulnerabilities in web apps, mobile apps, APIs, and network infrastructure</li>
        <li>Implement security controls, risk assessment frameworks aligned with regulatory requirements</li>
        <li>Create use cases, rules, and RegEx to enhance detection capabilities in SIEM</li>
        <li>Conduct malware analysis and stay updated on emerging malware threats</li>
        <li>Work on SIEM-SOAR, PAM, PCI DSS, and ISO 27001 implementation</li>
        <li>Participate in BD-CIRT Cyber Drills and FINDrill exercises</li>
      </ul>
    </div>

    <div class="cv-job">
      <div class="cv-job-title">Officer — Computer Engineer <span style="color:#4a7a4a;font-weight:normal;font-size:12px;">(4.5 yrs)</span></div>
      <div class="cv-job-meta">01 Jan, 2017 – 30 Jun, 2021</div>
      <div class="cv-job-company">Pubali Bank Limited, Motijheel</div>
      <div class="cv-job-area">Cyber Security · Information Security</div>
      <ul>
        <li>Define, implement, and maintain corporate security policies, providing end-user training</li>
        <li>Conduct security analysis and reporting of ICT infrastructure events</li>
        <li>Monitor internal control systems to maintain appropriate information access levels</li>
        <li>Oversee and audit firewalls, IPS/IDS, ESA, WSA, TG, FMC, and other security devices</li>
        <li>Perform VAPT using Qualys and open-source tools</li>
      </ul>
    </div>

    <div class="cv-job">
      <div class="cv-job-title">Computer Engineer — Junior Officer <span style="color:#4a7a4a;font-weight:normal;font-size:12px;">(5.3 yrs)</span></div>
      <div class="cv-job-meta">17 Sep, 2011 – 31 Dec, 2016</div>
      <div class="cv-job-company">Pubali Bank Ltd., Head Office ITD, Dhaka</div>
      <div class="cv-job-area">Software Implementation</div>
      <ul>
        <li>Design, develop, and test BACPS, BEFTN, and RTGS application software</li>
        <li>Install, configure, and maintain PBM servers including HSM and clearing house certificates</li>
        <li>Reconcile daily BACPS/BEFTN/RTGS settlements with Bangladesh Bank</li>
      </ul>
    </div>

    <div class="cv-job">
      <div class="cv-job-title">IT Officer <span style="color:#4a7a4a;font-weight:normal;font-size:12px;">(0.5 yrs)</span></div>
      <div class="cv-job-meta">23 Mar, 2011 – 14 Sep, 2011</div>
      <div class="cv-job-company">Prochito Integrated Marketing and Communication Ltd, Dhaka</div>
      <div class="cv-job-area">IT System Management</div>
      <ul>
        <li>Maintain attendance software, configure routers and switches, administer DNS servers</li>
        <li>Establish and maintain LAN for internal offices</li>
      </ul>
    </div>

  </div>
</div>

<!-- EDUCATION -->
<div class="cv-section">
  <div class="cv-section-title">Academic / Education</div>
  <div class="cv-section-body" style="padding:0;">
    <table class="cv-table">
      <thead>
        <tr><th>Degree</th><th>Major</th><th>Institute</th><th>Result</th><th>Year</th></tr>
      </thead>
      <tbody>
        <tr><td>MSc. Computer Science</td><td>Computer Science</td><td>Jahangirnagar University</td><td>3.28/4</td><td>2016</td></tr>
        <tr><td>BSc. CS &amp; Engineering</td><td>CS &amp; Engineering</td><td>Northern University Bangladesh</td><td>2.85/4</td><td>2013</td></tr>
        <tr><td>Diploma in Computer</td><td>Software &amp; Network</td><td>Institute of Computer &amp; Technology, Feni</td><td>3.47/4</td><td>2008</td></tr>
        <tr><td>SSC</td><td>Science</td><td>Ali Azam High School and College, Feni</td><td>3/5</td><td>2003</td></tr>
      </tbody>
    </table>
  </div>
</div>

<!-- CERTIFICATIONS -->
<div class="cv-section">
  <div class="cv-section-title">Professional Qualifications &amp; Certifications</div>
  <div class="cv-section-body">
    <div class="cv-cert-grid">
      <div class="cv-cert"><div class="cv-cert-name">Junior Penetration Tester (eJPTv2)</div><div class="cv-cert-meta">INE Security · 2025–2029</div></div>
      <div class="cv-cert"><div class="cv-cert-name">APISec Certified Practitioner (ACP)</div><div class="cv-cert-meta">APISec University · 2025–2028</div></div>
      <div class="cv-cert"><div class="cv-cert-name">eWPTXv2 — Web App Pentest Extreme</div><div class="cv-cert-meta">INE Security · 2025–2028</div></div>
      <div class="cv-cert"><div class="cv-cert-name">ACMP 4.0 — Advanced Cert for Management</div><div class="cv-cert-meta">IBA, University of Dhaka · 2025</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Certified in Cybersecurity (CC)</div><div class="cv-cert-meta">ISC2 · 2022–2025</div></div>
      <div class="cv-cert"><div class="cv-cert-name">ISO/IEC 27001 Lead Auditor</div><div class="cv-cert-meta">CQI IRCA · 2022</div></div>
      <div class="cv-cert"><div class="cv-cert-name">ISO/IEC 27001 Lead Implementer</div><div class="cv-cert-meta">Intertek · 2022</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Certified Ethical Hacker — Master (CEH-M)</div><div class="cv-cert-meta">EC-Council · 2021–2024</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Certified Ethical Hacker Practical (CEH-P)</div><div class="cv-cert-meta">EC-Council · 2021–2024</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Certified SOC Analyst v1 (CSA)</div><div class="cv-cert-meta">EC-Council · 2021–2024</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Cisco Certified Specialist — Enterprise Core</div><div class="cv-cert-meta">CISCO · 2020–2023</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Oracle Cloud Infrastructure 2019 — Architect Pro</div><div class="cv-cert-meta">Oracle University · 2020</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Certified Ethical Hacker (CEH)</div><div class="cv-cert-meta">EC-Council · 2018–2021</div></div>
      <div class="cv-cert"><div class="cv-cert-name">Oracle Certified Database Administrator</div><div class="cv-cert-meta">Oracle University · 2014</div></div>
    </div>
  </div>
</div>

<!-- TRAINING -->
<div class="cv-section">
  <div class="cv-section-title">Training</div>
  <div class="cv-section-body" style="padding:0;">
    <table class="cv-table">
      <thead>
        <tr><th>Training</th><th>Institute</th><th>Year</th><th>Duration</th></tr>
      </thead>
      <tbody>
        <tr><td>EC-Council Certified Incident Handler v3</td><td>IT Expert BD</td><td>2026</td><td>5 Days</td></tr>
        <tr><td>Performing Cybersecurity Using Cisco (CBRCOR)</td><td>CISCO</td><td>2025</td><td>5 Days</td></tr>
        <tr><td>Appdome Mobile App Security (BOT Defense)</td><td>Appdome</td><td>2025</td><td>2 Days</td></tr>
        <tr><td>Senhesagure PAM Administration</td><td>OneWorld InfoTech</td><td>2024</td><td>3 Days</td></tr>
        <tr><td>PCI DSS Targeted Risk Analysis (TRA)</td><td>ControlCase</td><td>2024</td><td>2 Days</td></tr>
        <tr><td>Fortify Scan Central SAST &amp; DAST</td><td>Trustaira Limited</td><td>2024</td><td>3 Days</td></tr>
        <tr><td>Malware Analysis &amp; Ransomware Investigation</td><td>Cyberfoxtrain</td><td>2024</td><td>5 Days</td></tr>
        <tr><td>PCI DSS V4.0 Implementer Training</td><td>ControlCase LLC</td><td>2024</td><td>2 Days</td></tr>
        <tr><td>Cyber Security Management &amp; SOC in Banks</td><td>BIBM</td><td>2024</td><td>2 Days</td></tr>
        <tr><td>Cyber Security and Fraud Prevention in Banks</td><td>BIBM</td><td>2023</td><td>5 Days</td></tr>
        <tr><td>PCI DSS V3.2.1 Implementer Training</td><td>ControlCase LLC</td><td>2022</td><td>2 Days</td></tr>
        <tr><td>Certified Ethical Hacking</td><td>IBCS-PRIMAX Software</td><td>2017</td><td>40 hrs</td></tr>
        <tr><td>ASP.NET MVC4 and WEB API</td><td>Pubali Bank Training Institute</td><td>2014</td><td>100 hrs</td></tr>
        <tr><td>Oracle Database 10g Administration II</td><td>IBCS-PRIMAX SOFTWARE</td><td>2014</td><td>120 hrs</td></tr>
        <tr><td>Object Oriented Programming in C#ASP.Net</td><td>BASIS</td><td>2013</td><td>150 hrs</td></tr>
      </tbody>
    </table>
  </div>
</div>

<!-- AWARDS -->
<div class="cv-section">
  <div class="cv-section-title">Accomplishments &amp; Awards</div>
  <div class="cv-section-body">
    <div class="cv-award">
      <div class="cv-award-title">🏆 Oracle Hall of Fame</div>
      <div class="cv-award-desc">Recognized by Oracle for contributions to their Online Presence Security program by responsibly reporting security issues that led to significant improvements in Oracle's external-facing systems. <a href="https://www.oracle.com/security-alerts/cpuapr2025.html" target="_blank" style="color:#00ff41;">oracle.com/security-alerts</a></div>
    </div>
    <div class="cv-award">
      <div class="cv-award-title">🏆 NASA Hall of Fame</div>
      <div class="cv-award-desc">Received a Letter of Appreciation for identifying critical bugs and contributing to application security improvements.</div>
    </div>
  </div>
</div>

<!-- LANGUAGES -->
<div class="cv-section">
  <div class="cv-section-title">Language Proficiency</div>
  <div class="cv-section-body" style="padding:0;">
    <table class="cv-table">
      <thead><tr><th>Language</th><th>Reading</th><th>Writing</th><th>Speaking</th></tr></thead>
      <tbody>
        <tr><td>Bangali</td><td>High</td><td>High</td><td>High</td></tr>
        <tr><td>English</td><td>High</td><td>Medium</td><td>Medium</td></tr>
        <tr><td>French</td><td>Medium</td><td>Low</td><td>Low</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

---
*Last updated: March 2026*
