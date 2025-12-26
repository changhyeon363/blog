---
title: AI, Workflow 관련 오픈소스 및 서비스
draft: false
date: 2025-12-27
---

> [!warning]
> 아래 내용은 ChatGPT.com가 작성하였습니다. 
> 부정확한 내용이 포함될 수 있습니다.

## 1️⃣ **Workflow Orchestrator (파이프라인 실행·관리자)**

> “**이 일들을 언제, 어떤 순서로, 실패하면 어떻게 재시도할까?**”

**목적**

- 배치 작업, 데이터 파이프라인, ML 파이프라인 관리
    
- 스케줄링, 재시도, 상태 추적, 의존성 관리
    

**대표 도구**

- Apache Airflow
    
- Prefect
    
- Dagster
    
- Metaflow
    
- Argo Workflows
    

**핵심 차이**

- Airflow: **전통적·강력·무거움**
    
- Prefect: **개발자 친화 / 유연**
    
- Dagster: **데이터 중심 / 타입·메타데이터**
    
- Metaflow: **ML 실험·모델 중심**
    
- Argo: **K8s 네이티브 / 인프라 중심**
    

👉 **AI·데이터 쪽이라면**  
➡️ _Prefect / Dagster / Metaflow_ 가 현실적으로 잘 맞음

---

## 2️⃣ **Automation / iPaaS (업무 자동화·연결)**

> “**이벤트가 오면 이 서비스랑 저 서비스 연결해줘**”

**목적**

- API 연결
    
- 트리거 기반 자동화
    
- 노코드/로우코드
    

**대표 도구**

- n8n
    
- Zapier, Make 등
    

**특징**

- **비개발자 친화**
    
- 데이터 파이프라인보단 **업무 자동화**
    
- AI 파이프라인의 _외곽_에 많이 붙음
    

👉 **AI 서비스 운영 보조용**으로 최고  
(예: “새 문서 업로드 → 임베딩 → DB 저장”)

---

## 3️⃣ **LLM Workflow / Agent Framework (AI 사고 흐름)**

> “**LLM이 어떤 순서로 생각하고, 도구를 쓰고, 판단할까?**”

**목적**

- LLM 체인 구성
    
- 에이전트 상태 관리
    
- Tool calling, memory
    

**대표 도구**

- LangFlow
    
- LangGraph
    
- LangChain
    

**특징**

- **데이터 파이프라인 아님**
    
- **‘추론 흐름’** 을 다룸
    
- 실시간·인터랙션 중심
    

👉 **RAG / Agent / 챗봇** = 여기 영역

---

## 4️⃣ **Pipeline 사고방식 (도구 이전 개념)** ⭐ 중요

> “**선형이든 병렬이든, DAG로 생각하는 습관**”

이건 툴이 아니라 **사고방식**이에요.

```text
수집 → 전처리 → 분석 → 저장 → 알림
```

이걸:

- 단계로 나누고
    
- 의존성을 명확히 하고
    
- 중간 결과를 재사용 가능하게 만들면
    

➡️ **어떤 툴을 써도 흔들리지 않음**

---

## 5️⃣ 한 장으로 정리하면

|범주|질문|대표|
|---|---|---|
|Workflow Orchestrator|언제·순서·재시도?|Prefect, Dagster|
|Automation|서비스 연결?|n8n|
|LLM Workflow|AI가 어떻게 생각?|LangGraph|
|UI Builder|시각적 체인|LangFlow|
|사고방식|DAG로 나눴나?|(개념)|
