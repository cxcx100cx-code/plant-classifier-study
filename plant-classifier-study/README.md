# 식물분류기사 합격 트레이너

모바일 대응 정적 웹앱. 로컬에서 `index.html`을 열거나 정적 호스팅에 배포할 수 있습니다.

## 기능
- 실기형 종 동정 연습, 국명/학명/분류체계 문제 유형
- 문항별 정답 피드백 및 100점 환산 점수, 60점 합격 기준 표시
- 오답 노트와 브라우저 로컬 저장
- 종 데이터 검색 및 CSV/JSON 가져오기
- 큐넷/국가생물종목록 참고 링크

## 데이터 스키마
JSON 배열 또는 CSV 헤더에 `korean,scientific,family`는 필수. 추천 필드: `id,korean,scientific,kingdom,phylum,class,subclass,order,family,genus,species,image,source,sourceUrl,note,verified`.

CSV 가져오기는 단순 CSV 파서이므로 필드 안에 쉼표가 들어가는 CSV는 JSON 형식을 권장합니다. 외부에서 불러온 데이터는 자동으로 정답 검증되지 않으므로 `verified`와 출처를 확인해야 합니다.

## 현재 데이터 상태
`public/data/species.json`은 국가생물자원관 종 상세 페이지에서 분류정보가 확인되는 예시 3종만 포함합니다. 2026년 큐넷 공지에 따라 출제예상종은 400종이지만, 공식 PDF 전체 목록을 검증·대조해 넣기 전에는 400종 완성본이라고 표시하지 않습니다. 사진 URL은 임의로 만들지 않았습니다.

## Railway 배포
1. 프로젝트를 GitHub 저장소에 올립니다.
2. Railway에서 **New Project → Deploy from GitHub repo**를 선택합니다.
3. 정적 사이트 제공용 서비스로 연결하고, 필요하면 `npx serve . -l $PORT` 시작 명령을 설정합니다.
4. 공개 도메인을 생성합니다.

이 세션에서는 Railway 계정 인증이나 프로젝트에 접근할 수 없으므로 외부 배포 완료/공개 URL을 주장하지 않습니다.
