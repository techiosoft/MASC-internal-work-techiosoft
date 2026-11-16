---
marp: true
theme: default
paginate: true
header: ''
style: |
  @import url('https://fonts.googleapis.com/css2?family=PT+Sans:ital,wght@0,400;0,700;0,900;1,400&family=Lora:ital,wght@0,600;0,700;1,600&display=swap');
  :root {
    --navy:#194722; --accent:#1E7A38; --ink:#1b1b1b; --muted:#5B6B5C;
    --gold:#E8C530; --dark:#102418; --dark-ink:#F5F8F2; --dark-muted:#AFC6AB;
  }
  section {
    font-family: 'PT Sans', 'Myriad Pro', 'Helvetica Neue', Arial, sans-serif;
    font-size: 24px; line-height: 1.5; color: var(--ink);
    font-variant-ligatures: none;
    padding: 66px 76px 110px 76px;
    justify-content: flex-start !important;
    align-content: flex-start !important;
    background-color: #F7F9F4;
    border-top: 6px solid var(--accent);
    background-image: url('assets/techio-logo.png'), url('assets/masc-logo.png');
    background-repeat: no-repeat, no-repeat;
    background-position: 50px calc(100% - 34px), calc(100% - 48px) 26px;
    background-size: 56px, 92px;
  }
  h1 {
    font-family: 'Lora', 'PT Sans', Georgia, serif;
    color: var(--navy); font-size: 48px; font-weight: 700; letter-spacing: -0.012em; line-height: 1.15;
  }
  h2 {
    color: var(--navy); font-size: 38px; font-weight: 700; letter-spacing: -0.015em;
    border-bottom: 3px solid var(--accent); padding-bottom: 10px; margin: 0 0 26px;
  }
  h3 { color: var(--accent); font-size: 25px; font-weight: 700; margin-bottom: 4px; }
  p { margin: 0 0 15px; }
  strong { color: var(--accent); font-weight: 700; }
  em { color: var(--muted); font-style: normal; }
  ul, ol { margin: 0 0 15px; }
  li { margin-bottom: 14px; }
  section.cards3 ul {
    list-style: none; padding: 0; margin: 8px 0 0;
    display: grid; grid-template-columns: repeat(auto-fit, minmax(230px, 1fr)); gap: 22px;
  }
  section.cards3 li {
    margin: 0; padding: 20px 22px 18px; min-height: 130px;
    background: var(--dark); border-left: 4px solid var(--gold); border-radius: 9px;
    font-size: 18px; line-height: 1.32; color: var(--dark-muted);
  }
  section.cards3 li strong { display: block; color: var(--gold); font-size: 22px; margin-bottom: 6px; }
  section.stats ul {
    list-style: none; padding: 0; margin: 20px 0 0;
    display: grid; grid-template-columns: repeat(4, 1fr); gap: 20px;
  }
  section.stats li { margin: 0; text-align: center; padding: 0 8px; }
  section.stats .num { display: block; font-size: 58px; font-weight: 700; color: var(--accent); line-height: 1; }
  section.stats .label { display: block; color: var(--navy); font-weight: 700; font-size: 18px; margin-top: 10px; }
  section.stats .desc { display: block; color: var(--muted); font-size: 15px; margin-top: 4px; line-height: 1.3; }
  section.lead { justify-content: center !important; align-content: center !important; text-align: center; }
  section.statement h1 { font-size: 90px; letter-spacing: -0.03em; margin: 0; }
  section::after { color: var(--muted); font-size: 16px; }
  section.agenda ol { line-height: 1.34; padding-left: 38px; margin-top: 10px; }
  section.agenda > ol > li {
    padding-left: 10px; padding-bottom: 16px; margin-bottom: 16px;
    font-size: 27px; border-bottom: 1px solid #E1E9D8;
  }
  section.agenda > ol > li:last-child { border-bottom: 0; margin-bottom: 0; }
  section.agenda li::marker { color: var(--accent); font-weight: 800; font-size: 27px; }
  section p em:only-child {
    display: block;
    background: var(--dark);
    border-left: 5px solid var(--gold);
    border-radius: 9px;
    color: var(--dark-ink); font-weight: 700; font-style: normal;
    font-size: 18px; line-height: 1.45;
    padding: 11px 18px; margin: 12px 0 0;
  }
  section.title {
    background-image: none;
    justify-content: center !important; align-content: center !important;
    text-align: center; padding: 56px 84px;
  }
  section.title h1 { font-size: 56px; margin: 0 0 16px; }
  section.title h3 {
    color: var(--muted); font-weight: 400; font-size: 27px;
    letter-spacing: 0; margin: 0 0 28px;
  }
  section.title img { vertical-align: middle; margin: 0 30px; }
  section.title .title-rule { width: 64px; height: 3px; background: var(--gold); border-radius: 2px; margin: 0 auto 40px; }
  section.title p { margin: 0; font-size: 22px; color: var(--muted); line-height: 1.6; }
  section.title p:last-of-type { margin-top: 56px; }
