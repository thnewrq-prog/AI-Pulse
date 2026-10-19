# AI Pulse 업데이트 기록 / Changelog

## v1.13.5 — 트레이 하단 안내 수정 / Popup notice hotfix

- 트레이 하단의 브라우저 응답 지연 등 상태 문구가 계속 남던 문제를 수정했습니다. 문구는 6초 뒤 사라지며 정상 응답/상태 수신 시 즉시 해제됩니다.
- 정상 상태 메시지를 초기 읽기 응답으로 처리하여, 데이터가 도착했는데도 뒤늦게 시간 초과 안내가 뜨는 경우를 방지했습니다. 다른 명령은 실제 응답을 기다립니다.
- 알림 해제 시 트레이 팝업 높이를 다시 계산합니다. 서비스 수집·트레이 조정·초기화 알림 일정은 변경하지 않았습니다.
- 설치 payload 45개 중 popup.js만 교체하고 나머지 44개 파일의 원본 일치를 확인했습니다. 같은 제품이 설치돼 있으면 수정 파일 강제 복구와 설치 원본 갱신을 수행하도록 설치기를 재빌드했습니다. 버전 번호는 1.13.5를 유지합니다.
- 원본 문제의 모의 재현, 패치 구문 검사 및 회귀 테스트 6개를 통과했습니다. 설치기와 실제 Windows 트레이는 실행하지 않았습니다.
- Exit all tray instances and browsers, rerun the updated installer, and reload the extension. Status notices now expire after six seconds or clear on successful responses/state updates. A valid snapshot completes the initial read without leaving a false timeout. Only popup.js in the installed payload changed; the wrapper also supports repairing an existing installation. Version remains 1.13.5. Installer/tray end-to-end behavior was not exercised.

## v1.13.5 — v1.8.0 대비 누적 업데이트

비교 기준: 이 저장소의 AI-Pulse-v1.8.0.zip과 사용자가 제공한 AI-Pulse-v1.13.5.zip. 설치 EXE를 실행하지 않고 내장 MSI의 실제 파일을 추출해 비교했습니다. 개별 버전 번호는 동봉된 누적 사용안내에 기록된 경우만 표시합니다.

### 추가 기능

- **Windows 트레이 프로그램:** 브라우저 확장과 Native Messaging으로 연결해 작업 표시줄의 트레이에서 사용량·잔액 팝업, 전체/개별 갱신, 대시보드를 사용할 수 있습니다. 브라우저 팝업과 같은 화면 파일을 사용하며 트레이 화면은 WebView2를 사용합니다.
- **초기화 알림:** 전체/서비스별 알림을 켜고 매주 요일·매월 날짜·한 번만 실행하는 초기화 일정을 설정합니다. 초기화 24시간 이내에 회차당 한 번 알리며, 반복 일정은 다음 회차로 계산합니다. 해당 날짜가 없는 달은 말일을 사용합니다. 사이트의 실제 초기화 시각을 자동으로 알아내는 기능이 아니라 사용자가 설정한 일정입니다.
- **Windows 테스트 알림 (v1.13.1):** 계정 연결이나 자동 알림 활성화 없이 알림을 시험할 수 있습니다. 테스트는 실제 일정과 발송 기록을 변경하지 않습니다. 알림 클릭 시 대시보드가 열립니다.
- **서비스 메인 화면 바로가기 (v1.13.4):** 팝업의 서비스 아이콘을 클릭해 새 브라우저 탭으로 메인 화면을 엽니다. 미연결 서비스도 사용 가능하고 키보드 Enter/Space를 지원합니다. 사용자 추가 서비스의 계정·결제 경로 및 쿼리·해시를 제거하며, 동작 줄이기 설정을 반영합니다.
- **설치 구성 변경:** Windows Installer(MSI) 기반으로 확장과 데스크톱 동반 프로그램을 설치합니다. 사용자의 로컬 앱 폴더에 설치하고 Chrome/Edge Native Messaging 호스트를 등록합니다. 내장 MSI의 SHA-256을 확인한 뒤 설치를 진행합니다.

### 개선 및 버그 수정

