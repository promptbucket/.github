# 🌟 PromptBucket

> **A playground-turned-project by [@mayurrawte](https://github.com/mayurrawte) — now looking for OSS friends!**  
> Store, version & remix ✨ **prompts** and 🤖 **personas** the way Docker Hub stores containers.

---

## 🤔 What’s inside a PromptBucket package?
| Emoji | Piece | Why it matters |
|-------|-------|----------------|
| 📄 | **`promptbucket.yaml`** | One YAML file that carries **metadata** *and* the prompt / template text. |
| 📦 | `.pbt` archive | Tar-gzipped blob prefixed with `PBKT␀`, signed with Cosign & pushed to any OCI registry. |
| 🧠 | `knowledge/` *(optional)* | Extra facts or style guides a persona can cite. |
| ✅ | `tests/` *(optional)* | Promptfoo regression cases to keep outputs stable. |

A **Prompt** package has one `prompt:` block.  
A **Persona** package lists multiple `templates:` + `entrypoint:`.

---

## 🗂️ Our Repos

| Repo | 🚧 Status | 🔎 What you’ll find |
|------|-----------|--------------------|
| [`cli`](https://github.com/promptbucket/cli) | **stub ✅** | Go CLI `promptbucket` (init · build · push · pull…) |
| `hub-backend` | 🏗️ todo | Go API + job workers (lint, sign, index) |
| `hub-ui` | 🏗️ todo | Astro v4 + React + shadcn/ui website |
| `spec` | 🏗️ todo | YAML schema & docs for `.pbt` |
| `examples` | growing 🌱 | Sample prompts & personas |

---

## 🔭 Roadmap

| Phase | Task | Status |
|-------|------|--------|
| **CLI v0.1** | Stub scaffold (`init`, `build`, completions) | ✅ |
| | Packager (tar+gz, digest, YAML parsing) | 🛠️ |
| | CI matrix & unit tests | 🔹 |
| **CLI v0.2** | `lint`, `sign`, `verify` | 🔹 |
| **Backend MVP** | Supabase auth • API • worker queue | 🔹 |
| **UI Alpha** | Home + Explore + Publish wizard | 🔹 |
| **SDKs** | Python & Node loaders | 🔹 |
| **Community** | Docs, CONTRIBUTING, Prompt-Jam contest | 🔹 |

*Legend: 🔹 not started • 🛠️ in progress • ✅ done*

---

## 🚀 5-Minute Demo

```bash
# 1 · install
go install github.com/promptbucket/cli@latest

# 2 · create prompt
mkdir hello && cd hello
promptbucket init
# edit promptbucket.yaml …

# 3 · build & push
promptbucket build
promptbucket push mayurrawte/hello:0.1.0 hello-0.1.0.pbt --sign

Load in Python 🐍:

from promptbucket import load_prompt
tmpl = load_prompt("promptbucket://mayurrawte/hello:0.1.0")
messages = tmpl.render(name="Alice")

🤝 How to Help
	•	🐛 Find an issue with help wanted and comment “/claim”.
	•	🧑‍💻 Fork → branch feat/<topic> → make lint test build.
	•	🔖 Use Conventional Commits (feat:, fix:…).
	•	📬 Open PR — CI must be green. First-timers 🌱 welcome!

⸻

📝 License

Apache 2.0 for everything.
Disclaimers: hobby hours ⏰, no warranties — but lots of ❤️ for contributors!

Made with ☕ & 🎵 by Mayur Rawte.