# 청렴 신고 사건 조회 - Netlify 배포

- `index.html`: 사건 카드, 신고유형·처리상태 필터, 지역·사건 ID 검색, 결과 건수
- `data/cases.json`: 첨부 CSV의 500건 JSON 변환본
- `data/rss-snapshot.json`: RSS 프록시 실패 시 표시하는 예비 목록
- `netlify/functions/rss.js`: 행정안전부 보도자료 RSS 프록시

## 배포 방법
1. ZIP 압축을 풀고 폴더 안 파일을 GitHub 저장소에 업로드합니다.
2. Netlify에서 Add new site → Import an existing project를 선택하고 저장소를 연결합니다.
3. Build command는 비워 두고 Publish directory는 `.`로 설정한 뒤 배포합니다.
4. 배포 URL에서 필터와 보도자료 링크를 확인합니다.

RSS 원본: https://www.mois.go.kr/gpms/view/jsp/rss/rss.jsp?ctxCd=1012
로컬 파일로 직접 열면 Netlify Functions 대신 저장된 스냅샷이 표시됩니다. 스냅샷은 최신성을 유지하려면 갱신해야 합니다. 사건 데이터는 제공 파일 기반이며 공식 사건조회 시스템이 아닙니다.