- **트레이 아이콘 중복 (v1.13.5):** 브라우저·프로필마다 연결은 유지하되 공유 메모리와 Mutex로 표시 담당을 하나로 조정합니다. 연결 서비스가 더 많은 프로필을 우선하고 동률이면 기존 담당을 유지합니다. 이전 아이콘을 먼저 숨긴 뒤 승계하며, 담당 종료와 PID 재사용도 처리합니다. 프로필의 데이터를 서로 병합하는 기능은 아닙니다.
- **계정 연결 창 정리 (v1.13.2, v1.13.5):** ComfyUI Cloud·Suno·Higgsfield는 잔액을 읽지 못하더라도 로그인된 계정 표시를 확인하면 계정 연결용으로 연 탭을 닫을 수 있습니다. 로그인 성공 확인과 잔액 수집 성공을 구분합니다. 일반 탭·수동 공식 화면·인증 입력·인증 대화상자·잔액 위치 지정은 자동 정리 대상에서 제외하며 관찰 시간은 10분입니다.
- **Suno 로그인 감지 (v1.13.5):** 활성 로그인 세션을 페이지 안에서 확인하고 참/거짓만 반환합니다. 중복된 Sign out/로그아웃 접근성 이름과 화면 문구를 각각 검사합니다. 로그인 UI 지연 및 단일 페이지 내 주소 변경을 재확인합니다. 이 확인에서 사용자 ID·세션 ID·토큰·쿠키 값을 확장으로 반환하지 않습니다.
- **Gemini 사용량 수집:** 대화 본문 대신 사용량 팝오버·패널에서 현재 세션과 주간 한도를 구분합니다. 업그레이드 광고 수치를 제외하고 한국어 '사용' 표현을 인식합니다. 메뉴의 아이콘 텍스트를 제거해 버튼을 찾고, 반복 클릭을 줄이며, 숨김 페이지 타이머 지연에 대응하도록 워커에서 단계별 조회를 실행합니다.
- **Edge 자동 등록 (v1.13.3, 동봉 안내 기준):** 여러 개발자 모드 접근성 제어 방식과 한국어/영어 로드 버튼 이름을 지원합니다. 폴더 경로·선택창 종료·대시보드 응답을 확인하고 진단 로그를 남깁니다. 조직 정책 제한 시 중단하며 정책을 변경하지 않도록 안내합니다. 이번 비교에서는 실제 Edge 등록을 실행하지 않았습니다.
- **Magnific·Lumina 프리셋 주소:** Magnific의 구독 화면과 BytePlus Lumina 요금제 화면으로 기본 조회 주소를 변경하고 해당 도메인의 권한 요청 범위를 조정했습니다. 기존에 저장한 서비스 주소까지 자동 이전한다고 보장하지 않습니다.

### 동작·권한 변경 및 호환성

| 항목 | v1.8.0 | v1.13.5 |
| --- | --- | --- |
| 배포 | 확장 폴더 + 자동 등록 EXE | MSI를 내장한 설치 EXE + Windows 트레이 동반 프로그램 |
| 자동 조회 창 | 최소화 창과 debugger 실행 유지 | 트레이가 조회 창 숨김을 확인한 뒤 사이트로 이동; 트레이 미연결/숨김 실패 시 중단 |
| 확장 권한 | storage, scripting, debugger | storage, scripting, nativeMessaging, alarms, notifications |
| 기본 사이트 접근 | 선택적 호스트 권한 | 기본 서비스 및 Magnific/BytePlus를 host_permissions로 선언 |
| 추가 사이트 접근 | 선택적 HTTP/HTTPS 권한 | 선택적 HTTP/HTTPS 권한 유지 |
| ComfyUI 잔액 응답 | debugger를 통해 공식 응답 본문 판독 | 해당 응답 수신 경로가 비활성화됨; 화면 판독/잔액 위치 지정 사용 |
| 확장 ID | manifest에 고정 공개키 없음 | manifest에 공개키 추가; v1.8.0의 기존 연결·기록 자동 이전은 보장하지 않음 |

조회 창이 만들어지는 순간 작업 표시줄에 잠깐 나타날 수 있습니다. 일부 사이트는 숨김 상태에서 수집을 제한할 수 있습니다. 자동 조회에는 브라우저와 트레이 연결이 필요하고, 초기화 알림에는 브라우저 실행 및 Windows/브라우저의 알림 허용이 필요합니다. 알림 API 수락은 실제 배너 표시를 보장하지 않습니다.

### 설치 및 업데이트

