## Lotto_generator
+ ConstraintLayout
+ NumberPicker
+ Shape Drawable

### 사용한 Kotlin 문법
+ apply
+ When
+ Random
+ Collection - Set, List
+ 람다함수

### 기능
+ 번호 수동선택 및 랜덤선택 가능

### 2021-04-22
1. activity_main.xml  
  + ConstraintLayout chainStyle="packed" : 컨스트레인트 레이아웃에서 벌어지는것을 체인스타일 packed로 서로 붙여놓을수 있다.
  + TextView background="@drawable/???" : 텍스트뷰에만 적용되는것은 아님, drawable폴더에 xml파일을 생성해서 shape solid 등의 속성으로 커스텀 하여 백그라운드 지정 가능(물론 코틀린클래스에서 변경가능)

2. MainActivity.kt
  + 버튼, 텍스트 등 레이아웃에서 사용하는 객체 선언하기, listOf 사용 하여 한번에 선언 
    ```KOTLIN
    private val runButton: Button by lazy {
      findViewById<Button>(R.id.runButton)
    }
    
    //////////////////////////////////////
    private val numberTextViewList: List<TextView> by lazy {
      listOf<TextView>(
          findViewById(R.id.textView1),
          ...
          findViewById(R.id.textView6)
      )
    }
    ```
    처럼 지정하는데 가장 기본적인 방법이고 최근들어 ViewBinding 사용함. 뒤에 다룰 예정
    
  + onCreate는 가볍게, 아래처럼
    ```KOTLIN
    override fun onCreate(savedInstanceState: Bundle?) {
      super.onCreate(savedInstanceState)
      setContentView(R.layout.activity_main)

      initNumberPicker()
      initRunButton()
      initAddButton()
      initClearButton()
    }
    ...
    private fun initNumberPicker(){
    ...
    }
    ...
    ```
  + return@setOnclickListener 처럼 return문 활용가능  
  + forEach : 자바 for(i : ??){}랑 비슷한듯, 컬렉션타입의 데이터 이용할 때 자주사용 👉 [설명 잘 되어있음](https://ddolcat.tistory.com/561)
  + shuffle(), sorted() 등 코틀린에서 제공하는 컬렉션 함수들 많으니까 따로 체크할것.
  + 기능구현 부분은 반복숙달할것.
