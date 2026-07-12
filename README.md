# 종로유학원 영국 진학 AI 컨설팅 (chongro-uk-ai)

QS 세계대학랭킹 2027 데이터 기반 영국 대학 진학 진단 랜딩페이지.
`edm-uk-master-ai`의 구조를 기반으로 종로유학원용으로 새로 제작 — **석사 진단** + **학부 진단(파운데이션·IYO)** 2트랙.

## 구성

- `index.html` — 단일 파일 (Tailwind CDN + 바닐라 JS, 외부 API 없음)
- `assets/logo.png` — 종로유학원 로고
- `.nojekyll` — GitHub Pages 배포용

## 배포 (GitHub Pages)

```bash
cd chongro-uk-ai
git init && git add . && git commit -m "종로유학원 영국 진학 AI 컨설팅 v1"
# GitHub에서 새 저장소 chongro-uk-ai 생성 후:
git remote add origin https://github.com/jaebong-choi/chongro-uk-ai.git
git branch -M main && git push -u origin main
# 저장소 Settings → Pages → Branch: main 선택
```

## 공개 전 체크리스트

- [ ] `index.html` 상단의 `<meta name="robots" content="noindex, nofollow">` 줄 삭제 (시안 단계 검색 노출 방지용)
- [ ] 상담 신청 링크 확인: `https://www.coei.com/info/consult/reserve.php`
- [ ] 필요 시 전화번호 CTA 추가 (현재는 링크 상담만 연결)

## 데이터 갱신 포인트

| 위치 | 내용 | 갱신 주기 |
|---|---|---|
| `UG_UNIS` 배열 | 학부 22개교 — QS 순위(`qs`), 파운데이션 기관(`fnd`), IYO 여부(`iyo`) | QS 발표(매년 6월) 및 기관 제휴 변경 시 |
| `majorData` | 석사 전공별 추천 대학 (순위·학비) | 매년 |
| 파운데이션·IYO 학비 안내 문구 | 학부 결과 경로 섹션 | 매년 |

### 알려진 미확정 항목 (상담 시 확인 문구로 처리됨)
- 요크·QMUL 석사 카드 2건: QS 2026 표기 유지 (2027 미검증)
- 더럼·랭커스터·글래스고 등 IYO 개설 여부: 학기별 변동 → 카드에 "상담 시 확인" 명시
- QS 2027 순위 출처: 러셀그룹 전체 + 세인트앤드루스(115)·바스(125)·엑서터(136)·뉴캐슬(149)·랭커스터(164) 개별 검증 완료 (2026.6.18 발표판)
