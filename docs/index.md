---
hide:
  -toc
---
#
<style>
    /* Application header should be static for the landing page */
    .md-header {
      position: initial;
    }

    /* Remove spacing, as we cannot hide it completely */
    .md-main__inner {
      margin: 0;
    }

    .md-content{
      background: transparent !important;
    }
    .md-main__inner {
        background: transparent !important;
    }

    /* Hide navigation */
    @media screen and (min-width: 76.25em) {
      .md-sidebar--primary {
        display: none;
      }
    }
      /* Hide table of contents */
    @media screen and (min-width: 60em) {
      .md-sidebar--secondary {
        display: none;
      }
    }
  </style>
<div class="datu-hero">
  <img src="assets/datusignature.png" alt="Datu Logo" width="90" style="margin-bottom:1.5rem;">
  <div class="datu-hero-title">Datu AI Analyst</div>
  <div class="datu-hero-subtitle">Build intelligent, data-driven AI agents in just a few lines of code.</div>
  <a href="user-guide/quickstart/" class="datu-hero-btn">Get Started</a>
</div>

<div class="datu-features">
  <div class="datu-feature">
    <h3>Data-Driven Agents</h3>
    <p>Connect to databases, files, APIs, and more. Let your agents analyze, transform, and act on data.</p>
  </div>
  <div class="datu-feature">
    <h3>Provider Agnostic</h3>
    <p>Use any LLM provider—OpenAI, AWS Bedrock, Anthropic, and more. Switch providers without code changes.</p>
  </div>
  <div class="datu-feature">
    <h3>Simple Multi-Agent Workflows</h3>
    <p>Compose agents, tools, and workflows with simple primitives for collaboration and orchestration.</p>
  </div>
  <div class="datu-feature">
    <h3>Production Ready</h3>
    <p>Deploy to containers, serverless, or cloud. Built-in observability, security, and extensibility.</p>
  </div>
</div>

<div class="datu-cta">
  <div>Ready to get started?</div>
  <div style="margin:1rem 0 0.5rem 0;">Check out the quickstart guide or book a demo with our team.</div>
  <a href="user-guide/quickstart/" class="datu-cta-btn">Quickstart Guide</a>
  <a href="hello@datu.fi" class="datu-cta-btn">Book a Demo</a>
</div>
