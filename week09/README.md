# week09

## 무엇을 하는 코드인가

영화진흥위원회(KOBIS) 오픈 API로 일별 박스오피스를 조회합니다. `tools_nodoc.py`에 함수 두 개가 있습니다.

- `get_boxoffice_rank_1(date)`: 그날 1위 영화의 제목을 돌려줍니다.
- `get_movie_audience(date, title)`: 그날 해당 영화의 관객 수(예: `"123,456명"`)를 돌려줍니다. 순위에 없는 영화면 안내 문장을 돌려줍니다.

## 무엇을 설치해야 하나

```bash
pip install requests
```

KOBIS 오픈 API 키도 있어야 합니다. 같은 폴더에 `secret.py`를 만들고 키를 넣으세요.

```python
API_KEY = "발급받은_키"
```

## 어떻게 실행하나

`week09` 폴더에서 다음을 실행합니다. 날짜는 `YYYYMMDD` 형식입니다.

```bash
python -c "from tools_nodoc import *; print(get_boxoffice_rank_1('20261103'))"
python -c "from tools_nodoc import *; print(get_movie_audience('20261103', '영화제목'))"
```
