#### Activity

##### Activity란

- 안드로이드에서 Activity는 애플리케이션의 컴포넌트를 의미한다. 우리가 앱을 사용하면서 보는 화면이 액티비티를 의미하며 사용자와의 상호작용을 위한 UI를 올릴 수 있다.
- 하나의 앱에는 여러개의 액티비티가 존재한다. 보통 하나의 앱에서 하나의 액티비티가 main으로 설정되면, 앱을 처음 구동하였을 때 가장 먼저 화면에 표시되는 액티비티가 된다. 그러다가 필요에 따라 다른 sub 액티비티가 실행이 된다. 이때 main 액티비티는 실행이 중단되지만, 시스템은 해당 액티비티를 스택에 push 하고 sub 액티비티를 실행하게 된다.

##### Activity 생명주기 함수

- onCreate 함수

  액티비티가 처음 생성될 때 호출하는 함수이다. 처음 프로젝트를 생성하면 main activity 에서 자동으로 생성해줄 만큼 액티비티 생명주기에 있어서 중요한 함수이다.

- onStart() 함수

  액티비티가 사용자에게 표시되기 직전에 호출되는 함수이다. 액티비티가 표시되면 onResume() 함수가 뒤따라 호출된다.

- onResume() 함수 

  액티비티가 시작되고 사용자와 상호작용을 시작하기 전에 호출되는 함수이다. 이 시점에 액티비티는 스택의 가장 상위에 존재하고 있고 해당 함수 뒤에는 onPause() 함수가 뒤따라 호출된다.

- onPause() 함수

  해당 액티비티에서 다른 액티비티로 전환되기 직전에 호출되는 함수이다. 보통 해당 함수에서는 아직 저장되지 않은 데이터를 유지하기 위해 데이터를 저장하거나 시스템 자원을 소모하는 작업을 진행하는 경우 중단할 때 사용된다. 해당 함수가 끝나기 전까지 액티비티 전환이 이루어지지 않기 때문에 해당 함수는 빠르게 작업이 이루어져야 한다. 액티비티가 다시 표시되기 시작하면 다시 onResume 함수가 호출되고 전환된 액티비티에 의해 액티비티가 가려지게 되면 onStop() 함수가 호출된다.

- onStop() 함수

  액티비티가 사용자에게 표시되지 않을 때 호출된다. 해당 함수는 액티비티가 소멸되는 경우에 호출될 수도 있고 다른 액티비티로 전환되면서 호출되는 경우도 있다. 

- onDestroy()

  액티비티가 소멸되기 전에 호출하는 함수이다. 시스템이 메모리 확보를 위해 인스턴스를 제거하는 경우가 있고 또는 finish() 함수를 호출한 경우에 호출되는 함수이다.

  

  - 참고자료

  https://lktprogrammer.tistory.com/164

