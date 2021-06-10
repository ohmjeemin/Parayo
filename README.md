### 코틀린으로 안드로이드 쇼핑몰 앱 만들기 (210611~)

---

##### Activity

- Activity는 안드로이드 애플리케이션을 구성하는 화면 단위의 컴포넌트
- 화면에 보여지기 위해서 View 를 포함해야 하며 애플리케이션의 구성요소로 취급되기 위해서는 **Manifest** 파일에 등록되어야 한다.

##### AndroidManifest 수정하기

- API를 사용하는 등의 네트워크 요청을 위해 INTERNET 권한을 명시해주기

  `<users-permission android:name="android.permission.INTERNET"/>`

  



