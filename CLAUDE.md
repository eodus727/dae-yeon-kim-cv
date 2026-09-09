# CV_DYK.tex 작업 가이드

이 저장소는 김대연 교수님의 학술 CV(LaTeX, RenderCV 스타일 템플릿)를 관리함.
CV_DYK.tex를 수정해서 push하면 GitHub Actions가 자동으로 CV_DYK.pdf를 재생성해서 같은 저장소에 커밋함.
그 PDF는 raw.githubusercontent.com 링크로 구글 사이트 CV 탭에 걸려 있으므로 파일명과 경로는 절대 바꾸지 말 것.

## 새 항목 추가할 때 지켜야 할 규칙

### PUBLICATIONS
- `\subsection{Peer-reviewed Journal Articles}` 안의 각 항목은 `\begin{pubitem}{번호.}{내용}` 형식
- 번호는 최신 논문이 가장 큰 숫자, 맨 위가 최신, 아래로 갈수록 오래된 논문 (내림차순)
- 새 논문이 게재 확정되면 가장 큰 번호를 새로 부여하고 맨 위에 삽입
- 저자 중 Dae Yeon Kim 본인은 `\textbf{\underline{...}}`로 강조
- equal contribution은 이름 뒤에 `*`, co-corresponding은 `\ensuremath{^{\dagger}}`
- 항목 사이 간격은 `\vspace{0.3em}`
- `\subsection{Submitted/in-progress}`는 별도의 독립적인 번호 체계(1번부터), 게재 확정되면 여기서 빼고 Peer-reviewed 쪽으로 정식 서지정보(권/호/페이지/DOI)와 함께 옮길 것

### PRESENTATIONS
- International Conference, Others 두 하위 섹션 각각 번호 내림차순(최신이 위, 가장 큰 번호)
- 학회명에 적힌 연도와 실제 개최 날짜가 다른 경우가 있음(코로나 등으로 연기됨). 이런 불일치는 오류가 아니므로 임의로 고치지 말고, 명백한 오타로 보이는 경우만 사용자에게 확인 후 수정

### TEACHING AND MENTORING / AWARDS AND HONORS / OTHER ACTIVITIES / REFERENCES
- `threecolentrywide`, `threecolentryref`, `threecolentryteach` 등은 컬럼 폭만 다름, 내용 길이에 맞는 것 선택
- 최신 항목이 위로 오도록 정렬

## 절대 건드리면 안 되는 것
- 파일 상단 `\newenvironment` 정의 등 스타일 관련 preamble
- 주석 처리된 블록(후보 레퍼런스, Lab manager 등)은 삭제하지 말고 그대로 둘 것, 사용자가 명시적으로 지우라고 할 때만 제거
- `\placelastupdatedtext` 관련 코드는 현재 미사용 상태, 별도 지시 없으면 그대로 둠

## 새 내용 추가 시 진행 순서
1. 요청받은 내용을 위 규칙에 맞게 적절한 섹션, 적절한 위치에 삽입
2. 로컬에 LaTeX 배포판이 있으면 pdflatex를 2회 돌려서 참조나 페이지 번호가 깨지지 않는지 확인 (없으면 생략, 최종 컴파일은 GitHub Actions가 담당)
3. git commit 후 push
