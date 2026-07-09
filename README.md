# 익명 기술 블로그

이력서와 포트폴리오의 경험을 바탕으로 만든 정적 기술 블로그입니다. 별도 빌드 없이 GitHub Pages에 바로 배포할 수 있습니다.

## 배포

1. GitHub에서 `<username>.github.io` 저장소를 만듭니다.
2. 이 폴더 안의 파일을 저장소 최상위에 올립니다.
3. `Settings → Pages → Build and deployment`에서 `GitHub Actions`를 선택합니다.
4. `main` 브랜치에 push하면 자동 배포됩니다.

사용자 사이트가 아닌 프로젝트 저장소에 올려도 동작합니다. 모든 내부 경로가 상대 경로로 되어 있습니다.

## 사진 넣기

현재 회색 대각선 영역은 사진 자리입니다. 사진을 넣으려면 해당 HTML의 `.photo-slot`을 아래처럼 바꿉니다.

```html
<div class="photo-slot">
  <img src="./assets/images/profile.jpg" alt="익명 프로필 이미지">
</div>
```

글 상세 페이지에서는 이미지 경로 앞에 `../`를 붙입니다.

```html
<div class="photo-slot small">
  <img src="../assets/images/k6-before-after.png" alt="k6 성능 테스트 전후 결과">
</div>
```

권장 파일:

- `assets/images/profile.jpg` - 익명 프로필 또는 작업 이미지, 세로 4:5
- `assets/images/about.jpg` - 작업 모습, 가로 3:2
- `assets/images/k6-before-after.png` - 성능 개선 그래프, 가로 16:9
- `assets/images/aws-parameter-store.png` - AWS 구성 또는 실행 화면
- `assets/images/monitoring-dashboard.png` - Grafana 대시보드
- `assets/images/route-service.png` - 등불 서비스 화면 또는 경로 지도

## 개인정보

이름, 생년월일, 전화번호, 이메일, 지역과 개인 프로필 링크는 공개 사이트에서 제외했습니다.

## 새 글 추가

1. `posts/`의 기존 글을 복사합니다.
2. 제목, 설명, 본문을 수정합니다.
3. `index.html`의 `.post-list` 안에 새 글 카드를 추가합니다.

## 로컬 미리보기

```powershell
python -m http.server 8000
```

브라우저에서 `http://localhost:8000`을 엽니다.
