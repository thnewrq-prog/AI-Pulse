<div align="center">

# AI Pulse

### Your AI usage. One clear view.

Track usage limits, remaining credits, and Fast GPU time across your AI services.

**Chrome & Edge 118+** · **7 built-in services + custom services** · **v1.8.0**

[**Download v1.8.0 ↓**](./AI-Pulse-v1.8.0.zip?raw=true) · [What’s new](#whats-new) · [Installation](#installation) · [Features](#features) · [한국어 안내](#korean-guide)

</div>

---

## 📑 Contents

1. [💻 Overview](#overview)
2. [🚀 Features](#features)
3. [🤖 Supported services](#supported-services)
4. [📦 Installation](#installation)
5. [▶️ Quick start](#quick-start)
6. [🔄 Updating](#updating)
7. [🔐 Privacy & permissions](#privacy--permissions)
8. [🛠️ Troubleshooting](#troubleshooting)
9. [🇰🇷 한국어 안내](#korean-guide)
10. [✨ v1.8.0 updates / 업데이트](#whats-new)

<a id="whats-new"></a>

## ✨ v1.8.0 updates / 업데이트

Changes since **v1.6.1**, including the intervening updates.

### English

- **Custom AI services:** Add, edit, or remove services with your own URL, name, color, icon text, and credit/GPU-time type.
- **10 presets:** Magnific, Lumina, Dreamina, Kling AI, Hailuo AI, OpenArt, Runway, Leonardo.Ai, ElevenLabs, and Luma Dream Machine. Presets help fill in service details; they are not dedicated API integrations. Balance-location selection may be needed.
- **Improved balance picker:** Preview the hovered area, choose a number when several appear, expand to a parent element, and record/replay menu-opening clicks. Saved locations are also used for manual page reads, and successful selections are added to refresh history.
- **ChatGPT collection improvements:** A dedicated reader recognizes explicit quota values on the official Usage screen, excludes conversation content and app-limit settings, waits longer for loading, and avoids repeatedly toggling menus. It does not estimate overall chat usage when no quota is shown.
- **Korean / English:** Switch languages from the new Settings tab or the top bar. The selected language is saved and applied to the dashboard, popup, balance picker, and related UI.
- **Windows installation helper:** The included AI-Pulse-설치기.exe requests administrator approval and automates extension registration for Microsoft Edge or Google Chrome, including Developer mode and folder selection. Manual installation remains available.
- **Settings shortcuts and site access:** Access service creation, layout editing, history export, and data deletion from Settings. Custom services request optional access to their domain and subdomains when connected.

The existing seven services, 1.5-second Refresh All notice, concurrent background checks, and lookup-window cleanup are retained. ComfyUI's official balance-response reader was already present in v1.6.1.

### 한국어

**v1.6.1 대비 변경 사항**이며, 중간 버전에서 추가된 기능을 포함합니다.

- **사용자 정의 AI 서비스:** 원하는 서비스의 주소·이름·색상·표시 기호·크레딧/GPU 시간 유형을 직접 등록·수정·삭제할 수 있습니다.
- **10종 프리셋:** 매그니픽, 루미나, 드리미나, 클링, 하일루오, 오픈아트, Runway, Leonardo.Ai, ElevenLabs, Luma Dream Machine을 추가했습니다. 프리셋은 기본 정보 입력을 돕는 기능이며, 서비스별 API 연동은 아닙니다. 잔액 위치 지정이 필요할 수 있습니다.
- **잔액 위치 지정 개선:** 마우스 호버 미리보기, 여러 숫자 중 순번 선택, 상위 영역 선택, 메뉴 열기 클릭 단계 기록·재실행을 지원합니다. 수동 화면 읽기에도 저장한 위치를 사용하고, 지정 성공 결과를 갱신 기록에 추가합니다.
- **ChatGPT 조회 개선:** 공식 사용량 화면의 명시적 한도 수치를 읽는 전용 판독기를 추가했습니다. 대화 내용·앱별 한도 설정값의 오인식을 방지하고, 로딩 대기와 메뉴 반복 클릭 처리를 개선했습니다. 표시되지 않은 전체 채팅 사용률을 추정하지 않습니다.
- **한국어·영어 지원:** 새 설정 탭과 상단 버튼에서 언어를 전환하고 저장할 수 있습니다. 대시보드·팝업·잔액 위치 지정기 등 관련 UI에 반영됩니다.
- **Windows 자동 설치기:** 동봉된 AI-Pulse-설치기.exe가 관리자 권한 승인을 요청한 뒤 Edge 또는 Chrome의 개발자 모드 활성화와 확장 폴더 등록을 자동화합니다. 기존 수동 설치 방식도 사용할 수 있습니다.
- **설정·권한 관리:** 설정 화면에서 서비스 추가, 화면 배치 편집, 기록 내보내기·데이터 삭제에 접근할 수 있습니다. 직접 추가한 서비스는 연결할 때 해당 도메인과 하위 도메인의 선택적 접근 권한을 요청합니다.

기존 7종 서비스, 전체 갱신 시 1.5초 대기, 동시 백그라운드 조회, 조회 창 자동 정리는 유지됩니다. ComfyUI 공식 잔액 응답 판독은 v1.6.1에 이미 포함된 기능입니다.

---

<a id="overview"></a>

## 💻 Overview

Switching between account pages to check your AI limits takes time. **AI Pulse brings those checks into a compact toolbar popup and a customizable dashboard.**

Sign in on each service's official website, refresh AI Pulse, and see the latest available usage or balance with its last checked time.

> **Current status:** v1.8.0 adds custom services, Korean/English language settings, and a Windows installation helper. Collection still depends on the official website and account; successful operation across all services and real accounts has not been verified.

<a id="features"></a>

## 🚀 Features

### 🧩 Quick-view popup & dashboard

- Check service usage directly from the extension icon.
- Open the full dashboard for balances, last checked times, and refresh history.

### ⚡ One-click, concurrent refresh

- Refresh All starts automatically after a **1.5-second notice**, with no second confirmation.
- Check all connected, visible services together, or refresh a service individually.

### 🖥️ Background checks

- Lookup windows start minimized without requesting focus on your work window.
- AI Pulse closes the windows it creates when each check finishes. Browser and service restrictions can still cause failures.

### 🎛️ A dashboard that fits your workflow

- Reorder cards and hide or restore services with **화면 편집** (*Edit Layout*).
- Hidden services are excluded from Refresh All.

### 💾 Local preferences & history

- Keep connection settings, dashboard layout, results, and history in your browser.
- Reuse your setup after a restart while the same browser profile and service login sessions remain valid.

### 🌙 Dark theme

- Black surfaces, white text, and neon green accents make usage and balances easy to scan.

<a id="supported-services"></a>

## 🤖 Supported services

| Usage limits | Information available on the official website |
| :--- | :--- |
| **Google Gemini** | Usage percentages and limits |
| **Claude** | Session and weekly usage |
| **ChatGPT** | Available usage percentages and limits |

| Credits & time | Balance |
| :--- | :--- |
| **ComfyUI Cloud** | Remaining credits |
| **Midjourney** | Included and purchased/awarded Fast time |
| **Suno** | Remaining credits |
| **Higgsfield** | Remaining credits |

Custom credit/GPU-time services can also be added using the 10 presets or your own URL. Use **Bind Balance** to select the number to read.

Information varies by account and service. Values are **snapshots from the last refresh**, not a continuously updating live feed. AI Pulse does not track API token usage or API billing, and it does not combine unrelated limits or balances.

<a id="installation"></a>

## 📦 Installation

**Requirements:** Chrome or Microsoft Edge **118 or later**, with Developer mode enabled.

**Windows helper:** Extract the ZIP and run the included **AI-Pulse-설치기.exe**. Approve the administrator prompt and select Edge or Chrome to automate registration. Confirm that AI Pulse appears in the extension list. You can also install manually:

1. [Download **AI-Pulse-v1.8.0.zip**](./AI-Pulse-v1.8.0.zip?raw=true) and extract it.
2. Open your browser's extension management page:

   | Browser | Address |
   | :--- | :--- |
   | Chrome | `chrome://extensions` |
   | Edge | `edge://extensions` |

3. Turn on **Developer mode** and click **Load unpacked**.
4. Select the extracted **AI-Pulse** folder containing `manifest.json`.
5. Review any permission prompts and pin AI Pulse to the toolbar.

> **Downloading the whole repository?** Extract the repository archive first, then extract the `AI-Pulse-v1.8.0.zip` inside it. Load the inner **AI-Pulse** folder, not the repository folder or the ZIP itself.

<a id="quick-start"></a>

## ▶️ Quick start

**Connect once → Sign in → Refresh → Check your results**

1. Click the extension icon, then **새 탭 열기** (*Open in New Tab*).
2. Choose **계정 연결** (*Connect Account*) for a service.
3. Sign in directly on that service's official website.
4. Return to AI Pulse and click **전체 갱신** (*Refresh All*).
5. A notice appears; checks start automatically **1.5 seconds later**, with no second confirmation.
6. View the results and last checked times in the popup or dashboard.

You can continue working during checks. Keep the browser running and leave the minimized lookup windows alone; AI Pulse closes the windows it creates when each check finishes.

<details>
<summary><strong>Useful controls & login sessions</strong></summary>

| Interface label | Meaning |
| :--- | :--- |
| 새 탭 열기 | Open the full dashboard |
| 계정 연결 | Connect an account |
| 전체 갱신 | Refresh all connected, visible services |
| 화면 편집 | Reorder, hide, or restore cards |
| 잔액 위치 지정 | Select a credit balance location |
| 수동 화면 읽기 | Read the currently opened official page |

Connection settings survive browser and computer restarts. Your service login must remain valid in the **same browser profile**. Expired sessions require signing in again.

</details>

<a id="updating"></a>

## 🔄 Updating

1. Extract the new version and overwrite the files in your existing **AI-Pulse** installation folder.
2. Open the extension management page and click **Reload** for AI Pulse.
3. Review any new permission prompts, then close and reopen the dashboard.

Keeping the same installation folder and browser profile helps preserve your existing settings.

<a id="privacy--permissions"></a>

## 🔐 Privacy & permissions

- **Official sign-in:** You log in on each service's own website. AI Pulse does not collect or store passwords, cookies, or authentication tokens.
- **Local storage:** Connection settings, dashboard preferences, usage results, and history stay in your browser. AI Pulse does not send them to a separate server.
- **Site access:** Permission to access a service's official pages is needed to read the available usage information. Custom services use optional HTTP/HTTPS host permissions; connecting a service requests access to its domain and subdomains.
- **Debugger access:** The `debugger` permission grants broad browser capabilities. AI Pulse uses it on automatically created lookup tabs to maintain page activity and read ComfyUI's official workspace balance response. It does not attach to your existing work tabs.
- **Visible browser notices:** Chrome or Edge may show a debugging notification during checks. Canceling that connection can interrupt a check. AI Pulse disconnects and closes its lookup windows afterward.

<a id="troubleshooting"></a>

## 🛠️ Troubleshooting

| Problem | Try this |
| :--- | :--- |
| Login or security check required | Open the official page, complete the check yourself, and refresh again. |
| Credits are missing | Use **잔액 위치 지정** (*Select Balance Location*) on the credit service card. |
| Automatic lookup fails | Open the official page from AI Pulse, then use **수동 화면 읽기** (*Read Current Page*) on the account connection page. |
| Results look old | Check the last checked time and refresh the service. |
| A lookup stops | Keep the browser running; avoid closing lookup windows or canceling the debugging connection. |

Website changes, network conditions, browser policies, and account differences can affect collection. Minimized lookup windows may appear in your taskbar, and checks are not guaranteed to succeed on every account.

[**Report an issue →**](https://github.com/thnewrq-prog/AI-Pulse/issues) Include the service name, extension version, and error message. Remove personal information from screenshots before posting.

---

<a id="korean-guide"></a>

<details>
<summary><strong>🇰🇷 한국어 안내 — 소개 · 설치 · 사용 방법</strong></summary>

### 💻 AI 사용량을 한곳에서

**AI Pulse**는 Gemini·Claude·ChatGPT의 사용량과 ComfyUI Cloud·Midjourney·Suno·Higgsfield의 잔여 크레딧 또는 Fast 시간을 확인하는 Chrome·Edge 확장 프로그램입니다.

### 📦 설치

**Windows 자동 설치:** ZIP 압축을 푼 뒤 **AI-Pulse-설치기.exe**를 실행하고 관리자 권한을 승인한 다음 Edge 또는 Chrome을 선택합니다. 설치 후 확장 목록에 AI Pulse가 표시되는지 확인하세요. 수동 설치는 아래 순서로 진행합니다.

1. 상단의 **Download v1.8.0**을 눌러 ZIP을 내려받고 압축을 풉니다.
2. Chrome은 `chrome://extensions`, Edge는 `edge://extensions`를 엽니다.
3. **개발자 모드 → 압축해제된 확장 프로그램 로드**를 누릅니다.
4. `manifest.json`이 들어 있는 **AI-Pulse** 폴더를 선택합니다.
5. 권한 안내를 확인하고 확장 아이콘을 고정합니다.

저장소 전체를 내려받았다면, 그 안의 **AI-Pulse-v1.8.0.zip도 한 번 더 압축 해제**해야 합니다.

### ▶️ 사용

**확장 아이콘 → 새 탭 열기 → 계정 연결 → 공식 사이트 로그인 → 전체 갱신**

- 전체 갱신은 안내 후 **1.5초 뒤 자동 시작**하며, 표시 중인 연결 서비스를 동시에 확인합니다.
- 조회 결과와 시각은 팝업 또는 대시보드에서 확인합니다.
- **화면 편집**에서 카드 순서와 표시 여부를 바꿀 수 있습니다.
- 같은 브라우저 프로필에서 로그인 상태가 유지되면 재시작 후에도 갱신할 수 있습니다.

### 💡 알아두세요

조회값은 마지막 갱신 시점의 스냅샷입니다. API 토큰·청구 금액은 조회하지 않습니다. 가려진 페이지 실행 유지와 ComfyUI 공식 잔액 응답 확인에 **디버깅 권한**을 사용하며, 브라우저에 디버깅 표시가 나타날 수 있습니다. 조회 창은 최소화되고 작업 표시줄에 나타날 수 있습니다.

v1.8.0은 사용자 정의 서비스와 한영 전환을 지원하며, 모든 실제 계정에서의 조회 성공을 보장하지 않습니다. 로그인 만료·보안 확인·사이트 변경 등으로 실패하면 공식 화면에서 상태를 확인하거나 **잔액 위치 지정 / 수동 화면 읽기**를 사용하세요.

### 🔄 업데이트

기존 설치 폴더에 새 파일을 덮어쓴 뒤 **확장 프로그램 새로고침 → 대시보드 다시 열기**를 진행합니다.

</details>