1. 기존 AI Pulse 트레이 아이콘을 모두 우클릭해 종료하고 관련 Chrome/Edge를 닫습니다. 이전 프로세스는 새 트레이 조정에 참여하지 않습니다.
2. ZIP을 압축 해제하고 **AI-Pulse-설치.exe**를 실행합니다.
3. 설치 후 AI Pulse 시작 화면에서 Chrome 또는 Edge를 선택해 등록합니다. 자동 등록 중 브라우저와 폴더 선택창을 조작하지 않습니다.
4. 브라우저를 다시 시작해 확장 관리 화면에서 **1.13.5**를 확인하고 필요하면 새로고침합니다.
5. 계정 연결·트레이 연결 상태를 확인하고 설정에서 초기화 알림을 저장합니다.

v1.8.0의 기록이 필요하면 업데이트 전에 기록을 내보내세요. 기존 내보내기는 기록 보관용이며 전체 설정의 복원/가져오기 기능을 뜻하지 않습니다. 새 ZIP의 최상위에는 확장 폴더가 직접 들어 있지 않으므로 v1.8.0처럼 압축 해제만 한 뒤 ZIP 폴더를 Load unpacked로 선택하는 방식과 다릅니다.

설치 파일은 디지털 서명이 없습니다. 이전 설치기 차단 문제가 해결됐다고 검증한 배포판은 아닙니다. 보안 프로그램이 차단하면 탐지 내역을 확인하고 임의로 허용하지 마세요.

### 확인 범위

- **이번 비교에서 확인:** GitHub v1.8.0의 확장 29개 파일과 비교 기준 일치, 설치기 내장 MSI 해시 일치, MSI 45개 파일 정적 추출, 확장 JavaScript 전체 구문 검사, 첨부 로그인 회귀 테스트 81개 통과(입력 경로만 추출 위치로 변경).
- **배포 문서가 보고한 별도 검증:** 트레이 선택/승계 11개, 실제 프로세스 2개의 공유 상태/Mutex 검사, 바로가기 18개, Native Messaging 3개, 알림 로직 19개 및 UI 4개, Edge 등록 로직 23개 및 대시보드 연동 3개. 이 비교 작업에서 모두 재실행한 결과는 아닙니다.
- **이번 작업에서 실행하지 않음:** 설치 EXE/MSI, 실제 Windows 트레이 아이콘, 실제 서비스 로그인·갱신, Windows 알림 배너, Chrome/Edge 자동 등록, 백신 검사. 전체 동작 성공 또는 보안 미탐지를 보장하지 않습니다.

## v1.13.5 — English summary (since v1.8.0)

### Added

- Windows tray companion connected through Native Messaging, sharing the browser popup UI through WebView2.
- User-configured weekly, monthly, or one-time reset reminders within the preceding 24 hours, once per cycle; short months use the last day.
- Test notifications (v1.13.1), without changing real schedules or delivery history.
- Clickable service icons to open product home pages (v1.13.4), with keyboard and reduced-motion support.
- MSI-based installation with an embedded payload checksum and Chrome/Edge native-host registration.

### Fixed and improved

- Duplicate tray icons across browsers/profiles: retain connections while coordinating one visible owner, prioritizing more connected services and preserving the owner on ties (v1.13.5).
- Account Connect tabs can close after confirming sign-in independently of balance collection for ComfyUI, Suno, and Higgsfield (v1.13.2/1.13.5); manual pages, credential/verification screens, and balance picking remain protected.
- Suno active-session checks return only a boolean; duplicated logout labels, delayed UI updates, and single-page route changes are handled (v1.13.5).
- Gemini usage popovers, session/weekly labels, Korean usage wording, icon-bearing menu controls, and hidden-page timer delays are handled more specifically.
- Edge developer-mode controls, load-button labels, folder confirmation, dashboard response, and diagnostic logging improved according to bundled notes (v1.13.3).
- Magnific and Lumina presets now point to Magnific subscriptions and BytePlus Lumina plans.

### Behavior and compatibility

The debugger permission is removed; nativeMessaging, alarms, and notifications are added. Background refresh requires the tray connection and verified window hiding. The previous debugger-based ComfyUI balance-response capture is inactive; screen reading and balance binding remain. Built-in domains are now declared in host_permissions, while extra domains remain optional. A manifest public key stabilizes the new extension ID; automatic migration of v1.8.0 data is not guaranteed.

Exit all old tray instances and browsers, extract the ZIP, run AI-Pulse-설치.exe, register Chrome/Edge from the start screen, restart the browser, and verify version 1.13.5. The package does not contain a top-level unpacked-extension folder. The installer is unsigned; no antivirus clearance is claimed. JavaScript syntax and 81 mocked login regression checks passed during this comparison. Installation, real-account collection, tray UI, notification banners, and full browser registration were not exercised. Other test counts in the bundled report are author-reported results.

---

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
