# 🍚 우리집 저녁 뭐 먹지?

가족이 한 표씩 저녁 메뉴를 투표하는 웹앱입니다. (Firebase 실시간 데이터베이스 사용)

## 설정 방법

1. **Firebase 콘솔** → 프로젝트 `dinner-9177d` → ⚙️ 프로젝트 설정 → 내 앱(웹)에서
   `firebaseConfig` 값을 복사해 `index.html`의 같은 부분에 붙여넣습니다.
   - `apiKey`는 `AIza`로 시작하는 **39자**입니다. 한 글자라도 빠지면 접속되지 않아요.
2. **Authentication** → 로그인 방법 → **익명(Anonymous)** 을 사용 설정합니다.
3. **Realtime Database** → 규칙 탭에 아래 규칙을 붙여넣고 게시합니다.

```json
{
  "rules": {
    "familyDinner": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

4. **Authentication → 설정 → 승인된 도메인**에 앱 주소를 추가합니다.
   (GitHub Pages라면 `hanasone16.github.io`)
5. `index.html`의 `ADMIN_PIN`을 가족끼리 정한 번호로 바꿉니다.

## 참고

- `ADMIN_PIN`은 화면 코드에 그대로 보이므로, 장난 방지용 정도로만 생각해 주세요.
- Firebase 웹 `apiKey`는 공개돼도 되는 값이지만, 위 보안 규칙은 꼭 적용해야 합니다.
