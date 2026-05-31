# LLM Playground

base URL · model · API key · 파라미터를 전부 브라우저에서 조작할 수 있는 OpenAI 호환 LLM 채팅 프론트엔드. 단일 `index.html` 정적 페이지.

## 배포 (GitHub Pages)

1. 이 레포의 **Settings → Pages**
2. **Source: Deploy from a branch** 선택
3. Branch: `main` / `/ (root)` 지정 후 Save
4. 잠시 후 `https://amamirugi.github.io/llm-playground/` 에서 접속

## 사용법

1. **Base URL** 입력 — 예: `https://api.openai.com/v1`, `https://openrouter.ai/api/v1`, `http://localhost:11434/v1`
2. **API Key** 입력
3. **Model** 직접 입력 또는 목록 불러오기 버튼
4. 파라미터(temperature, max tokens, top_p, penalty, streaming) 토글 후 대화

각 파라미터 옆 토글을 끄면 요청 body에서 아예 제외돼. 특정 파라미터를 거부하는 백엔드에 유용.

## ⚠️ CORS 주의

브라우저에서 외부 API를 직접 호출하므로, 대상 서버가 CORS(`Access-Control-Allow-Origin`)를 허용해야 동작해.

- **로컬 Ollama**: `OLLAMA_ORIGINS` 환경변수 설정 후 재시작. 단 https 페이지에서 http localhost 호출은 혼합 콘텐츠로 막힘.
- **클라우드 API**: 브라우저 직접 호출을 막는 경우 프록시(예: Cloudflare Worker) 필요.

## 보안

API Key는 서버로 전송되지 않고 브라저의 localStorage에만 저장돼. 공용 PC에서는 주의.
