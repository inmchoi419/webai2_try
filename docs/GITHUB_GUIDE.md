# GitHub 사용 가이드

GitHub와 Git을 처음 사용하는 분들을 위한 기본 사용법 문서입니다.

---

## 1. GitHub란?

- **Git**: 코드의 변경 이력을 관리하는 버전 관리 시스템(도구)
- **GitHub**: Git 저장소를 온라인에서 관리하고 협업할 수 있게 해주는 웹 서비스

> 쉽게 말해, Git은 내 컴퓨터에서 버전을 관리하는 도구이고, GitHub는 그 결과물을 인터넷에 올려 공유·협업하는 공간입니다.

---

## 2. 기본 용어

| 용어 | 설명 |
|------|------|
| Repository (저장소) | 프로젝트 파일과 변경 이력이 담기는 공간 |
| Commit (커밋) | 변경 사항을 기록하는 하나의 저장 단위 |
| Branch (브랜치) | 독립적으로 작업할 수 있는 분기 (예: `main`, `feature/login`) |
| Push (푸시) | 로컬 커밋을 원격(GitHub)으로 업로드 |
| Pull (풀) | 원격의 변경 사항을 로컬로 내려받기 |
| Clone (클론) | 원격 저장소를 통째로 복제해 로컬에 가져오기 |
| Pull Request (PR) | 내 브랜치의 변경을 다른 브랜치에 병합해달라고 요청 |
| Merge (머지) | 브랜치의 변경 사항을 합치기 |

---

## 3. 처음 시작하기

### 3.1 Git 설치 확인

```bash
git --version
```

### 3.2 사용자 정보 설정 (최초 1회)

```bash
git config --global user.name "이름"
git config --global user.email "이메일@example.com"
```

### 3.3 저장소 가져오기 (Clone)

```bash
git clone https://github.com/inmchoi419/webai2_try.git
cd webai2_try
```

---

## 4. 기본 작업 흐름

가장 많이 쓰는 기본 흐름입니다.

```bash
# 1. 현재 상태 확인
git status

# 2. 변경한 파일을 스테이징(기록 대상에 추가)
git add 파일명
# 모든 변경을 추가하려면
git add .

# 3. 커밋(변경 기록 저장) - 메시지는 무엇을 왜 바꿨는지 적기
git commit -m "로그인 기능 추가"

# 4. 원격(GitHub)으로 업로드
git push origin 브랜치명
```

---

## 5. 브랜치 사용

여러 작업을 안전하게 나눠서 하기 위해 브랜치를 사용합니다.

```bash
# 새 브랜치 만들고 이동
git checkout -b feature/login

# 브랜치 목록 보기
git branch

# 다른 브랜치로 이동
git checkout main

# 최신 변경 내려받기
git pull origin main
```

---

## 6. Pull Request (PR) 만들기

1. 작업 브랜치를 GitHub에 푸시합니다.
   ```bash
   git push origin feature/login
   ```
2. GitHub 저장소 페이지에 접속하면 **"Compare & pull request"** 버튼이 나타납니다.
3. 버튼을 눌러 제목과 설명을 작성합니다.
   - 무엇을 바꿨는지
   - 왜 바꿨는지
   - 확인이 필요한 부분
4. **"Create pull request"**를 클릭합니다.
5. 리뷰 후 문제가 없으면 **"Merge"**로 병합합니다.

---

## 7. 자주 쓰는 명령어 요약

| 명령어 | 설명 |
|--------|------|
| `git status` | 현재 변경 상태 확인 |
| `git add .` | 모든 변경 스테이징 |
| `git commit -m "메시지"` | 커밋 |
| `git push origin 브랜치` | 원격에 업로드 |
| `git pull origin 브랜치` | 원격 변경 내려받기 |
| `git log --oneline` | 커밋 이력 간단히 보기 |
| `git checkout -b 이름` | 새 브랜치 생성 및 이동 |
| `git diff` | 변경 내용 비교 |

---

## 8. 좋은 커밋 메시지 작성 팁

- 한 커밋에는 하나의 목적만 담기
- 명확하고 간결하게: `버그 수정: 로그인 시 널 포인터 오류 해결`
- 무엇을 했는지 + 필요하면 왜 했는지 함께 작성

---

## 9. 문제 해결

**푸시가 거부될 때 (원격에 새 변경이 있음)**
```bash
git pull origin 브랜치명   # 먼저 최신 변경을 받고
git push origin 브랜치명   # 다시 푸시
```

**직전 커밋 메시지 수정**
```bash
git commit --amend -m "새 메시지"
```

**변경 사항 되돌리기 (커밋 전, 주의)**
```bash
git checkout -- 파일명
```

---

## 참고 링크

- GitHub 공식 문서: https://docs.github.com
- Git 공식 문서: https://git-scm.com/doc
