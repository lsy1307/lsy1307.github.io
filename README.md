# lsy1307 기술 블로그

실제 프로젝트 구현과 기술 회고를 기록하는 정적 기술 블로그입니다. 별도 빌드 과정 없이 GitHub Pages에서 배포합니다.

## 배포

1. GitHub에서 `<username>.github.io` 저장소를 만듭니다.
2. 이 폴더 안의 파일을 저장소 최상위에 올립니다.
3. `Settings → Pages → Build and deployment`에서 `Deploy from a branch`를 선택합니다.
4. `main` 브랜치의 `/ (root)`를 배포 대상으로 지정합니다.

내부 링크와 자산 경로는 상대 경로를 사용합니다. 프로젝트 저장소의 Pages 경로에서 재사용할 때는 canonical·Open Graph URL을 해당 배포 주소로 바꿔야 합니다.

## 글의 상태 표시

프로젝트 글은 다음 상태를 구분해 표시합니다.

- `IMPLEMENTED`: 공개 코드에서 확인 가능한 구현
- `IMPLEMENTED WITH LIMITS`: 적용했지만 보장하지 못한 실패 구간이나 운영 과제가 있는 구현
- `RETROSPECTIVE`: 과거 구현을 다시 분석한 글
- `PROPOSED DESIGN`: 아직 공개 `main`에 적용하지 않은 목표 설계
- `MEASUREMENT PENDING`: 구조는 적용했지만 최적값을 비교 측정하지 않은 내용

회고에서 제안한 구조를 완료된 성과처럼 쓰지 않습니다. 수치를 제시할 때는 측정 환경·부하 조건·데이터 규모·오류율을 함께 남기는 것을 원칙으로 합니다.

## 사진 넣기

이미지를 추가할 때는 페이지 깊이에 맞는 상대 경로와 내용을 설명하는 대체 텍스트를 함께 사용합니다.

```html
<div class="photo-slot">
  <img src="./assets/images/article-image.png" alt="기술 글 설명 이미지">
</div>
```

글 상세 페이지에서는 이미지 경로 앞에 `../`를 붙입니다.

```html
<div class="photo-slot small">
  <img src="../assets/images/k6-before-after.png" alt="k6 성능 테스트 전후 결과">
</div>
```

현재 주요 파일:

- `assets/images/backend-workspace.webp` - 작업 환경 이미지
- `assets/images/k6-before-after.png` - 성능 개선 그래프, 가로 16:9
- `assets/images/loadtest-lifecycle.svg` - 부하 테스트 환경 수명주기
- `assets/images/terraform-modules.svg` - Terraform root와 module 경계
- `assets/images/s3-compensation-matrix.svg` - 실패 지점별 보상 범위
- `assets/images/safe-route-overview.svg` - CCTV 가중 경로 계산 개요

## 개인정보

GitHub 주소를 제외한 이름, 생년월일, 전화번호, 이메일과 지역 정보는 공개 사이트에서 제외했습니다.

## 새 글 추가

1. `posts/`의 기존 글을 복사합니다.
2. 제목, 설명, 본문을 수정합니다.
3. `index.html`의 `.post-list` 안에 새 글 카드를 추가합니다.
4. 구현 상태, 기준 버전, 관련 PR·commit과 남은 한계를 본문에 표시합니다.

## Java Spring 공부 노트

Java, JVM, Spring, JPA 공부 노트는 `spring-study.html`에서 관리합니다.
개별 노트는 `study/` 폴더에 둡니다.

## 로컬 미리보기

```powershell
python -m http.server 8000
```

브라우저에서 `http://localhost:8000`을 엽니다.

배포 전에 다음을 확인합니다.

- 내부 HTML 링크와 이미지 경로가 실제 파일을 가리키는지
- 모든 HTML에 `<title>`, description, viewport가 있는지
- 프로젝트 글이 구현·회고·설계안을 정확히 구분하는지
- 공개 코드에 없는 기능을 완료형으로 서술하지 않았는지
- 민감한 계정, 토큰, 운영 데이터가 예시와 이미지에 포함되지 않았는지