---

<!-- _class: title -->
<!-- _paginate: false -->

# MASC Client.Api Modernization

### Project Handoff

<div class="title-rule"></div>

![h:96](assets/masc-logo.png) ![h:68](assets/techio-logo.png)

TechIO<br>Monday, November 16, 2026

---

<!-- _class: agenda -->

## Agenda

1. **Realized Benefits**
2. **UAT & Quality Results**
3. **Closing Out the Engagement**
4. **Next Steps**
5. **Looking Ahead**

---

<!-- _class: cards3 -->

## Realized Benefits — Platform & Security

- **Supported runtime**
  Moved from .NET Framework 4.8 (end-of-life, no security patches) to .NET 10 LTS
- **Secure authentication**
  Replaced deprecated ADAL with MSAL / Microsoft.Identity.Web, routes and tokens unchanged
- **Platform portability**
  The service now runs on Linux Azure App Service, without containers
- **Safer secrets**
  Configuration and secrets now use managed identity

---

<!-- _class: cards3 -->

## Realized Benefits — Data, Monitoring & Parity

- **Modern data and code layers**
  14 dependency projects migrated, EF6 moved to EF Core 10, 3 dead references removed
- **Preserved monitoring**
  Telemetry now runs on the Azure Monitor OpenTelemetry SDK, same App Insights resource
- **Proven parity**
  Golden-master tests confirm identical responses, backed by unit, integration, and security testing
- **No consumer impact**
  Existing consumers need no changes

---

<!-- _class: stats -->

## UAT & Quality Results

*Reviewed and verified by your own team.*

<ul>
<li><span class="num">100%</span><span class="label">Codebase reviewed</span><span class="desc">Full UAT code review completed by the client-side business team</span></li>
<li><span class="num">15</span><span class="label">Bugs reported</span><span class="desc">Raised during the UAT code review</span></li>
<li><span class="num">15/15</span><span class="label">Bugs cleared</span><span class="desc">All reported bugs resolved by the TechIO team</span></li>
<li><span class="num">0</span><span class="label">Open defects</span><span class="desc">No outstanding UAT findings at handoff</span></li>
</ul>

*TechIO trains the modernizing agent on what we learned from this review, and continues tailoring it with enhancements specific to your APIs.*

---

<!-- _class: cards3 -->

## Closing Out the Engagement

*Client.Api has been live in the test environment since October 13, completing the project's signed scope. This handoff follows hypercare.*

- **Sign-off**
  Formal handoff document going out November 16 for your team's review and signature
- **Deliverables**
  Client.Api live in the test environment since Oct 13, plus source repos, test harness, dashboard, access checklist, and run guide

<!-- Deliverables list above should be confirmed complete with the Tech Lead before presenting. -->

---

<!-- _class: cards3 -->

## Next Steps

- **Go-live**
  When is production deployment scheduled on your team's side? That will help us align on next steps.
- **Your feedback**
  We'd love your take on the modernization itself, and on the agent-assisted approach that built it

<!-- Capture the client's feedback live and record it here afterward. -->

---

<!-- _class: cards3 -->

## Looking Ahead

- **TechIO's agentic platform**
  The same agent-driven approach behind Client.Api could extend to the rest of your API portfolio — worth a conversation with your executive team.

---

<!-- _class: lead statement -->
<!-- _paginate: false -->

# Thank You

### Questions and discussion
