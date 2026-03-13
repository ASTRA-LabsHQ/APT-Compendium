# ASTRA Threat Compendium

[![Hits](https://hits.sh/github.com/ASTRA-LabsHQ/APT-Compendium.svg?style=plastic&label=Views&color=2C2E47)](https://hits.sh/github.com/ASTRA-LabsHQ/APT-Compendium/)

Welcome to the **ASTRA Threat Compendium** — an open-source repository documenting the world's most notorious Advanced Persistent Threat (APT) groups, their malware arsenals, and the campaigns they conduct. This compendium is intended as a living reference for malware analysts, threat intelligence practitioners, and defenders.

> **Disclaimer:** Attribution in threat intelligence is inherently probabilistic. Alias mappings, sponsoring entities, and campaign attributions reflect the current consensus of the open-source threat intelligence community and may be contested or revised as new reporting emerges. Always cross-reference with primary sources.

---

## Table of Contents

1. [How to Read This Compendium](#how-to-read-this-compendium)
2. [Quick Reference: Alias Mapping](#quick-reference-alias-mapping)
3. [Russia-Nexus Groups](#russia-nexus-groups)
   - [APT28 — Fancy Bear](#apt28--fancy-bear)
   - [APT29 — Cozy Bear](#apt29--cozy-bear)
   - [Sandworm — Voodoo Bear](#sandworm--voodoo-bear)
   - [Turla — Snake](#turla--snake)
4. [China-Nexus Groups](#china-nexus-groups)
   - [APT41 — Double Dragon](#apt41--double-dragon)
   - [Volt Typhoon](#volt-typhoon)
   - [Salt Typhoon](#salt-typhoon)
   - [APT10 — Stone Panda](#apt10--stone-panda)
   - [Mustang Panda — TA416](#mustang-panda--ta416)
5. [North Korea-Nexus Groups](#north-korea-nexus-groups)
   - [Lazarus Group — Hidden Cobra](#lazarus-group--hidden-cobra)
   - [APT38 — Bluenoroff](#apt38--bluenoroff)
   - [Kimsuky — Thallium](#kimsuky--thallium)
   - [Andariel — Silent Chollima](#andariel--silent-chollima)
6. [Iran-Nexus Groups](#iran-nexus-groups)
   - [APT33 — Elfin](#apt33--elfin)
   - [APT34 — OilRig](#apt34--oilrig)
   - [APT35 — Charming Kitten](#apt35--charming-kitten)
   - [MuddyWater — Static Kitten](#muddywater--static-kitten)
7. [Notable Campaigns Index](#notable-campaigns-index)
8. [Tracking & Reference Resources](#tracking--reference-resources)
9. [Contributing](#contributing)

---

## How to Read This Compendium

Each group entry follows this structure:

| Field | Description |
|---|---|
| **Also Known As** | All known aliases across major vendors (Mandiant, CrowdStrike, Microsoft, ESET, etc.) |
| **Attributed To** | Sponsoring government / intelligence service |
| **Active Since** | Earliest confirmed activity |
| **Primary Motivation** | Espionage / Financial / Destructive / All three |
| **Target Sectors** | Industries and verticals this group prioritizes |
| **Target Regions** | Geographic focus |
| **Malware Arsenal** | Key malware families attributed to this group |
| **Signature TTPs** | Common tactics, techniques, and procedures |
| **MITRE ATT&CK** | Link to MITRE group profile |
| **Notable Campaigns** | Landmark intrusions attributed to the group |
| **Key Reports** | Essential reading for deeper understanding |

---

## Quick Reference: Alias Mapping

Vendor naming conventions vary significantly. This table maps common aliases to a canonical group name.

| Canonical Name | Mandiant | CrowdStrike | Microsoft | ESET | Kaspersky |
|---|---|---|---|---|---|
| APT28 | APT28 | Fancy Bear | Forest Blizzard / STRONTIUM | Sednit | — |
| APT29 | APT29 | Cozy Bear | Midnight Blizzard / NOBELIUM | — | The Dukes |
| Sandworm | Sandworm | Voodoo Bear | Seashell Blizzard | — | Black Energy |
| Turla | — | Venomous Bear | Secret Blizzard | — | Snake |
| APT41 | APT41 | Wicked Panda / Brass Typhoon | BARIUM | Winnti Group | — |
| Volt Typhoon | — | Vanguard Panda | Volt Typhoon | — | — |
| Salt Typhoon | UNC2286 | — | Salt Typhoon | FamousSparrow | GhostEmperor |
| APT10 | APT10 | Stone Panda | Citrине Typhoon | — | — |
| Mustang Panda | — | Panda — | — | — | — |
| Lazarus Group | — | Labyrinth Chollima | Diamond Sleet / ZINC | — | — |
| APT38 | APT38 | Stardust Chollima | — | — | — |
| Kimsuky | APT43 | Sparkling Pisces | Emerald Sleet / THALLIUM | — | — |
| Andariel | — | Jumping Spider | Onyx Sleet | — | — |
| APT33 | APT33 | Refined Kitten | Peach Sandstorm | — | — |
| APT34 / OilRig | APT34 | Helix Kitten | Hazel Sandstorm | — | — |
| APT35 | APT35 | Charming Kitten | Mint Sandstorm | — | — |
| MuddyWater | — | Static Kitten | Mango Sandstorm | — | Seedworm |

---

## Russia-Nexus Groups

Russia's cyber operations are primarily executed through two intelligence services: the **GRU** (military intelligence) and the **SVR** (foreign intelligence). GRU-linked groups (APT28, Sandworm) tend toward aggressive, disruptive, and influence operations. SVR-linked groups (APT29) operate with greater patience and stealth, prioritizing long-term espionage.

---

### APT28 — Fancy Bear

| Field | Detail |
|---|---|
| **Also Known As** | Fancy Bear, Sednit, Sofacy, Pawn Storm, STRONTIUM, Forest Blizzard, FROZENLAKE, GruesomeLarch, Tsar Team, Group 74, Iron Twilight, TA422 |
| **Attributed To** | Russian GRU, Unit 26165 (with operational support from Unit 74455 / Sandworm) |
| **Active Since** | ~2007 |
| **Primary Motivation** | Espionage, political interference, influence operations |
| **Target Sectors** | Government, defense, military, political parties, media, anti-doping agencies, think tanks |
| **Target Regions** | NATO member states, Ukraine, United States, Western Europe |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| X-Agent (Sofacy) | Backdoor / keylogger | Core cross-platform implant; Windows, Linux, iOS, Android variants |
| X-Tunnel | Network tunneling | Encrypted communication tool |
| Komplex | macOS backdoor | Targets macOS environments |
| Zebrocy | Dropper / downloader | Multi-stage loader written in Go, Delphi, AutoIT |
| LoJax | UEFI rootkit | First UEFI rootkit observed in the wild (2018); highly persistent |
| CHOPSTICK | Modular backdoor | Also known as SPLM/EVILTOSS |
| SOURFACE / Downdelph | Downloader | First-stage payload |

**Signature TTPs**
- Spearphishing with malicious Office documents (T1566.001), often themed around geopolitical events
- Exploitation of webmail vulnerabilities (XSS in Roundcube, Zimbra, Horde) for initial access (T1190)
- Password spraying and brute force against public-facing services (T1110)
- Credential harvesting via spoofed login pages
- DLL sideloading and rundll32.exe abuse for execution (T1218.011)
- PowerShell for post-exploitation (T1059.001)
- Network device exploitation (Cisco router CVE-2017-6742)

**MITRE ATT&CK:** [G0007](https://attack.mitre.org/groups/G0007/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2014–2016 | DNC / U.S. Election Interference | Compromised the Democratic National Committee, DCCC, and Hillary Clinton campaign; worked alongside APT29 |
| 2015 | German Bundestag | Infected parliamentary network, exfiltrated ~16GB of data |
| 2015–2016 | WADA / Anti-Doping | Targeted World Anti-Doping Agency and related sports organizations post-Russian doping scandal |
| 2017 | Emmanuel Macron Campaign | Attempted to disrupt the French presidential election with leaked documents |
| 2018 | LoJax Operation | Deployed the first-ever UEFI rootkit against a European government target |
| 2023–2024 | Webmail Exploitation Campaign | Systematic exploitation of XSS vulnerabilities in enterprise webmail platforms across Europe |

**Key Reports**
- [MITRE ATT&CK: APT28](https://attack.mitre.org/groups/G0007/)
- [CISA Advisory AA23-108: APT28 Cisco Router Exploitation](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-108)
- [ESET: LoJax — First UEFI Rootkit in the Wild](https://www.welivesecurity.com/2018/09/27/lojax-first-uefi-rootkit-found-wild-courtesy-sednit-group/)

---

### APT29 — Cozy Bear

| Field | Detail |
|---|---|
| **Also Known As** | Cozy Bear, The Dukes, CozyDuke, NOBELIUM, UNC2452, SolarStorm, Midnight Blizzard, Dark Halo, Iron Ritual, Blue Kitsune |
| **Attributed To** | Russian SVR (Foreign Intelligence Service) |
| **Active Since** | ~2008 |
| **Primary Motivation** | Long-term intelligence collection; strategic espionage |
| **Target Sectors** | Government, diplomatic missions, think tanks, NGOs, technology firms, pharmaceutical/vaccine research |
| **Target Regions** | NATO member states, United States, Europe, diplomatic targets globally |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| SUNBURST | Supply chain backdoor | Embedded in SolarWinds Orion updates; the defining tool of the 2020 campaign |
| SUNSHUTTLE (GoldMax) | C2 backdoor | Second-stage Go-based backdoor used in SolarWinds follow-on operations |
| BOOMBOX | Downloader | Used alongside SUNSHUTTLE |
| WINELOADER | Phishing payload / loader | Observed in 2024 diplomatic phishing operations; uses DLL search-order hijacking |
| ROOTSAW (EnvyScout) | First-stage dropper | Malicious HTML dropper used to profile victims and deliver payloads |
| NativeZone | Loader | CobaltStrike loader observed in 2021 USAID phishing campaign |
| WellMess / WellMail | Backdoor | Used against COVID-19 vaccine research targets (2020) |
| MiniDuke | Backdoor | Early-era implant using Twitter and PDF for C2 |
| CosmicDuke | Infostealer | Used against diplomatic targets |
| GraphDrop / SPICYBEAT | Loader | Uses Microsoft OneDrive for C2 |
| SNOWYAMBER | Backdoor | Uses Notion databases for C2 |

**Signature TTPs**
- Surgical spearphishing campaigns targeting specific individuals with highly customized lures (T1566)
- Extensive use of cloud services (OneDrive, Dropbox, Notion, Trello, Slack) as C2 channels to blend with legitimate traffic (T1102)
- Supply chain compromise — infecting trusted software update mechanisms rather than targeting victims directly (T1195.002)
- DLL search-order hijacking for execution (T1574.001)
- Long dwell time; extremely patient; operates with minimal footprint on victim networks
- Switches between "smash-and-grab" and "slow-and-deliberate" postures depending on target value

**MITRE ATT&CK:** [G0016](https://attack.mitre.org/groups/G0016/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2015 | DNC Breach | APT29 gained initial access a full year before APT28, maintaining quiet access for months |
| 2015 | Pentagon Email System | Caused the shutdown of the Joint Staff unclassified email system |
| 2020 | SolarWinds Supply Chain | SUNBURST backdoor embedded in Orion updates; infected ~18,000 organizations including CISA, Treasury, State Department |
| 2021 | USAID Phishing Campaign | Compromised a USAID email marketing account to launch highly targeted phishing against NGOs, think tanks, and government agencies |
| 2023–2024 | Microsoft & Tech Sector Intrusions | Compromised Microsoft corporate email; accessed accounts of senior leadership and security teams |
| 2024 | AWS-Themed Phishing | Large-scale credential phishing campaign using AWS-themed lures against European government entities |

**Key Reports**
- [MITRE ATT&CK: APT29](https://attack.mitre.org/groups/G0016/)
- [Mandiant: UNC2452 / SolarWinds Compromise](https://www.mandiant.com/resources/blog/unc2452-merged-into-apt29)
- [CISA: Enhanced Analysis of GRIZZLY STEPPE Activity](https://www.cisa.gov/sites/default/files/publications/AR-17-20045_Enhanced_Analysis_of_GRIZZLY_STEPPE_Activity.pdf)
- [F-Secure: The Dukes — 7 Years of Russian Cyber Espionage](https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf)

---

### Sandworm — Voodoo Bear

| Field | Detail |
|---|---|
| **Also Known As** | Sandworm, Voodoo Bear, Black Energy, ELECTRUM, Seashell Blizzard, TeleBots, IRIDIUM, UAC-0133 |
| **Attributed To** | Russian GRU, Unit 74455 (Main Center for Special Technologies) |
| **Active Since** | ~2009 |
| **Primary Motivation** | Sabotage, disruption of critical infrastructure, destructive operations in support of geopolitical objectives |
| **Target Sectors** | Energy / power grid, industrial control systems (ICS/SCADA), government, media, finance |
| **Target Regions** | Ukraine (primary), NATO member states, United States |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| BlackEnergy | Modular backdoor | Used in early power grid attacks; evolved over multiple versions |
| Industroyer / Crashoverride | ICS-specific destructive malware | Designed to directly interact with and disrupt power grid protocols; caused 2016 Ukraine blackout |
| Industroyer2 | ICS-specific destructive malware | Updated version deployed against Ukrainian power infrastructure in 2022 |
| KillDisk | Disk wiper | Destructive payload deployed alongside BlackEnergy |
| NotPetya | Wiper (disguised as ransomware) | Spread via M.E.Doc accounting software update; caused ~$10B in global damage; most destructive cyber weapon deployed to date |
| Olympic Destroyer | Wiper | Used to disrupt the 2018 Pyeongchang Winter Olympics opening ceremony |
| Cyclops Blink | Router botnet | Replaced VPNFilter; targeted Asus and WatchGuard devices |
| VPNFilter | Router botnet | Compromised ~500,000 SOHO routers globally |

**Signature TTPs**
- Compromise of ICS/SCADA environments via IT-to-OT lateral movement
- Supply chain compromise (M.E.Doc accounting software for NotPetya deployment)
- Spearphishing with ICS-themed lures targeting energy sector employees
- Living-off-the-land techniques alongside purpose-built destructive payloads
- Deployment of wipers designed to be non-recoverable and maximally disruptive

**MITRE ATT&CK:** [G0034](https://attack.mitre.org/groups/G0034/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2015–2016 | Ukraine Power Grid Attacks | First confirmed destructive cyberattacks against power infrastructure; caused widespread blackouts across Ukraine |
| 2017 | NotPetya | Disguised as ransomware; caused estimated $10B+ in global damage; devastated Maersk, Merck, FedEx, and dozens of other multinationals |
| 2018 | Olympic Destroyer | Disrupted IT systems at the Pyeongchang Winter Olympics; deployed false flags implicating other nation-states |
| 2022 | Industroyer2 | Attempted to destroy Ukrainian power infrastructure alongside the Sandworm-linked CaddyWiper destructive malware campaign |
| 2024 | European Critical Infrastructure Sabotage | U.S., UK, and allies jointly accused Sandworm of targeting critical infrastructure across NATO member states |

**Key Reports**
- [MITRE ATT&CK: Sandworm](https://attack.mitre.org/groups/G0034/)
- [Mandiant: Sandworm Team](https://www.mandiant.com/resources/blog/ukraine-and-sandworm-team)
- [ESET: Industroyer — Biggest Threat to Industrial Control Systems](https://www.welivesecurity.com/2017/06/12/industroyer-biggest-threat-industrial-control-systems-since-stuxnet/)
- [WIRED: The Untold Story of NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/)

---

### Turla — Snake

| Field | Detail |
|---|---|
| **Also Known As** | Turla, Snake, Venomous Bear, Secret Blizzard, KRYPTON, Waterbug, Iron Hunter, WhiteBear, Uroburos |
| **Attributed To** | Russian FSB (Federal Security Service) |
| **Active Since** | ~1996 (one of the longest-operating APT groups in existence) |
| **Primary Motivation** | Strategic intelligence collection; long-term access to high-value targets |
| **Target Sectors** | Government, defense, diplomatic missions, military, education, research |
| **Target Regions** | NATO member states, Middle East, Central Asia; global diplomatic targets |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| Uroburos / Snake | Kernel-level rootkit | Sophisticated peer-to-peer encrypted C2 network; designed for stealth and persistence in air-gapped environments |
| Carbon | Modular backdoor | Used for long-term access and lateral movement |
| KAZUAR | .NET backdoor | Multi-platform; supports Windows, macOS, Linux |
| ComRAT v4 | RAT | One of Turla's most advanced tools; uses Gmail web interface for C2 |
| HyperStack | Lateral movement | Used for C2 via IPC pipes within compromised networks |
| TinyTurla | Backdoor | Lightweight second-stage implant deployed after other tools are detected |
| Capibar / DeliveryCheck | Backdoor | Recently observed in operations against Ukraine |

**Signature TTPs**
- Hijacking of other threat actors' C2 infrastructure (notably hijacked Iranian APT34 infrastructure)
- Use of satellite internet links as C2 channels to obfuscate infrastructure
- Watering hole attacks against embassy and government websites
- Extremely sophisticated long-term presence; documented dwell times of years
- Peer-to-peer encrypted C2 that does not require direct internet connectivity on all compromised hosts

**MITRE ATT&CK:** [G0010](https://attack.mitre.org/groups/G0010/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2008 | Agent.btz | Infected U.S. military networks via infected USB drives left in parking lots near military bases |
| 2014–2018 | Moonlight Maze (alleged successor) | Long-running espionage campaign targeting U.S. government and research institutions |
| 2019–2020 | OilRig Infrastructure Hijack | Accessed and weaponized APT34's (OilRig) own attack infrastructure against their targets |
| 2020 | ComRAT v4 Campaign | Deployed Gmail-based C2 backdoor against European government foreign affairs ministries |
| 2022–2024 | Ukraine-Focused Operations | Ongoing campaigns deploying TinyTurla and DeliveryCheck against Ukrainian government and defense targets |

**Key Reports**
- [MITRE ATT&CK: Turla](https://attack.mitre.org/groups/G0010/)
- [ESET: Uroburos / Snake Rootkit Analysis](https://www.welivesecurity.com/)
- [Kaspersky: The Epic Turla Operation](https://securelist.com/the-epic-turla-operation/65545/)
- [CISA: Infamous Chisel — Turla Mobile Malware](https://www.cisa.gov/resources-tools/resources/infamous-chisel-malware-analysis-report)

---

## China-Nexus Groups

China's cyber operations are primarily driven by strategic intelligence collection aligned with national economic and military interests, including the "Made in China 2025" technology initiative, Belt and Road investments, and pre-positioning in critical infrastructure for potential future conflict scenarios. Chinese APT groups are notable for tool-sharing across clusters, making attribution challenging.

---

### APT41 — Double Dragon

| Field | Detail |
|---|---|
| **Also Known As** | Double Dragon, Wicked Panda, Brass Typhoon, BARIUM, Winnti Group, Earth Baku, HOODOO |
| **Attributed To** | Chinese MSS (Ministry of State Security); unique among Chinese APTs for parallel government and financially motivated operations |
| **Active Since** | ~2012 |
| **Primary Motivation** | Espionage AND financial gain (unique dual-mission mandate) |
| **Target Sectors** | Healthcare, telecom, technology, finance, video gaming, education, government; also software supply chains |
| **Target Regions** | Global (14+ countries confirmed); United States, Taiwan, Southeast Asia primary |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| HIGHNOON | Backdoor | Core implant used across espionage operations |
| POISONPLUG / CROSSWALK | Backdoor | Used in supply chain operations |
| Derusbi | DLL backdoor | Shared across multiple Chinese APT clusters |
| ShadowPad | Modular backdoor | Widely shared across Chinese state-sponsored groups; successor to PlugX in many campaigns |
| PlugX / Korplug | RAT | Commodity-grade RAT widely shared across Chinese groups |
| DUSTTRAP | Loader | Used in recent operations; loads encrypted payloads |
| TOUGHPROGRESS | Backdoor | Observed in 2024–2025 operations |
| MESSAGETAP | Network interceptor | Deployed on telecom SMSC servers to intercept SMS messages |
| Winnti | Backdoor | Kernel-level rootkit originally used against gaming companies; source of the "Winnti umbrella" grouping |

**Signature TTPs**
- Supply chain compromise targeting software vendors to deliver malicious updates to downstream victims (T1195.002)
- Phantom DLL hijacking for stealthy execution (T1574)
- Cloud service C2 (Google Calendar, OneDrive) for covert communications (T1102)
- Dual operations: espionage tooling used in financially motivated campaigns and vice versa
- Environmental keying: payloads only execute on intended victim systems, complicating analysis

**MITRE ATT&CK:** [G0096](https://attack.mitre.org/groups/G0096/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2019–2020 | "This Is Not a Test" Global Campaign | Exploited multiple high-severity CVEs within hours of public disclosure across a global multi-industry target set |
| 2019 | CCleaner Supply Chain | Infected CCleaner software update with ShadowPad in a second-stage payload targeting technology companies |
| 2020–2021 | U.S. State Government Intrusions | Compromised at least six U.S. state government networks |
| 2021 | Air India Breach | Third-party supply chain attack affecting millions of airline passenger records |
| 2024 | Salt Typhoon Telecom Operations | Infiltrated nine major U.S. telecom providers including AT&T, Verizon, and T-Mobile; accessed lawful intercept systems |

**Key Reports**
- [MITRE ATT&CK: APT41](https://attack.mitre.org/groups/G0096/)
- [Mandiant: APT41 — A Dual Espionage and Cyber Crime Operation](https://cloud.google.com/blog/topics/threat-intelligence/apt41-dual-espionage-and-cyber-crime-operation)
- [DOJ Indictment (2020): Five Chinese APT41 Members](https://www.justice.gov/opa/pr/seven-international-cyber-defendants-including-apt41-actors-charged-connection-computer)

---

### Volt Typhoon

| Field | Detail |
|---|---|
| **Also Known As** | Vanguard Panda (CrowdStrike), BRONZE SILHOUETTE, DEV-0391, InsidousTaurus |
| **Attributed To** | Chinese PLA or MSS (People's Liberation Army / Ministry of State Security) |
| **Active Since** | ~2021 (confirmed; likely earlier) |
| **Primary Motivation** | Pre-positioning within critical infrastructure; intelligence collection; preparation for potential wartime disruption |
| **Target Sectors** | Communications, energy, transportation, water and wastewater, maritime, government |
| **Target Regions** | United States, Guam, and Indo-Pacific; NATO member critical infrastructure |

**Malware Arsenal / Tools**

Volt Typhoon is notable for relying almost entirely on **living-off-the-land (LOTL) techniques**, using native OS tools and legitimate software rather than custom malware to avoid detection.

| Tool | Type | Notes |
|---|---|---|
| PowerShell / cmd.exe | Native execution | Core execution environment; avoids writing to disk where possible |
| WMI | Native lateral movement | Used for lateral movement and remote code execution |
| Impacket | Open-source framework | Used for network reconnaissance and lateral movement |
| Earthworm / FRP | Network tunneling | Used to proxy C2 traffic and pivot through networks |
| Mimikatz | Credential dumping | Used for credential theft post-access |
| LOTL + KV-Botnet | Botnet of compromised SOHO routers | Routes C2 traffic through compromised home and small office routers to obscure origin |

**Signature TTPs**
- Exclusive reliance on living-off-the-land techniques; rarely deploys custom malware (T1218, T1059)
- Compromises SOHO routers, VPN appliances, and edge devices as C2 relay infrastructure
- Extremely long dwell time with minimal network noise
- Exfiltrates data using legitimate tools and services already present on victim networks
- Strong focus on Operational Technology (OT) environments and industrial control systems

**MITRE ATT&CK:** [Volt Typhoon](https://attack.mitre.org/groups/G1017/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2021–2023 | Guam / Pacific Critical Infrastructure | Embedded in U.S. military and critical infrastructure in Guam; assessed as pre-positioning ahead of potential Taiwan conflict |
| 2023 | CISA/NSA Joint Advisory | CISA and NSA issued joint advisory documenting Volt Typhoon's LOTL TTPs and critical infrastructure targeting |
| 2024 | KV-Botnet Discovery | Researchers uncovered a botnet of compromised SOHO routers used by Volt Typhoon to route and disguise its C2 traffic |

**Key Reports**
- [MITRE ATT&CK: Volt Typhoon](https://attack.mitre.org/groups/G1017/)
- [CISA: People's Republic of China State-Sponsored Cyber Actor Living Off the Land](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-144a)
- [Microsoft: Volt Typhoon Targets US Critical Infrastructure](https://www.microsoft.com/en-us/security/blog/2023/05/24/volt-typhoon-targets-us-critical-infrastructure-with-living-off-the-land-techniques/)

---

### Salt Typhoon

| Field | Detail |
|---|---|
| **Also Known As** | FamousSparrow (ESET), GhostEmperor (Kaspersky), UNC2286 (Mandiant), Earth Estries, Kelp |
| **Attributed To** | Chinese government (PRC); affiliated with MSS or PLA |
| **Active Since** | ~2020 |
| **Primary Motivation** | Strategic espionage; interception of communications including lawful intercept infrastructure |
| **Target Sectors** | Telecommunications, internet service providers (ISPs), government |
| **Target Regions** | United States, Europe, Indo-Pacific |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| SparrowDoor | Backdoor | Core implant; multiple updated variants observed |
| Demodex | Rootkit | Kernel-level rootkit; used for stealth and persistence on Exchange servers |
| GhostSpider | Backdoor | Newer implant observed in 2024–2025 campaigns |
| Deed RAT (Snappy Bee) | RAT | Shared tool used across multiple Chinese APT clusters |
| Motnug | Shellcode loader | Loads the CROSSWALK backdoor; links Salt Typhoon to broader Winnti/APT41 ecosystem |

**Signature TTPs**
- Exploitation of Microsoft Exchange Server vulnerabilities for initial access (ProxyLogon, ProxyShell)
- Exploitation of Cisco and Fortinet edge device vulnerabilities
- DLL sideloading using legitimate, signed binaries
- Targeting of lawful intercept (CALEA) infrastructure within telecom environments
- Extended dwell time; patient access maintenance before high-value exfiltration

**MITRE ATT&CK:** [Salt Typhoon / G1043](https://attack.mitre.org/groups/G1043/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2024 | U.S. Telecom Breach | Compromised nine major U.S. telecom providers (AT&T, Verizon, T-Mobile, and others); accessed lawful intercept platforms used by law enforcement and intelligence agencies |
| 2024 | Government Targeting | Intercepted communications involving senior U.S. government officials, including personnel associated with then-President-elect Trump's communications |

**Key Reports**
- [CISA: Enhanced Visibility and Hardening Guidance for Communications Infrastructure](https://www.cisa.gov/resources-tools/resources/enhanced-visibility-and-hardening-guidance-communications-infrastructure)
- [Hack The Box: Salt Typhoon Attack Anatomy](https://www.hackthebox.com/blog/salt-typhoon-apt-us-telecom-espionage-attack-analysis)

---

### APT10 — Stone Panda

| Field | Detail |
|---|---|
| **Also Known As** | Stone Panda, MenuPass, Cicada, Potassium, BRONZE RIVERSIDE, Cloud Hopper, Red Apollo |
| **Attributed To** | Chinese MSS, Tianjin Bureau |
| **Active Since** | ~2009 |
| **Primary Motivation** | Intellectual property theft; managed service provider (MSP) compromise for downstream access |
| **Target Sectors** | Managed service providers, healthcare, pharmaceutical, aerospace, defense, automotive, satellite technology, government |
| **Target Regions** | United States, Japan, Europe, Australia; global via MSP compromise |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| PlugX | RAT | Widely shared Chinese RAT; used for persistence and lateral movement |
| QuasarRAT | RAT | Open-source RAT modified and deployed by the group |
| ANEL / ChChes | Backdoor | Used in later campaigns targeting Japanese organizations |
| RedLeaves | Backdoor | Evolved from the Poison Ivy RAT codebase |
| Mimikatz | Credential dumping | Used post-access for lateral movement |
| Ecipekac | Loader | Multi-layer shellcode loader observed in A41APT campaign (2021) |

**Signature TTPs**
- Compromise of managed service providers (MSPs) to access hundreds of downstream client organizations simultaneously (Operation Cloud Hopper)
- Spearphishing with job application-themed lures targeting Japanese corporations
- Use of compromised MSP VPNs and remote management tools for lateral movement
- Long-term persistence across both MSP and client environments simultaneously

**MITRE ATT&CK:** [G0045](https://attack.mitre.org/groups/G0045/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2016–2018 | Operation Cloud Hopper | Compromised managed service providers globally to access intellectual property of MSP clients across 45+ companies in 15 countries |
| 2018 | U.S. DOJ Indictments | DOJ indicted two Chinese nationals affiliated with APT10 for the Cloud Hopper campaign and theft of IP from over 45 government agencies and companies |
| 2021 | A41APT (Japan Targeting) | Targeted Japanese companies using novel Ecipekac loader; campaign name reflects overlap with APT41 tools |

**Key Reports**
- [MITRE ATT&CK: APT10](https://attack.mitre.org/groups/G0045/)
- [PwC & BAE Systems: Operation Cloud Hopper](https://www.pwc.co.uk/cyber-security/pdf/pwc-cyber-threats-2017-a-year-in-retrospect.pdf)
- [Kaspersky: Ecipekac / A41APT Campaign](https://securelist.com/apt10-sophisticated-multi-layered-loader-ecipekac-discovered-in-a41apt-campaign/101519/)

---

### Mustang Panda — TA416

| Field | Detail |
|---|---|
| **Also Known As** | TA416, RedDelta, Bronze President, HoneyMyte, PKPLUG, Earth Preta |
| **Attributed To** | Chinese state-sponsored; MSS-aligned |
| **Active Since** | ~2014 |
| **Primary Motivation** | Espionage; diplomatic and geopolitical intelligence collection |
| **Target Sectors** | Government, NGOs, diplomatic missions, religious organizations, think tanks, military |
| **Target Regions** | Southeast Asia, Europe, Vatican, Africa; countries aligned with or of interest to China's Belt and Road Initiative |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| PlugX / Korplug | RAT | Primary implant; used in virtually all Mustang Panda operations |
| TONEINS / TONESHELL | Backdoor | Custom implant family unique to Mustang Panda |
| PUBLOAD | Stager | Used to deliver second-stage payloads |
| ShadowPad | Modular backdoor | Used in some operations |

**Signature TTPs**
- Spearphishing with malicious archives containing LNK files or weaponized documents themed around geopolitical events (T1566.001)
- Abuse of legitimate software for DLL sideloading (T1574.002)
- Domain fronting to evade network-layer detection
- Targeting of European diplomatic missions in parallel with Southeast Asian government targeting

**MITRE ATT&CK:** [G0129](https://attack.mitre.org/groups/G0129/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2020 | Vatican Targeting | Targeted the Vatican and Catholic missions ahead of China-Vatican diplomatic negotiations |
| 2022–2024 | Operation Earth Preta | Large-scale campaign against Southeast Asian diplomatic entities using spearphishing with geopolitical lures; deployed TONEINS/TONESHELL malware |

---

## North Korea-Nexus Groups

North Korean cyber operations are primarily executed through the **Reconnaissance General Bureau (RGB)**, specifically Bureau 121. DPRK groups serve two primary mandates: **intelligence collection** and **revenue generation** (cryptocurrency theft and financial fraud) to fund the regime's weapons programs. The "Lazarus Group" label is often used as an umbrella term in public reporting; in practice, multiple distinct subordinate units operate under different mandates.

---

### Lazarus Group — Hidden Cobra

| Field | Detail |
|---|---|
| **Also Known As** | Hidden Cobra, ZINC, Diamond Sleet, Guardians of Peace, Labyrinth Chollima, APT-C-26, NICKEL ACADEMY, Group 77, TraderTraitor, DreamJob |
| **Attributed To** | DPRK RGB (Reconnaissance General Bureau), Bureau 121, 414 Liaison Office |
| **Active Since** | ~2009 |
| **Primary Motivation** | Financial theft (cryptocurrency, SWIFT fraud, ransomware), espionage, sabotage |
| **Target Sectors** | Cryptocurrency exchanges, financial institutions, defense, aerospace, media, government |
| **Target Regions** | Global; United States, South Korea, and cryptocurrency platforms as primary targets |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| FALLCHILL | RAT | Multi-platform; persistent across years of Lazarus operations |
| HOPLIGHT | Backdoor | Used against financial targets |
| ELECTRICFISH | Tunneling tool | Used to exfiltrate data from isolated network segments |
| AppleJeus | macOS/Windows trojan | Trojanized cryptocurrency trading applications |
| DTrack | Infostealer / backdoor | Deployed against critical infrastructure; linked to the 2019 Indian nuclear plant incident |
| BLINDINGCAN | Backdoor | Used in Operation DreamJob spearphishing campaigns |
| WannaCry | Ransomware worm | Leveraged EternalBlue exploit; ~$4–8B in global damage (2017) |
| GoldDragon | Backdoor | Targeted South Korean organizations |
| NukeSped | RAT | Cross-platform backdoor family |

**Signature TTPs**
- "Operation DreamJob": fake job recruitment campaigns on LinkedIn targeting defense and tech sector employees with malicious attachments disguised as job offers (T1566)
- Supply chain attacks targeting software development environments
- Creation of fake companies and personas to gain employment at target organizations (see Blocknovas LLC, 2025)
- Cryptocurrency theft via trojanized applications (AppleJeus) and exchange compromises
- Watering hole attacks against financial and cryptocurrency platforms

**MITRE ATT&CK:** [G0032](https://attack.mitre.org/groups/G0032/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2014 | Sony Pictures Hack | Devastating combination of data theft, public leaks, and disk wiper (Destover) deployed in response to The Interview film |
| 2016 | Bangladesh Bank SWIFT Heist | Stole $81M via fraudulent SWIFT transactions; attempted $1B total theft |
| 2017 | WannaCry | Global ransomware worm using NSA's EternalBlue exploit; impacted 200,000+ systems across 150 countries |
| 2022 | Ronin Network / Axie Infinity | $620M stolen from Ronin blockchain bridge — largest single cryptocurrency theft at the time |
| 2022 | Horizon Bridge | $100M stolen from Harmony's Horizon Bridge |
| 2023 | Atomic Wallet | $100M+ stolen from Atomic Wallet users |
| 2025 | Bybit Exchange | $1.5B stolen from Dubai-based exchange — largest crypto theft on record |
| Ongoing | Operation DreamJob | Multi-year LinkedIn-based fake recruiting campaign targeting aerospace, defense, and cryptocurrency |

**Key Reports**
- [MITRE ATT&CK: Lazarus Group](https://attack.mitre.org/groups/G0032/)
- [CISA: TraderTraitor — North Korean Cryptocurrency Targeting](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-108a)
- [Risky.biz: The Many Personalities of Lazarus](https://risky.biz/laz/)
- [Lexfo: The Lazarus Constellation (Deep Technical Analysis)](https://blog.lexfo.fr/ressources/Lexfo-WhitePaper-The_Lazarus_Constellation.pdf)

---

### APT38 — Bluenoroff

| Field | Detail |
|---|---|
| **Also Known As** | Bluenoroff, Stardust Chollima, BeagleBoyz, NICKEL GLADSTONE, COPERNICIUM, Sapphire Sleet |
| **Attributed To** | DPRK RGB, Bureau 121 (subordinate to Lazarus umbrella) |
| **Active Since** | ~2014 |
| **Primary Motivation** | Financial theft — the regime's primary revenue-generating cyber unit |
| **Target Sectors** | Banks, financial institutions, cryptocurrency exchanges, ATM networks, SWIFT endpoints |
| **Target Regions** | Global; 38+ countries confirmed, concentrated in Asia, Latin America, Africa |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| ELECTRICFISH | Tunneling | Exfiltrates data across network segments |
| PowerRatankba | Downloader | Used in initial stages of financial institution targeting |
| PowerSpritz | Obfuscation tool | Obfuscates PowerShell payloads |
| DYEPACK | SWIFT manipulation | Specifically designed to tamper with SWIFT transaction records to cover theft |
| HERMES | Disk wiper | Destructive payload deployed post-theft to destroy evidence; also used as foundation for Ryuk ransomware |

**Signature TTPs**
- Long-term infiltration of bank networks (average 1.5+ years dwell time before theft execution)
- Manipulation of SWIFT interbank messaging systems to execute fraudulent transfers
- ATM jackpotting via custom malware implanted on ATM management infrastructure
- Deliberate deployment of destructive wipers post-theft to destroy forensic evidence

**MITRE ATT&CK:** [G0082](https://attack.mitre.org/groups/G0082/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2016 | Bangladesh Bank | $81M stolen via fraudulent SWIFT transfers; attempted total was ~$1B |
| 2018 | Banco de Chile | ATM jackpotting + SWIFT fraud; $10M+ stolen |
| 2018 | Bancomext (Mexico) | Attempted $110M SWIFT fraud |
| 2020 | BeagleBoyz Revival | U.S. government advisory documenting resumed ATM cashout operations across Africa and Asia |

**Key Reports**
- [MITRE ATT&CK: APT38](https://attack.mitre.org/groups/G0082/)
- [Mandiant: APT38 — Un-usual Suspects](https://www.mandiant.com/resources/blog/apt38-details-on-new-north-korean-regime-backed-threat-group)
- [CISA: BeagleBoyz — Robbing Banks](https://www.cisa.gov/news-events/alerts/2020/08/26/north-korean-malicious-cyber-activity-fak19-007)

---

### Kimsuky — Thallium

| Field | Detail |
|---|---|
| **Also Known As** | APT43, Thallium, Emerald Sleet, Sparkling Pisces, Velvet Chollima, CERIUM, Black Banshee |
| **Attributed To** | DPRK RGB, Bureau 121 |
| **Active Since** | ~2012 |
| **Primary Motivation** | Espionage and intelligence collection; credential theft to support North Korean foreign policy goals |
| **Target Sectors** | Government, think tanks, academia, nuclear policy organizations, media, human rights organizations, cryptocurrency |
| **Target Regions** | South Korea (primary), United States, Japan, Europe; wherever Korean Peninsula policy is discussed |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| BabyShark | Downloader | Visual Basic Script-based downloader; named due to links to KimJongRAT |
| KimJongRAT | RAT | Simple infostealer linked to early Kimsuky operations |
| GoldDragon | Backdoor | Used against South Korean targets |
| AppleSeed | Backdoor | Custom Android and Windows backdoor |
| Sharpext | Browser extension | Malicious browser extension that silently exfiltrates email from Gmail and AOL webmail |
| RandomQuery | Infostealer | Used in recent credential phishing campaigns |
| KONNI | RAT | Associated with Kimsuky; deployed against diplomatic and government targets |

**Signature TTPs**
- "King of Spearphishing" — highly tailored, research-intensive social engineering campaigns
- Extensive pre-attack reconnaissance; engages targets in extended email conversations before deploying malware
- Credential phishing infrastructure designed to mimic Korean government and research institutions
- Cryptocurrency theft to fund regime espionage operations (APT43 function)
- IP validation techniques to serve malicious content only to intended victims

**MITRE ATT&CK:** [G0094](https://attack.mitre.org/groups/G0094/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2014 | Korea Hydro & Nuclear Plant | Targeted South Korean nuclear operator with destructive and espionage objectives |
| 2020 | COVID-19 Vaccine Research Targeting | Targeted pharmaceutical companies developing COVID-19 vaccines (CERIUM cluster, identified by Microsoft) |
| 2023 | Microsoft / NSA Joint Advisory | Joint advisory documenting Kimsuky's social engineering TTPs targeting think tanks and journalists |
| 2024 | Sharpext Campaigns | Deployed malicious browser extensions to exfiltrate emails from targets discussing North Korean policy |

**Key Reports**
- [MITRE ATT&CK: Kimsuky](https://attack.mitre.org/groups/G0094/)
- [CISA: North Korean Kimsuky Hackers Using Social Engineering Tactics](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-301a)
- [Volexity: North Korean APT Uses Browser Extension to Steal Emails](https://www.volexity.com/blog/2022/11/17/north-korean-kimsuky-apt-uses-browser-extension-to-steal-emails-from-google-and-aol-users/)

---

### Andariel — Silent Chollima

| Field | Detail |
|---|---|
| **Also Known As** | Silent Chollima, Jumping Spider, Onyx Sleet, Dark Seoul, Rifle, Wassonite |
| **Attributed To** | DPRK RGB, Bureau 121 |
| **Active Since** | ~2015 |
| **Primary Motivation** | Espionage and disruption against South Korean entities; ransomware for revenue generation |
| **Target Sectors** | South Korean defense, government, financial, healthcare; increasingly global ransomware targeting |
| **Target Regions** | South Korea (primary); increasingly United States and global |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| Maui | Ransomware | Deployed against U.S. healthcare and public health organizations |
| DTrack | Backdoor / Infostealer | Shared with Lazarus; used in nuclear facility targeting |
| MagicRAT | RAT | Golang-based RAT; used in targeted espionage operations |
| YamaBot | RAT | Cross-platform Golang RAT |
| EarlyRat | RAT | Used in Log4Shell exploitation campaigns |

**MITRE ATT&CK:** [G0138](https://attack.mitre.org/groups/G0138/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2013 | Dark Seoul | Wiping attacks against South Korean banks and broadcasters; caused significant disruption |
| 2019 | Indian Nuclear Plant | DTrack malware discovered in Kudankulam Nuclear Power Plant network |
| 2022 | Maui Ransomware | U.S. government advisory attributing Maui ransomware targeting of U.S. hospitals to Andariel |

---

## Iran-Nexus Groups

Iran's cyber operations support two intelligence services: the **MOIS** (Ministry of Intelligence and Security) and the **IRGC** (Islamic Revolutionary Guard Corps). Iran-linked APTs are characterized by heavy spearphishing, increasing use of destructive wiper malware, and a growing focus on Israel and the United States. Tool-sharing across Iranian APT clusters is common, and operations frequently combine espionage with disruptive objectives.

---

### APT33 — Elfin

| Field | Detail |
|---|---|
| **Also Known As** | Elfin, Refined Kitten, Peach Sandstorm, HOLMIUM, MAGNALLIUM, Yellow Garuda |
| **Attributed To** | Iranian IRGC |
| **Active Since** | ~2013 |
| **Primary Motivation** | Espionage and potentially destructive operations; aligned with IRGC strategic objectives |
| **Target Sectors** | Aerospace, aviation, defense, energy, petrochemical, satellite technology |
| **Target Regions** | United States, Saudi Arabia, South Korea, Western Europe |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| DROPSHOT | Dropper | Installs StoneDrill and Turnedup |
| StoneDrill | Disk wiper | Sophisticated wiper; regional variant of Shamoon used against targets in Saudi Arabia |
| Turnedup | Backdoor | Custom backdoor used alongside wiper operations |
| PoshC2 / PowerShell Empire | Post-exploitation | Open-source frameworks used alongside custom tooling |
| ShimRatReporter | Recon tool | Used in early-stage reconnaissance |

**Signature TTPs**
- Spearphishing with domain masquerading (impersonates legitimate aviation and energy companies)
- Password spraying targeting Microsoft 365 and Azure Active Directory at scale (primary initial access method since 2023)
- Multi-stage attacks combining espionage tooling with destructive capability (StoneDrill)
- Possible collaboration with APT34 on destructive ZeroCleare wiper campaigns

**MITRE ATT&CK:** [G0064](https://attack.mitre.org/groups/G0064/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2017 | Initial Public Disclosure | FireEye disclosed APT33 targeting of aviation and energy sectors in the U.S., Saudi Arabia, and South Korea |
| 2018–2019 | StoneDrill / ZeroCleare | Destructive wiper operations against Gulf energy sector targets |
| 2023–2024 | Peach Sandstorm Password Spraying | Large-scale Microsoft 365 password spraying against U.S. defense, satellite, and pharmaceutical targets |

**Key Reports**
- [MITRE ATT&CK: APT33](https://attack.mitre.org/groups/G0064/)
- [Microsoft: Peach Sandstorm Password Spray Campaigns](https://www.microsoft.com/en-us/security/blog/2023/09/14/peach-sandstorm-password-spray-campaigns-enable-intelligence-collection-at-high-value-targets/)

---

### APT34 — OilRig

| Field | Detail |
|---|---|
| **Also Known As** | OilRig, Helix Kitten, Hazel Sandstorm, COBALT GYPSY, IRN2, CHRYSENE, TA452 |
| **Attributed To** | Iranian MOIS (Ministry of Intelligence and Security) |
| **Active Since** | ~2014 |
| **Primary Motivation** | Espionage; intelligence collection in support of MOIS strategic objectives |
| **Target Sectors** | Government, financial services, telecommunications, energy, chemical, defense |
| **Target Regions** | Middle East (primary); United States, Europe |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| POWRUNER | PowerShell backdoor | DNS tunneling-based C2 |
| BondUpdater | Backdoor | Uses DNS tunneling for C2 communication |
| SideTwist | Backdoor | Native implant supporting file operations and remote shell |
| Karkoff | Backdoor | Lightweight C# backdoor |
| RDAT | Backdoor | Uses steganography within Exchange-based C2 |
| MailDropper | Implant | Deployed against Lebanese government entities; uses email for C2 |
| DNSpionage | Campaign toolset | DNS tunneling implant used in Middle Eastern targeting |
| OopsIE | Trojan | Used with a variant of ISMDoor for persistence |

**Signature TTPs**
- Highly developed DNS tunneling C2 architecture; multiple malware families implement custom DNS-based communication
- Spearphishing with job application-themed lures or weaponized documents
- Abuse of legitimate cloud services (OneDrive, Exchange Online) as covert C2 channels
- Supply chain attacks leveraging trust relationships between target organizations and their IT providers
- DNS tunneling is a signature technique shared across the majority of APT34 malware families

> **Notable:** In 2019, a threat actor using the Telegram persona "Lab Dookhtegan" publicly leaked APT34's full toolset, victim data, and infrastructure details. The group rebuilt its toolset within weeks, demonstrating significant development capacity.

**MITRE ATT&CK:** [G0049](https://attack.mitre.org/groups/G0049/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2018–2019 | DNSpionage | Targeted government and private sector in Lebanon and the UAE using DNS hijacking |
| 2019 | Lab Dookhtegan Leak | Group's tools, infrastructure, and victim list publicly exposed via Telegram |
| 2023–2024 | Iraq / Yemen Targeting | Targeted Iraqi government and Yemeni telecom entities as part of regional intelligence gathering aligned with MOIS priorities |

**Key Reports**
- [MITRE ATT&CK: APT34](https://attack.mitre.org/groups/G0049/)
- [Palo Alto Unit 42: OilRig Campaign Overview](https://unit42.paloaltonetworks.com/tag/oilrig/)
- [Cisco Talos: DNSpionage Campaign](https://blog.talosintelligence.com/dnspionage-campaign-targets-middle-east/)

---

### APT35 — Charming Kitten

| Field | Detail |
|---|---|
| **Also Known As** | Charming Kitten, Mint Sandstorm, PHOSPHORUS, Magic Hound, Newscaster, TA453, ITG18, Yellow Garuda |
| **Attributed To** | Iranian IRGC (Islamic Revolutionary Guard Corps) |
| **Active Since** | ~2014 |
| **Primary Motivation** | Espionage and influence operations; targeting of journalists, activists, dissidents, and foreign policy personnel |
| **Target Sectors** | Government, academia, media, human rights organizations, political campaigns, pharmaceutical |
| **Target Regions** | United States, Israel, UK, Western Europe; targeting of Iranian diaspora globally |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| POWERSTAR (GorjolEcho) | Backdoor | PowerShell-based backdoor delivered via phishing |
| HYPERSCRAPE | Email scraper | Steals email contents from Gmail, Yahoo, and Outlook web accounts |
| PINEFLOWER | Mobile spyware | Android spyware targeting Iranian dissidents |
| NokNok | macOS backdoor | Delivered via trojanized VPN applications; targets macOS users |
| BANANAPHONE | Backdoor | Recently observed implant |
| MFA interception kits | Phishing credential harvester | Browser-in-the-middle proxies that intercept MFA codes in real time |

**Signature TTPs**
- Highly elaborate, research-intensive social engineering; spends weeks or months building rapport with targets before deploying malware
- Impersonates journalists, academics, think tank researchers, and policy officials
- Multi-stage MFA interception via browser-in-the-middle credential phishing infrastructure
- Abuse of cloud services (Dropbox, Google Drive, IPFS, Backblaze) for C2
- Targeting of medical researchers (COVID-19 vaccines), nuclear negotiators, and presidential campaign staff

**MITRE ATT&CK:** [G0059](https://attack.mitre.org/groups/G0059/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2019–2020 | Scholar / Journalist Targeting | Extended impersonation of journalists and think tank staff to compromise U.S. and European foreign policy researchers |
| 2020 | COVID-19 Vaccine Research | Targeted pharmaceutical companies including Gilead Sciences during peak of COVID-19 pandemic |
| 2024 | U.S. Presidential Campaign Targeting | Compromised and attempted to compromise staff associated with both U.S. presidential campaigns; passed material to domestic political actors |

**Key Reports**
- [MITRE ATT&CK: APT35](https://attack.mitre.org/groups/G0059/)
- [Google TAG: Charming Kitten Updates HYPERSCRAPE](https://blog.google/threat-analysis-group/new-iranian-apt-data-extraction-tool/)
- [Microsoft: Mint Sandstorm Campaign Overview](https://www.microsoft.com/en-us/security/blog/2024/04/17/iran-affiliated-threat-actor-mint-sandstorm-targets-high-profile-individuals-as-israel-hamas-conflict-continues/)

---

### MuddyWater — Static Kitten

| Field | Detail |
|---|---|
| **Also Known As** | Static Kitten, Seedworm, TEMP.Zagros, Mercury, Earth Vetala, Mango Sandstorm |
| **Attributed To** | Iranian MOIS (Ministry of Intelligence and Security) |
| **Active Since** | ~2017 |
| **Primary Motivation** | Espionage; access provision to other MOIS-aligned actors |
| **Target Sectors** | Government, telecommunications, defense, oil and natural gas, academia, NGOs |
| **Target Regions** | Middle East, Central Asia, Europe, North America |

**Malware Arsenal**

| Malware | Type | Notes |
|---|---|---|
| POWERSTATS | PowerShell backdoor | Core implant; multiple versions observed across campaigns |
| MuddyC2Go | C2 framework | Latest evolution of MuddyWater's proprietary C2 ecosystem (POWERSTATS → MuddyC3 → PhonyC2 → DarkBeatC2 → MuddyC2Go) |
| Small Sieve | Backdoor | Uses Telegram API for C2 |
| PowGoop | DLL loader | Loads PowerShell scripts via DLL sideloading |
| Canopy / Starwhale | WSF-based implant | Distributed via malicious Excel files |
| Syncro RMM / SimpleHelp | Legitimate RMM tools | Abuses commercial remote monitoring and management tools as C2 |

**Signature TTPs**
- Delivery of remote management and monitoring (RMM) tools (Atera, Syncro, SimpleHelp) within malicious archives as primary initial access vector
- Spearphishing using password-protected archives containing malicious links or documents
- Heavy use of open-source red team tools (Mimikatz, Invoke-Obfuscation, Lazagne)
- C2 infrastructure abuses cloud platforms (Telegram API, OneDrive, GitHub)
- Provides stolen access and data to other MOIS cyber units
- Supply chain compromise of IT providers to gain access to downstream organizations

**MITRE ATT&CK:** [G0069](https://attack.mitre.org/groups/G0069/)

**Notable Campaigns**

| Year | Campaign | Description |
|---|---|---|
| 2021 | Rashim IT Supply Chain Attack | Compromised Israeli IT company to gain downstream access to dozens of organizations |
| 2022 | CISA/FBI Joint Advisory | U.S. government publicly attributed MuddyWater to MOIS; provided IOCs and TTPs |
| 2023–2024 | DarkBeatC2 / MuddyC2Go | Rollout of updated C2 infrastructure targeting governments and telecoms in Middle East and Central Asia |

**Key Reports**
- [MITRE ATT&CK: MuddyWater](https://attack.mitre.org/groups/G0069/)
- [CISA: Iranian Government-Sponsored Actors — MuddyWater](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-055a)
- [Trend Micro: MuddyWater Campaign Analysis](https://www.trendmicro.com/en_us/research.html)

---

## Notable Campaigns Index

A cross-reference index of landmark campaigns with their attributed groups.

| Campaign | Group | Year | Impact |
|---|---|---|---|
| SolarWinds SUNBURST | APT29 | 2020 | ~18,000 organizations compromised; U.S. government-wide breach |
| NotPetya | Sandworm | 2017 | ~$10B global damage; most destructive cyberweapon deployed to date |
| WannaCry | Lazarus | 2017 | 200,000+ systems in 150 countries; ~$4–8B in damage |
| Operation Cloud Hopper | APT10 | 2016–2018 | Compromised MSPs across 15 countries; IP theft from 45+ organizations |
| Ukraine Power Grid | Sandworm | 2015–2016 | First confirmed cyberattack to cause power outages |
| Bangladesh Bank SWIFT Heist | APT38 | 2016 | $81M stolen; $1B attempted |
| Bybit Exchange | Lazarus | 2025 | $1.5B stolen — largest crypto theft on record |
| U.S. Telecom Breach | Salt Typhoon | 2024 | Nine major U.S. telecoms compromised; lawful intercept infrastructure accessed |
| DNC Breach | APT28 / APT29 | 2016 | Interference in U.S. presidential election |
| Ronin / Axie Infinity | Lazarus | 2022 | $620M stolen from blockchain bridge |
| Sony Pictures | Lazarus | 2014 | Disk wiping + data leak campaign in retaliation for The Interview |
| Olympic Destroyer | Sandworm | 2018 | Disrupted Winter Olympics IT infrastructure; false-flag attribution |
| TRITON / TRISIS | Suspected IRGC | 2017 | Targeted Schneider Electric safety instrumentation systems; first attack designed to cause physical harm |

---

## Tracking & Reference Resources

These are the essential tools and platforms for tracking APT group activity and conducting further research.

### Authoritative Group Profiles
- [MITRE ATT&CK Groups](https://attack.mitre.org/groups/): The definitive reference for TTPs, software, and campaigns organized by group
- [Mandiant APT Profiles](https://www.mandiant.com/resources/insights/apt-groups): Mandiant's group tracking with deep technical context
- [CrowdStrike Adversary Universe](https://www.crowdstrike.com/adversaries/): CrowdStrike's adversary profiles with naming convention explanations
- [ETDA APT Group Cards](https://apt.etda.or.th/cgi-bin/aptgroups.cgi): Thailand CERT's comprehensive APT card database; cross-references aliases

### Threat Intel Aggregators
- [APT Campaign Collection (CyberMonitor)](https://github.com/CyberMonitor/APT_CyberCriminal_Campagin_Collections): GitHub repository aggregating APT campaign reports by date
- [ThaiCERT Threat Actor Encyclopedia](https://apt.etda.or.th): Searchable APT group database with alias cross-referencing
- [vx-underground APT Papers](https://vx-underground.org): Archive of threat intelligence papers and research
- [Malpedia](https://malpedia.caad.fkie.fraunhofer.de): Malware family encyclopedia with attribution links to APT groups
- [VulDB CTI](https://vuldb.com): Vulnerability database with threat actor tracking

### IOC & Infrastructure Hunting
- [Shodan](https://www.shodan.io): Search for APT C2 infrastructure patterns
- [VirusTotal Graph](https://www.virustotal.com/graph/): Pivot through related malware samples and infrastructure
- [RiskIQ / Microsoft Defender TI](https://ti.defender.microsoft.com): Infrastructure hunting and passive DNS
- [Validin](https://app.validin.com): DNS and infrastructure hunting for APT C2

---

## Contributing

This compendium is a living document. Contributions are welcome — please submit a pull request with:
- New group entries following the established template
- Updates to existing entries with new malware, campaigns, or reports
- Corrections to aliases, attribution, or TTPs with supporting citations

For significant structural changes, please open an issue for discussion first.

---

*Last substantively updated: 2025. Attribution reflects open-source threat intelligence community consensus and is subject to revision.*
