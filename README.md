```๐ก FastCampus ๊ฐ์ ์๊ฐ ๋ฐ ์ ๋ฆฌ```

### Lotto_generator
+ ConstraintLayout
+ NumberPicker
+ Shape Drawable

### ์ฌ์ฉํ Kotlin ๋ฌธ๋ฒ
+ apply
+ When
+ Random
+ Collection - Set, List
+ ๋๋คํจ์

### ๊ธฐ๋ฅ
+ ๋ฒํธ ์๋์ ํ ๋ฐ ๋๋ค์ ํ ๊ฐ๋ฅ


<img src="https://user-images.githubusercontent.com/63087903/119831785-92fc1580-bf38-11eb-96d5-1452c9c183de.jpg" width="200" height="430">


### 2021-04-22
1. activity_main.xml  
  + ConstraintLayout chainStyle="packed" : ์ปจ์คํธ๋ ์ธํธ ๋ ์ด์์์์ ๋ฒ์ด์ง๋๊ฒ์ ์ฒด์ธ์คํ์ผ packed๋ก ์๋ก ๋ถ์ฌ๋์์ ์๋ค.
  + TextView background="@drawable/???" : ํ์คํธ๋ทฐ์๋ง ์ ์ฉ๋๋๊ฒ์ ์๋, drawableํด๋์ xmlํ์ผ์ ์์ฑํด์ shape solid ๋ฑ์ ์์ฑ์ผ๋ก ์ปค์คํ ํ์ฌ ๋ฐฑ๊ทธ๋ผ์ด๋ ์ง์  ๊ฐ๋ฅ(๋ฌผ๋ก  ์ฝํ๋ฆฐํด๋์ค์์ ๋ณ๊ฒฝ๊ฐ๋ฅ)

2. MainActivity.kt
  + ๋ฒํผ, ํ์คํธ ๋ฑ ๋ ์ด์์์์ ์ฌ์ฉํ๋ ๊ฐ์ฒด ์ ์ธํ๊ธฐ, listOf ์ฌ์ฉ ํ์ฌ ํ๋ฒ์ ์ ์ธ 
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
    ์ฒ๋ผ ์ง์ ํ๋๋ฐ ๊ฐ์ฅ ๊ธฐ๋ณธ์ ์ธ ๋ฐฉ๋ฒ์ด๊ณ  ์ต๊ทผ๋ค์ด ViewBinding ์ฌ์ฉํจ. ๋ค์ ๋ค๋ฃฐ ์์ 
    
  + onCreate๋ ๊ฐ๋ณ๊ฒ, ์๋์ฒ๋ผ
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
  + return@setOnclickListener ์ฒ๋ผ return๋ฌธ ํ์ฉ๊ฐ๋ฅ  
  + forEach : ์๋ฐ for(i : ??){}๋ ๋น์ทํ๋ฏ, ์ปฌ๋ ์ํ์์ ๋ฐ์ดํฐ ์ด์ฉํ  ๋ ์์ฃผ์ฌ์ฉ ๐ [์ค๋ช ์ ๋์ด์์](https://ddolcat.tistory.com/561)
  + shuffle(), sorted() ๋ฑ ์ฝํ๋ฆฐ์์ ์ ๊ณตํ๋ ์ปฌ๋ ์ ํจ์๋ค ๋ง์ผ๋๊น ๋ฐ๋ก ์ฒดํฌํ ๊ฒ.
  + ๊ธฐ๋ฅ๊ตฌํ ๋ถ๋ถ์ ๋ฐ๋ณต์๋ฌํ ๊ฒ.
