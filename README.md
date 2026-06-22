### 메타데이터 플러그인 (imkun85 패치)

[flaskfarm/metadata](https://github.com/flaskfarm/metadata)를 포크해서 버그 하나를 고친 버전이다.

버전은 `1.2.6-imkun85`이고, 본가 `1.2.6`을 기반으로 한다.

수정한 파일은 `mod_ktv.py` 하나다.

티빙(tving) `info` 모드에서 회차 정보가 없는 프로그램은 `SupportTving.get_frequency_programid()`가 `None`을 반환하는데, 이때 `episode_data['result']`에 그대로 접근해 `TypeError: 'NoneType' object is not subscriptable` 에러로 ktv 검색 전체가 죽었다.

그래서 티빙 검색 자체는 정상인데도 Plex(`sjva_agent_ktv`)에서 "일치하는 항목 없음"으로 떴다.

`episode_data['result']`를 순회하기 전에 `None` / `result` 키 체크를 추가해서 해결했다.
