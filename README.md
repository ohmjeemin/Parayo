### 코틀린으로 안드로이드 쇼핑몰 앱 만들기 (210611~)

---

##### Activity

- Activity는 안드로이드 애플리케이션을 구성하는 화면 단위의 컴포넌트
- 화면에 보여지기 위해서 **View** 를 포함해야 하며 애플리케이션의 구성요소로 취급되기 위해서는 **Manifest** 파일에 등록되어야 한다.

##### AndroidManifest 수정

- API를 사용하는 등의 네트워크 요청을 위해 INTERNET 권한을 명시해줘야 한다.

  `<users-permission android:name="android.permission.INTERNET"/>`

##### Anko 라이브러리 추가

- 코틀린 DSL로 뷰를 만들기 위해 Anko라는 라이브러리를 사용한다.

- build.gradle에 Anko의 의존성을 추가한다.

  - gradle에서 Anko의 버전을 ext를 통해 변수 선언할 수 있다.

    ```kotlin
    ext {
    	anko_version = '0.10.8'
    }
    ```

    `implementation "org.jetbrains.anko:anko:$anko_version"`

##### 첫 UI 만들기

- 먼저 IntroActivityUI를 별도의 UI클래스로 사용하기 위해서는 먼저 AnkoComponent를 구현해야 한다. 이때 UI가 IntroActivity의 것이라는 정보도 함께 제공해야 한다. AnkoComponent를 구현한 UI클래스는 `fun createView(ui: AnkoContext<>):View` 를 오버라이드 해줘야 한다.

  ```kotlin
  class IntroActivityUI : AnkoComponent<IntroActivity>{
      override fun createView(ui: AnkoContext<IntroActivity>): View {
          return ui.relativeLayout() { // 루트 레이아웃을 RelativeLayout으로 지정
              gravity = Gravity.CENTER
              textView("PARAYO") {
                  textSize = 24f
                  textColorResource = R.color.purple_200
                  typeface = Typeface.DEFAULT_BOLD
              }
          }
      }
  }
  ```

  - RelativeLayout은 요소들에 대해 서로간의 상대적인 위치를 지정할 수 있는 레이아웃이다.







