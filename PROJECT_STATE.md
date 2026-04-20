# Dino Lex - 프로젝트 상태 보고서 (2026-04-20)

본 문서는 현재 진행 중인 **초등학생 영단어 암기 프로젝트(Dino Lex)**의 개발 상태를 요약한 보고서입니다.

## 1. 프로젝트 개요
- **목표**: 초등학생들이 재미있게 영단어를 외울 수 있도록 돕는 타이핑 기반의 디펜스/학습 게임.
- **핵심 철학**: 즉각적인 시각적/청각적 피드백, 챕터별 단계적 학습, 디바이스 최적화(PC/Tablet/Mobile).

## 2. 주요 기능 및 특징
- **게임 시스템**:
    - 챕터(Chapter) 선택 시스템: 총 10개 이상의 챕터로 구성된 단어 데이터 로드.
    - 900x900 대형 캔버스 기반의 게임 환경.
    - 콤보(Combo) 시스템 및 성공/실패 애니메이션 효과.
- **타이핑 엔진**:
    - **Hangul Automata**: 한국어 뜻 입력 시 자음/모음 조합을 실시간으로 처리하는 한글 오토마타 엔진 내장.
    - **실시간 피드백**: 타이핑 중인 글자의 정확도를 색상으로 표시(Correct: Blue, Current: Pink, Error: Red).
- **사운드 시스템 (Retro Audio)**:
    - Web Audio API를 활용한 레트로 스타일 사운드 생성(Arpeggio, Square/Sawtooth waveforms).
    - 배경음악(BGM) 엔진: 메뉴, 게임, 승리 등 상황별 시퀀스 재생.
- **다중 플랫폼 지원**:
    - 접속 UA(User Agent)를 감지하여 `index.html`(PC), `tablet.html`, `mobile.html`로 자동 리다이렉션.

## 3. 파일 구조 및 역할
- **[index.html](file:///d:/ag_coding_ex/amgibaksa/typinggame01/index.html)**: PC 버전 메인 게임 로직, UI, 한글 오토마타 및 사운드 엔진 포함.
- **[words01.json](file:///d:/ag_coding_ex/amgibaksa/typinggame01/words01.json)**: 전체 단어 데이터베이스(의미, 챕터 정보).
- **[mobile.html](file:///d:/ag_coding_ex/amgibaksa/typinggame01/mobile.html) / [tablet.html](file:///d:/ag_coding_ex/amgibaksa/typinggame01/tablet.html)**: 모바일 및 태블릿 환경에 최적화된 개별 레이아웃.
- **resource/**: 게임에 필요한 외부 에셋(이미지, 사운드 등) 저장 폴더.

## 4. 기술 명세 (Technical Notes)
- **State Management**: `WORD_DATABASE`와 `CONFIG` 객체를 통해 게임 설정 및 데이터를 전역적으로 관리.
- **Rendering**: 캔버스(`game-canvas`)를 사용하여 실시간 게임 오브젝트(적, 총알 등) 렌더링.
- **Fallback Data**: CORS 이슈 등을 방지하기 위해 `EMBEDDED_WORD_DATA`를 `index.html` 내부에 상수로 보유.

## 5. 향후 To-Do 리스트
- [ ] 챕터별 난이도 밸런싱 (적 이동 속도, 스폰 주기 조정).
- [ ] 모바일 버전의 입력 UI 개선 (가상 키보드 최적화).
- [ ] 학습 통계 대시보드 (오타가 잦은 단어 복습 기능) 추가.
- [ ] 캔버스 그래픽 에셋(디노 캐릭터 등) 고도화.

---
**업데이트 일시**: 2026-04-20
**작성자**: AI Antigravity (교정됨)
