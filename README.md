### 메타데이터 플러그인 (imkun85 패치)

[flaskfarm/metadata](https://github.com/flaskfarm/metadata)를 포크해서 버그 하나를 고친 버전이다.

버전은 `1.3.9-imkun85`이고, 본가 `1.3.9`를 기반으로 한다.

수정한 파일은 `mod_ktv.py` 하나다.

티빙(tving) `info` 모드에서 회차 정보가 없는 프로그램은 `SupportTving.get_frequency_programid()`가 `None`을 반환하는데, 이때 `episode_data['result']`에 그대로 접근해 `TypeError: 'NoneType' object is not subscriptable` 에러로 ktv 검색 전체가 죽었다.

그래서 티빙 검색 자체는 정상인데도 Plex(`sjva_agent_ktv`)에서 "일치하는 항목 없음"으로 떴다.

`episode_data['result']`를 순회하기 전에 `None` / `result` 키 체크를 추가해서 해결했다.

## Changelog
- 1.3.9 (2026.09.11) by golmog
    - 커스텀 비디오 지문(Fingerprints) 테이블 추가
    - DB 처리 로직/속도 개선
<br><br>
- 1.3.8 (2026.09.09) by golmog
    - 메타 DB 모듈 PostgreSQL 연동 수정/확인
    - Preview Video Clip 생성 기능 추가(AV)
<br><br>
- 1.3.7 (2026.09.03) by golmog
    - 로컬 메타데이터 DB 도입
<br><br>
- 1.2.6 (2025.07.30) by soju6jan
    - avdbs censored 모듈에서 찾도록 수정
<br><br>
- 1.2.5 (2025.07.27) by soju6jan
    - 이미지서버 rewrite 옵션추가.
<br><br>
- 1.2.4 (2025.07.27) by soju6jan
    - jav censored / uncensored.
<br><br>  
- 1.2.3 (2025.07.11)   
  jav censored 준비
<br><br>
- 1.1.7 (2025.06.29)   
  버전 수정
<br><br>
- 1.1.6p5 (2025.05.02)
    - 다음 TV 정보 개편 대응
    - 다음 영화 일부 복구
    - 리뷰 source 기본값 설정
<br><br>
- 1.1.6 (2024.09.23)   
  minor fix.
<br><br>
- 1.1.5 (2024.09.05)   
  tmdb 등급 가져오지 않는 문제 수정. 부가영상 처리 삭제.
<br><br>
- 1.1.4 (2024.08.21)   
  영화 daum, naver 제거.
<br><br>
- 1.1.2 (2024.07.11)   
  KTV Daum 소개 사용.
<br><br>
- 1.1.1 (2024.06.11)    
  KTV 왓챠피디아 추가.
<br><br>
- 1.1.0 (2024.06.01)
    - plex에서 이모지를 지원하지 않아 extra에서 제거하여 보내도록 수정    
    예: 용감한 형사들
