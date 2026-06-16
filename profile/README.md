# cloiworks

정욱(@hongmono)의 개인 프로젝트와 홈서버 인프라를 관리하는 조직.

## 🏗 인프라 (2026-06 현재)

```
인터넷 ──▶ OCI 엣지(공인 IP, Traefik + WireGuard 허브)
                 │  *.hongmono.com · Let's Encrypt TLS 종단
                 │  WireGuard 터널 (10.10.0.0/24) + 홈LAN 라우팅
                 ▼
         홈 Proxmox ── k3s VM(10.10.0.4) ── HAOS VM
                          │ k3s + ArgoCD (GitOps)
                          ▼
              tinyauth · n8n · homepage · recipe-book · 근태 CronJob
```

- **엣지**: OCI 인스턴스. Traefik이 `*.hongmono.com`을 TLS 종단 후 WireGuard 너머 홈 서비스(NodePort)로 라우팅.
- **컴퓨트**: 홈 Proxmox 위 k3s 단일노드 + **ArgoCD app-of-apps**. 모든 배포는 `cloiworks/gitops` repo 선언으로 일어남(GitOps).
- **인증**: `tinyauth`(forward-auth)가 보호 서비스의 SSO 게이트.
- **home-assistant**: Proxmox 별도 VM(HAOS).

## 📦 서비스 / 프로젝트

| repo | 설명 | 배포 |
|------|------|------|
| [gitops](https://github.com/cloiworks/gitops) | k3s + ArgoCD GitOps 선언(인프라의 단일 소스) | — |
| [recipe-book](https://github.com/cloiworks/recipe-book) | 🍳 레시피북 (Rust API + 웹, SQLite + Cloudflare D1 백업) | k3s · recipe.hongmono.com |
| [homepage](https://github.com/cloiworks/homepage) | 정적 홈페이지(nginx) | k3s · home.hongmono.com |
| [sprite-studio](https://github.com/cloiworks/sprite-studio) | 스프라이트/스티커 생성 FastAPI | k3s(현재 보류) |
| [winter_mario](https://github.com/cloiworks/winter_mario) | Next.js 미니게임 | — |
| [folio_flow](https://github.com/cloiworks/folio_flow) | macOS 캡처·OCR 앱(Swift) | 로컬 앱 |
| [lotto-purchase-action](https://github.com/cloiworks/lotto-purchase-action) | 로또 자동구매 GitHub Action(미러) | GitHub Action |

## 🛠 스택

![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![k3s](https://img.shields.io/badge/k3s-FFC61C?style=flat-square&logo=k3s&logoColor=black)
![Argo CD](https://img.shields.io/badge/Argo%20CD-EF7B4D?style=flat-square&logo=argo&logoColor=white)
![Traefik](https://img.shields.io/badge/Traefik-24A1C1?style=flat-square&logo=traefikproxy&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A?style=flat-square&logo=wireguard&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white)
