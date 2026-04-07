# cloiworks

개인 프로젝트와 홈서버 인프라를 관리하는 조직입니다.

## 🛠 기술 스택

![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Nuxt](https://img.shields.io/badge/Nuxt-00DC82?style=flat-square&logo=nuxt.js&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Traefik](https://img.shields.io/badge/Traefik-24A1C1?style=flat-square&logo=traefikproxy&logoColor=white)

## 📦 주요 프로젝트

### 🍳 [recipe-book](https://github.com/cloiworks/recipe-book)
개인 레시피 관리 서비스.
Rust(Axum) 백엔드 API + Nuxt 프론트엔드로 구성되며, Cloudflare D1을 백업 스토리지로 활용합니다.

- **Backend**: Rust (Axum)
- **Frontend**: Nuxt 3
- **DB**: SQLite + Cloudflare D1

### 📖 [wiki](https://github.com/cloiworks/wiki)
개인 지식 베이스. Obsidian으로 작성한 노트를 git으로 관리합니다.

### 🚀 [migration-guides](https://github.com/cloiworks/migration-guides)
서버 마이그레이션 가이드. 레시피북, Traefik, WireGuard 설치 및 복구 절차를 문서화합니다.

## 🏗 인프라

- **서버**: Oracle Cloud (Ubuntu)
- **리버스 프록시**: Traefik v2 + Let's Encrypt 자동 SSL
- **VPN**: WireGuard (홈 네트워크 연결)
- **홈서버**: Proxmox + Home Assistant
- **도메인**: hongmono.com

## 🤖 개발 방식

AI 에이전트(Claude, Codex)를 활용한 개발을 지향합니다.
인프라 관리, 코드 작성, 문서화 등 대부분의 작업을 에이전트와 함께 처리합니다.
