---
layout: default
title: "The Silent Browser Botnet: How 148 Fake npm Proxies Weaponized Student Curiosity"
date: 2026-07-14
description: "Analysis of a recent campaign where malicious npm packages disguised as student web proxies bypassed traditional supply chain scanners to turn browsers into a DDoS botnet, highlighting the critical shift toward client-side execution attacks."
---

<a href="/2026/07/14/npm-student-proxy-botnet-es/" class="lang-switch">🇪🇸 Leer en Español</a>

<div class="post-header">
    <span class="post-date">July 14, 2026</span>
    <h1>The Silent Browser Botnet: How 148 Fake npm Proxies Weaponized Student Curiosity</h1>
</div>

<div class="post-content" markdown="1">

<p>In May 2026, a sophisticated campaign deployed 148 npm packages disguised as student web proxies, successfully transforming the browsers of unsuspecting users into a distributed denial-of-service (DDoS) botnet. This incident highlights a dangerous evolution in supply chain attacks: the shift from compromising the build pipeline to weaponizing client-side execution.</p>

<h3>1. The "Innocent" Registry Abuse</h3>
<p>Traditional Software Composition Analysis (SCA) and Static Application Security Testing (SAST) tools are designed to catch malicious code at install time. This campaign completely bypassed those controls. The packages contained no lifecycle hooks or native build scripts. Instead, they acted merely as free hosting for a client-side web application, waiting silently until a user actively visited the proxy site to bypass school network filters.</p>

<h3>2. The Mutable Branch Vulnerability</h3>
<p>Once the proxy loaded in the browser, it executed a remote script loader that fetched JavaScript from a GitHub repository via a CDN. Critically, this request pointed to a mutable main branch without any Subresource Integrity (SRI) checks. This allowed the operators to silently swap the payload at will, executing code with the proxy site’s own origin privileges and full access to cookies and local storage.</p>

<h3>3. Control-Plane Exhaustion Over Volumetric Flooding</h3>
<p>While the botnet did launch crude HTTP floods, its more sophisticated module utilized the Wisp proxy protocol to open hundreds of WebSocket connections per browser. This was not a traditional volumetric attack; it was a control-plane attack designed to exhaust file descriptors and flood log storage on the target Wisp server, effectively crashing the infrastructure through legitimate-looking connection churn.</p>

<div class="highlight-box">
<strong>4. The Social Engineering of Rebellion:</strong> The true genius of this attack was its psychological vector. It did not target developers; it targeted teenagers. By offering a working tool to bypass restrictive school web filters, the attackers leveraged the natural desire for digital freedom and rebellion. The users willingly opened the trap, believing they were outsmarting the system, while unknowingly becoming the weapon.
</div>

<h3>5. Strategic Defenses for a Client-Side Threat</h3>
<p>Mitigating this class of attack requires moving beyond static code analysis. Organizations and educational institutions must implement strict Content Security Policies (CSP) to block unauthorized cross-origin script execution. Furthermore, enforcing Subresource Integrity (SRI) for all external scripts and deploying DNS-level blocking for known malicious monetization and script hosts are non-n negotiable baseline controls. For affected users, clearing browser cache, local storage, and unregistering lingering service workers is the only way to break the persistence mechanism.</p>

<p>As long as public package registries can be abused as free Content Delivery Networks for client-side applications, the attack surface will continue to expand far beyond the traditional build environment. Defenders must adapt their monitoring to detect anomalous runtime behavior, not just static code vulnerabilities.</p>

<div class="source-link">
<strong>Source:</strong><br>
<a href="https://thehackernews.com/2026/07/148-npm-packages-disguised-as-student.html" target="_blank">The Hacker News: 148 npm Packages Disguised as Student Proxies Turned Browsers Into a DDoS Botnet</a><br>
<a href="https://cybersopho.top" target="_blank">https://cybersopho.top</a>
</div>

</div>