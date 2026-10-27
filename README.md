# GRAND PRIX 2026 — CWNU Industrial Design Archive

국립창원대학교 산업디자인학과 제36회 졸업전시 온라인 아카이브.

## GitHub Pages 배포
1. 이 폴더 안의 파일 전체를 저장소 루트에 업로드 (index.html이 루트에 있어야 함)
2. Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `/ (root)` → Save
3. 1–2분 후 `https://<아이디>.github.io/<저장소명>/` 에서 확인

## 구조
- `index.html` — 사이트 전체 (Main / About / Work / Designers / 작품 상세)
- `support.js`, `image-slot.js` — 실행에 필요한 스크립트 (삭제 금지)
- `assets/` — 봉투 종이 질감, 디자이너 프로필 사진
- `.nojekyll` — GitHub Pages 처리 방지용 빈 파일 (삭제 금지)


## 작품 상세페이지 편집 (works.json)

각 학생의 상세페이지 내용은 `works.json`에서 학생별 블록 목록으로 정합니다. **블록을 적은 순서대로 화면에 나오므로**, 블록을 위아래로 옮기거나 지우거나 추가해서 순서를 자유롭게 바꿀 수 있습니다.

이미지는 화면 폭에 맞춰지고 세로는 원본 비율을 따르기 때문에 잘리지 않습니다. 파일은 `assets/works/<학생 slug>/`에 올립니다. 파일이 아직 없으면 회색 자리 표시와 함께 경로가 보입니다.

| type | 쓰는 법 |
|---|---|
| section | `{ "type": "section", "label": "Background" }` — 소제목 (번호 자동) |
| text | `{ "type": "text", "title": "제목(선택)", "body": "본문", "align": "center"(선택), "size": "large"(선택) }` |
| image | `{ "type": "image", "src": "assets/works/slug/01.jpg", "full": true(선택, 화면 끝까지), "caption": "(선택)" }` |
| images | `{ "type": "images", "items": [ { "src": "…a.jpg" }, { "src": "…b.jpg" } ] }` — 2~3장 나란히 (모바일은 1열) |
| video | `{ "type": "video", "src": "assets/works/slug/intro.mp4" }` 또는 `{ "type": "video", "youtube": "영상주소" }` / `"vimeo": "영상주소"`. 자동재생 루프는 `"autoplay": true` |

* 쉼표·따옴표가 하나라도 틀리면 그 파일 전체가 무시되고 기본 템플릿이 나옵니다. jsonlint.com에서 검사 후 올리세요.
* 영상 파일은 GitHub 제한(100MB) 때문에 가능하면 YouTube/Vimeo를 권장합니다.
