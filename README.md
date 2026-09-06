# 등불 · 성경과 찬송

말씀을 읽고 찬송을 부르는 공간 — 별도 서버나 빌드 과정 없이 정적 HTML 한 장으로 동작하는 웹앱입니다.

## 폴더 구성
```
lamp-app/
├─ index.html          # 앱 전체 (HTML+CSS+JS, 성경 본문 데이터 포함)
├─ favicon.svg          # 앱 아이콘 (SVG)
├─ favicon-32.png       # 파비콘 (32x32)
├─ favicon-192.png      # 아이콘 (192x192, PWA/매니페스트용)
├─ favicon-512.png      # 아이콘 (512x512, PWA/매니페스트용)
├─ apple-touch-icon.png # iOS 홈 화면 아이콘 (180x180)
├─ manifest.json        # 웹앱 매니페스트 (홈 화면에 추가 시 아이콘/이름 지정)
└─ vercel.json          # Vercel 배포 설정 (정적 사이트, 별도 빌드 불필요)
```

## GitHub에 올리기
1. GitHub에서 새 저장소를 만듭니다 (예: `lamp-app`).
2. 이 zip 파일의 압축을 풀고, 그 폴더에서 아래 명령을 실행합니다.
   ```bash
   git init
   git add .
   git commit -m "첫 커밋: 등불 성경 앱"
   git branch -M main
   git remote add origin https://github.com/사용자명/lamp-app.git
   git push -u origin main
   ```

## Vercel로 배포하기
1. https://vercel.com 에 로그인 후 **Add New → Project**를 클릭합니다.
2. 방금 올린 GitHub 저장소(`lamp-app`)를 선택해서 Import 합니다.
3. Framework Preset은 **Other**로 두면 됩니다 (별도 빌드 명령이 필요 없는 정적 사이트입니다).
   - Build Command: 비워둠
   - Output Directory: 비워둠 (루트의 `index.html`을 그대로 서빙)
4. **Deploy**를 누르면 몇 초 안에 `https://lamp-app-사용자명.vercel.app` 같은 주소로 배포됩니다.
5. 이후 GitHub 저장소에 새로 커밋/푸시할 때마다 Vercel이 자동으로 재배포합니다.

## 참고
- 한국어 성경 본문은 저작권이 만료된 1911년 초역 성경, 영어 본문은 King James Version(공개 저작물)을 사용했습니다.
- 찬송은 원곡 저작권이 만료된(1923년 이전) 고전 찬송 10곡을 담았습니다.
- 사용자 데이터(글자 크기, 책갈피, 읽기 기록)는 브라우저의 localStorage에만 저장되며 외부로 전송되지 않습니다.
