# 카카오톡 송금 낚시 카드 — 설치 가이드

## 무엇을 만들었나요?
- `index.html`: 내가 보는 송금 카드 미리보기 + 카카오톡 공유 버튼
- `receive.html`: JavaScript 키 없이 URL로 친구에게 보낼 때 보이는 송금 장난 카드
- `surprise.html`: 클릭한 친구가 볼 알파카 반전 화면
- `assets/card-hero.png`: 노란 송금 카드 이미지
- `assets/card-hero.svg`: 같은 카드의 편집 가능한 벡터 이미지

**주의:** 진짜 카카오페이의 송금 카드나 공식 카카오페이 로고/발신자 명칭을 만드는 기능이 아닙니다. 실제 송금은 이루어지지 않습니다. 카카오톡 공유 시 앱 이름, 카드 배치 등은 공식 피드 템플릿에 따라 달라집니다.

## 1. GitHub에 올리기 (무료)
1. https://github.com 에 회원가입/로그인합니다.
2. 오른쪽 위 `+` → `New repository`를 선택합니다.
3. 저장소 이름을 `kakao-prank`로 만들고 `Public`으로 설정합니다.
4. `Add file` → `Upload files`에서 **이 ZIP을 먼저 압축해제**한 뒤, `index.html`, `receive.html`, `surprise.html`과 **assets 폴더**를 한 번에 업로드합니다. `assets/card-hero.png` 경로가 유지되어야 합니다.
5. `Commit changes`를 누릅니다.
6. `Settings` → `Pages` → `Build and deployment` → `Source: Deploy from a branch`를 선택합니다.
7. 브랜치 `main`, 폴더 `/(root)`를 선택하고 `Save`를 누릅니다.
8. 페이지가 배포되면 `https://내아이디.github.io/kakao-prank/`처럼 주소가 생깁니다. **URL 마지막의 `kakao-prank/` 부분도 포함해서 접속**합니다.

## 2. 카카오디벨로퍼스 설정 (공유 카드에 버튼을 넣고 싶다면)
1. https://developers.kakao.com 에 카카오계정으로 로그인합니다.
2. `내 애플리케이션`에서 앱을 생성합니다. 앱 이름은 `장난 송금 카드`처럼 정합니다.
3. `앱` → `플랫폼 키` → `JavaScript 키`에서 키를 확인하고 복사합니다. **REST API 키, Admin 키가 아닙니다.**
4. 그 JavaScript 키의 `JavaScript SDK 도메인`에 `https://내아이디.github.io`를 추가합니다.
5. `앱` → `제품 링크 관리` → `웹 도메인`에도 `https://내아이디.github.io`를 추가합니다.
6. (중요) `https://내아이디.github.io/kakao-prank/`에서 사이트를 연 다음, JavaScript 키를 입력하고 `카카오톡으로 보내기`를 누릅니다.
7. 카카오톡에서 친구 또는 채팅방을 선택하여 공유합니다.

설정 메뉴가 다르게 보일 경우, 카카오 공식 가이드 확인: https://developers.kakao.com/docs/ko/tutorial/js-share

## 3. JavaScript 키 없이 먼저 해보고 싶다면
1. 배포된 사이트 주소를 열고 `장난용 링크 복사`를 누릅니다.
2. 복사한 주소를 카카오톡 대화방에 붙여넣습니다.
3. 친구가 링크를 누르면 `receive.html`의 노란 카드가 열립니다.
4. 거기서 `송금 받기`를 누르면 알파카 반전 화면이 나옵니다.

이 방식은 일반 웹 링크/링크 미리보기이고, 공유 카드 안에 실제 카카오톡 버튼이 생기는 방식은 아닙니다.

## 4. 금액 변경
`index.html`의 '표시할 금액' 칸에서 바꾸면 됩니다. 노란 이미지 위에는 금액이 적혀 있지 않아 이미지를 수정하지 않아도 됩니다.

## 오류가 나면?
- GitHub Pages 404: 저장소 이름, Pages 활성화, `index.html` 루트 위치, 배포 완료 여부를 확인합니다.
- 이미지가 안 나옴: `assets/card-hero.png` 파일 경로가 정확한지 확인합니다.
- 카카오 공유가 실행되지 않음: JavaScript 키와 JavaScript SDK 도메인 + 제품 링크 웹 도메인을 확인합니다.
- 사이트를 로컬 파일(`file://`)로 열면 카카오 공유 기능은 작동하지 않습니다. GitHub Pages의 **HTTPS 웹 주소**에서 테스트해야 합니다.
- 카카오의 심사, 정책, UI 및 계정 설정에 따라 공유 방식이 제한되거나 변경될 수 있습니다.

## 개인정보와 주의사항
이 예시는 서버, 데이터베이스, 위치 추적, 개인정보 수집, 실제 결제 기능이 없습니다. JavaScript 키는 브라우저 localStorage에 저장되며 입력된 **공개용** 키만 사용합니다. 송금이 이루어진 것처럼 속여 실제 돈이나 계좌·인증 정보를 요구하는 용도로 사용해서는 안 됩니다.
