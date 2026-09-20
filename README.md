# SecuryBlack Agent Homepage Template

Official base template and **Catalyst** design system for all SecuryBlack agent websites (`titan-vault-homepage`, `oxi-pulse-homepage`, `ferro-sentry-homepage`, `cupra-flow-homepage`, `cromo-forge-homepage`).

---

## 🎯 Architecture & Purpose

Just as all native Rust agents share runtimes and networking primitives through [`sb-agent-core`](https://github.com/securyblack/sb-agent-core), all agent websites share this unified **Homepage Template ("Web Core")**.

### Core Features:
1. **Precision Catalyst Design System:** 100% aligned with the **SecuryBlack App** UI (`bg-zinc-950`, micro-borders `border-zinc-800`, `Inter` typography with `cv11`, smooth animations with `motion`).
2. **Total Separation of Engine vs Content:** Visual layouts, animations, responsive design, and SEO components are shared. Text copy, theme colors, technical benchmarks, and install snippets live in a single config file: [`config/agent.config.ts`](config/agent.config.ts).
3. **Interactive Terminal Simulator:** Live browser showcase simulating the agent's interactive terminal TUI without static screenshots or heavy video assets.
4. **Cloudflare Pages Native:** Ready for edge deployment with `@opennextjs/cloudflare` via `npm run build:cf`.

---

## 🚀 How to Export or Sync an Agent Homepage

### Step 1: Clone the repository
```bash
git clone https://github.com/securyblack/sb-agent-homepage-template my-agent-homepage
cd my-agent-homepage
npm install
```

### Step 2: Configure your agent in `config/agent.config.ts`
Set the agent identity, theme, and features:
```ts
export const activeAgentConfig: AgentConfig = {
  id: "my-agent",
  name: "MyAgent",
  tagline: "High-performance server observability",
  theme: {
    primary: "#10B981",       // Primary accent
    primaryDark: "#059669",
    primaryLight: "#34D399",
    glow: "rgba(16, 185, 129, 0.15)",
    accentTag: "emerald",
  },
  installCommands: [
    { os: "Linux", cmd: "curl -fsSL https://install.myagent.dev | sudo bash" }
  ],
  stats: [ ... ],
  features: [ ... ],
  faq: [ ... ],
};
```

### Step 3: Local development & edge build
```bash
# Run local dev server
npm run dev

# Build for Cloudflare Pages
npm run build:cf
```

### Export Script
You can automatically sync or bootstrap any agent website using the built-in sync script:
```bash
node scripts/export-agent.mjs ../oxi-pulse-homepage oxi-pulse
```

---

## 🎨 Official SecuryBlack Agent Palette

| Agent | Primary Color | Accent | Purpose |
|---|---|---|---|
| **TitanVault** | **Cyan (`#06B6D4`)** | Sky (`#38BDF8`) | Zero-disk streaming backups & disaster recovery |
| **OxiPulse** | **Mint (`#33E1BF`)** | Emerald (`#10B981`) | Real-time vital signs, CPU/RAM, OTLP metrics |
| **FerroSentry** | **Scarlet (`#F43F5E`)** | Rose (`#FB7185`) | Host security, lightweight EDR, nftables firewall |
| **CupraFlow** | **Copper (`#F97316`)** | Orange (`#FB923C`) | High availability, VRRP VIP failover, WireGuard mesh |
| **CromoForge** | **Cobalt (`#6366F1`)** | Violet (`#818CF8`) | GitOps, atomic container delivery & auto-rollback |

---

## License

Apache-2.0 License.
