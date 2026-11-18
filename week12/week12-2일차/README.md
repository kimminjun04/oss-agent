# boxoffice — KOBIS 박스오피스 조회 스킬

## 하는 일
영화진흥위원회(KOBIS) 일별 박스오피스 API를 호출하여, 특정 날짜(8자리 YYYYMMDD)의 박스오피스 1위 영화 제목이나 특정 영화의 관객 수를 조회해 알려준다.

## 들어 있는 파일
- `.claude/skills/boxoffice/SKILL.md`: 스킬의 이름, 설명, 사용법 및 주의사항을 담은 지시문
- `.claude/skills/boxoffice/scripts/boxoffice.py`: `tools.py`의 함수를 명령줄 인자(`rank`, `audience`)로 실행하는 스크립트
- `.claude/skills/boxoffice/LICENSE`: 스킬의 라이선스 파일 (MIT License)
- `tools.py`: KOBIS OpenAPI에 실제로 HTTP GET 요청을 보내는 파이썬 함수 모음

## 필요한 것
- Python 3 및 `requests` 패키지 (`pip install requests`)
- `week12` 폴더 위치의 `tools.py`와 본인의 KOBIS API 키가 담긴 `secret.py` 파일

## 설치
1. 프로젝트 폴더 아래에 `.claude/skills/boxoffice` 폴더가 위치하도록 복사한다.
2. 가상환경을 활성화하고 `pip install requests`로 필요한 패키지를 설치한다.
3. 프로젝트 폴더(`week12`)에 `secret.py`를 만들고 본인의 키를 넣는다.

## 바깥으로 요청하는 곳
- `https://www.kobis.or.kr/kobisopenapi/webservice/rest/boxoffice/searchDailyBoxOfficeList.json` (영화진흥위원회 KOBIS 일별 박스오피스 OpenAPI)
- 쿼리 파라미터로 API 키(`key`)와 조회할 8자리 날짜(`targetDt`)만 전송한다.

## 키
- 스킬 폴더나 저장소에는 API 키가 포함되어 있지 않다.
- 사용자는 직접 영화진흥위원회(KOBIS)에서 키를 발급받아 `week12/secret.py` 파일에 `API_KEY = "자기_발급_키"` 형태로 넣어야 한다.

## 권한
- `SKILL.md`에 `allowed-tools` 같은 자동 권한 확장 설정을 쓰지 않는다.
- Manual 모드에서 사용할 때 `python .claude/skills/boxoffice/scripts/boxoffice.py ...` 명령 실행 전 사용자에게 승인(권한 요청)을 묻는다.

## 라이선스
- MIT License (자세한 조건은 `.claude/skills/boxoffice/LICENSE` 파일 참고)