# 🛡️ SOC Assistant Platform

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Snort-3.0-FF0000?style=for-the-badge&logo=target&logoColor=white" alt="Snort" />
  <img src="https://img.shields.io/badge/Database-Firestore-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firestore" />
  <img src="https://img.shields.io/badge/AI-Gemini_Flash-4285F4?style=for-the-badge&logo=google-gemini&logoColor=white" alt="Gemini" />
</p>

---

### 📝 Project Overview

현직 **SOC Security Analyst**가 분석 업무의 병목 현상을 해결하기 위해 직접 설계하고 구축한 **개인 맞춤형 위협 인텔리전스 플랫폼**입니다. 수작업 위주의 위협 수집 및 분석 프로세스를 자동화하고, AI를 활용하여 즉각적인 대응 가이드(Actionable Intelligence)를 생성하는 데 초점을 맞추었습니다.

---

## 🚀 Key Features

### 1. 🔍 CTI (Cyber Threat Intelligence) Module

* **우선순위 자동 식별**: NVD 데이터를 실시간 수집하여 `CISA KEV`, `Nuclei`, `PoC` 공개 여부에 따라 즉시 분석 대상을 필터링합니다.
* **AI 심층 분석 리포트**: 
    * `Executive Summary`: 취약점의 핵심 위험 요인 요약.
    * `Root Cause`: 코드 레벨에서의 취약점 발생 원인 분석.
    * `Mitigation`: WAF/IPS 룰 및 최신 패치 대응 방안 제시.
    * `Detection Logic`: 실제 공격 시 발생할 **Raw Packet** 예시 및 **Snort 룰** 자동 생성.

### 2. 🛡️ Snort Rule Manager & Tester

* **Packet Repeater**: 분석가가 직접 HTTP 패킷을 입력하여 생성된 Snort 룰이 정상적으로 탐지(Matching)되는지 실시간 시뮬레이션이 가능합니다.
* **GUI Rule Builder**: 복잡한 Snort 문법 없이도 직관적인 UI를 통해 2.x 및 3.x 버전의 룰을 생성하고 관리합니다.

### 3. 🌐 Unified Analyzer

* **OSINT 통합 조회**: `VirusTotal`, `AbuseIPDB`, `AlienVault OTX` 등 파편화된 인텔리전스를 하나의 화면에서 통합 조회합니다.
* **대량 분석 지원**: 최대 500개의 IP/Domain을 CSV로 업로드하여 일괄 평판 분석을 수행하고 결과를 리포팅합니다.

### 4. ☣️ Ransomware Monitoring

* **공격 그룹 추적**: `Embargo`, `Akira`, `Qilin` 등 주요 랜섬웨어 그룹의 피해 현황 및 유출 데이터를 실시간 모니터링합니다.
* **IoC 추출**: 공격에 사용된 인디케이터(MD5, SHA256, IP, Domain)를 즉시 추출하여 보안 정책에 반영할 수 있도록 지원합니다.

---

## 🖥️ UI Structure (Sidebar Menu)

| 메뉴 명칭 | 주요 기능 및 역할 |
| :--- | :--- |
| **SOC Dashboard** | 보안 이벤트 통계 및 실시간 모니터링 현황 요약 |
| **Threat Intelligence** | CVE 데이터베이스 관리 및 PoC 공개 여부 추적 |
| **Analysis Reports** | AI가 생성한 취약점별 심층 분석 기술 리포트 보관함 |
| **Unified Analyzer** | IP/Domain/Email 평판 통합 분석 및 OSINT 도구 |
| **Ransomware** | 랜섬웨어 그룹 동향 모니터링 및 IoC 데이터 제공 |
| **Snort Rules** | 탐지 규칙 생성, 관리 및 Packet Repeater 테스트 |

---

## 🛠️ Tech Stack & Integration

* **Backend & Logic**: ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
* **Database**: ![Firestore](https://img.shields.io/badge/Firestore-FFCA28?style=flat-square&logo=firebase&logoColor=black)
* **AI Integration**: ![Google Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=flat-square&logo=google-gemini&logoColor=white)
* **Intelligence Source**: `NVD API`, `CISA KEV`, `VirusTotal`, `AbuseIPDB`, `AlienVault OTX`

---

## 📝 Analysis Workflow

1. **Collection**: NVD 및 글로벌 보안 피드로부터 신규 위협 정보 자동 수집.
2. **Prioritization**: CISA KEV 등재 여부 및 PoC 존재 여부에 따른 분석 우선순위 선정.
3. **AI Deep Dive**: 취약점 코드 분석 및 대응 가이드(Snort 룰 포함) 자동 생성.
4. **Validation**: 생성된 탐지 룰을 Packet Repeater로 검증 후 실제 장비 적용 준비.
5. **Response**: 통합 분석 도구를 통한 공격자 IP 평판 확인 및 최종 차단 조치.
