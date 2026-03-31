# Product Context (Example)

This is a fictional but realistic filled-out product context. Use it as a reference for what "good" looks like when you fill out `context-library/product-context-template.md`.

---

## Product

**Product name:** FleetDash

**What it does (one sentence):** A B2B analytics platform that helps operations teams monitor fleet performance, respond to exceptions, and file compliance reports in real time.

**Primary platform(s):** Web (desktop-first for enterprise features, responsive for field use on tablets)

**Stage:** Early growth

---

## Users

**Primary user:** Operations manager at a mid-market logistics company (50-500 vehicles)

**What they're trying to accomplish:** Monitor fleet health across multiple depots, respond to exceptions before they escalate, and generate compliance reports without switching between three different tools.

**Key pain points (from research):**
- Switching between dispatch, maintenance, and compliance tools wastes 45+ minutes per shift
- Exception alerts lack context, so managers have to investigate every alert manually
- Compliance reports require exporting from two systems and reformatting in Excel

**Technical proficiency:** Medium. Comfortable with web apps, not comfortable with data queries or API tools. Expects consumer-grade UX in a B2B product.

**Accessibility considerations:** Must meet WCAG 2.1 AA. Many users work in high-glare warehouse environments (high contrast matters). Some enterprise customers require keyboard-only navigation for accessibility compliance.

---

## Design Constraints

**Design system maturity:** Storybook with ~80 components, actively maintained. Figma library synced monthly. Component coverage is strong for forms and data display, weaker for data visualization and dashboards.

**Engineering stack (relevant to design):** React + TypeScript. Tailwind for utility styles. Recharts for data visualization. No mobile native app yet.

**Responsive requirements:** Desktop-first for enterprise features. Tablet support for field use (depot walkarounds). Phone support not required for v1.

**Brand / visual constraints:** Primary: #1E40AF. Secondary: #059669. Typography: Inter. Spacing: 4px base grid. No custom illustrations until brand team approves an illustration style.

**Feature flags / phased rollout:** Features gated by organization tier (Starter, Pro, Enterprise). Gradual rollout via LaunchDarkly. New features ship to internal dogfood org first, then 10% rollout.

---

## Business Context

**Company:** FleetDash Inc.

**Business model:** B2B SaaS, seats-based pricing. Mid-Market ($5k-25k ARR) and Enterprise ($50k+ ARR) segments. Free trial with limited vehicle count.

**Current priorities (this quarter):**
- Reduce onboarding time-to-value from 14 days to 3 days
- Launch exception alerting v2 (context-rich alerts with suggested actions)
- Enterprise SSO and audit logging

**North Star metric:** Weekly active enterprise seats

---

## Design Team

**Team size and structure:** 3 product designers + 1 design lead. No dedicated content designer (designers handle microcopy with PM review). 1 part-time researcher shared across product.

**Design process:** Two-week design sprints aligned with engineering sprints. Weekly design critique Thursdays at 2pm. Weekly PM sync Mondays at 10am. Quarterly design review with VP Product.

**Handoff process:** Figma with annotations for visual spec. Written UX spec in markdown for behavior, states, and edge cases. Engineers pull component names from Storybook. Questions go to the designer in Slack, not in Figma comments.

**Research cadence:** Monthly usability studies (5 participants). Continuous discovery calls every 2 weeks with active customers. Quarterly competitive UX review.

---

## Notes

- The design team is currently migrating from an older component library to the current Storybook-based system. About 20% of the product still uses legacy components.
- The onboarding flow is the top design priority this quarter. It's the first thing new users see and currently has a 40% drop-off at step 3.
- Customer Success has strong opinions about the dashboard layout. Loop them in early on dashboard changes.
