1. layout xml 파일 생성
2. custom view class 생성 extends Linear or Relative Layout
3. inflate

https://developer.android.com/training/custom-views/create-view.html

아래 생성자를 사용하지 않으면 crash 발생.
To allow Android Studio to interact with your view, at a minimum you must provide a constructor that takes a Context and an AttributeSet object as parameters. This constructor allows the layout editor to create and edit an instance of your view.

public LineAdCustomView(Context context, AttributeSet attrs) {
        super(context, attrs);
    }