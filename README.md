1. 프로젝트 개요 (Project Overview)

대상: 메이플 키우기 (방치형 RPG)

목적: 신규 기능 출시 전 핵심 로직 검증 및 사용자 잔존율(Retention)에 영향을 주는 크리티컬 결함 조기 발견.

2. 테스트 전략 및 방법론 (Test Strategy)

방법론: 리스크 기반 테스팅 (Risk-based Testing)

접근 방식: 블랙박스 테스팅 위주, 탐색적 테스팅 병행을 통한 엣지 케이스 발굴.

3. 테스트 범위 (Test Scope)

In-Scope: 캐릭터 성장, 장비 강화, 던전 입장 로직, 인앱 결제 프로세스.

Out-of-Scope: 서버 부하 테스트(Performance), 호환성(저사양 기기 제외).

4. 상세 테스트 환경 (Test Environment)

항목                                               사양 / 버전

OS                                             Android 13 (One UI 5.1), iOS 16.5

Devices                                        Galaxy S23 Ultra, iPhone 14 Pro

Network                                        Wi-Fi 6, 5G, LTE (네트워크 전환 테스트 포함)

Tool                                           ADB(Logcat), Charles Proxy (패킷 확인)

5. 적용 테스트 기법 (Test Design Techniques)

경계값 분석 (BVA): 레벨업 필요 경험치 경계 확인.

동등 분할 (EP): 아이템 등급별 강화 성공 확률 그룹화.

상태 전이 테스팅: 전투 -> 사망 -> 부활 -> 마을 이동 프로세스 검증.

6. 테스트 일정 및 공정 (Test Schedule)

분석/설계: 2024.0X.01 ~ 05 (TC 작성)

테스트 수행: 2024.0X.06 ~ 15 (1차/2차 수행)

결함 수정 확인: 2024.0X.16 ~ 18 (Retest)

7. 결함 관리 정책 (Defect Policy)

Severity(심각도): Critical(앱 크래시), Major(기능 미작동), Normal(UI/텍스트)

Priority(우선순위): P0(즉시 수정), P1(차기 빌드 수정), P2(여유 시 수정)

8. 테스트 결과 요약 (Metrics)

총 수행 TC: 150건

Pass Rate: 92% (138건 Pass / 12건 Fail)

결함 발견: 총 12건 (Critical 2, Major 5, Minor 5)

9. 리스크 및 이슈 관리 (Risks & Issues)

Risk: 테스트 기간 중 서버 점검으로 인한 테스트 중단 발생.

Mitigation: 로컬 빌드를 활용하여 UI/UX 테스트를 먼저 진행하여 가동률 확보.

10. 회고 및 개선 방향 (Retrospective)

성과: 가차 확률 로직에서 기획서와 0.1% 오차 발견 및 수정 기여.

성장: 단순 기능 체크를 넘어 로그 분석(ADB)을 통한 원인 파악 능력 배양.
