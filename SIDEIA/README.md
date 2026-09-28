# SIDEIA (근데?) 공개 페이지

App Store 제출과 앱이 읽는 공개 파일. 정적 파일만 있고 외부 의존 없음.

| 파일 | 용도 | 쓰는 곳 |
|---|---|---|
| `privacy.html` / `privacy-en.html` | 개인정보처리방침 (한/영) | App Store Connect 개인정보 처리방침 URL, 앱 설정 |
| `support.html` / `support-en.html` | 지원·문의 (한/영) | App Store Connect 지원 URL |
| `prompts.json` | 날짜를 지정한 오늘의 문장 | 앱이 내려받음 |

## prompts.json

```json
{ "version": 1,
  "ko": [{ "date": "2026-10-05", "text": "우산은 비를 기다린다." }],
  "en": [{ "date": "2026-10-05", "text": "The umbrella waits for rain." }] }
```

- `date` 는 `yyyy-MM-dd`, `text` 는 100자 이내이고 물음표로 끝나지 않는다. 어긋난 항목은 앱이 버린다.
- 앱은 **받은 다음 날부터** 쓴다 → 문장은 최소 이틀 앞서 올린다.
- `version` 이 1이 아니거나 JSON 이 깨지면 앱은 파일 전체를 무시하고 이전에 받은 것을 쓴다.

## 고칠 때

- 앱이 새 정보를 다루게 되면 앱 업데이트 전에 개인정보처리방침부터 고친다.
