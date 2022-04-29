# 创建第一个Andriod Kotlin应用

## 1. 创建一个新工程

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/1.png?raw=true)

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/2.png?raw=true)



## 2. 创建模拟器

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/3.png?raw=true)

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/4.png?raw=true)



创建好后尝试运行应用程序

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/5.png?raw=true)



## 3. 修改第一个页面fragment_first.xml的布局

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/6.png?raw=true)

修改完成代码：

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/screenBackground"
    tools:context=".FirstFragment">

    <TextView
        android:id="@+id/textview_first"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/hello_first_fragment"
        android:textColor="@color/white"
        android:textSize="72sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.3" />

    <Button
        android:id="@+id/random_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="24dp"
        android:background="@color/buttonBackground"
        android:text="@string/random_button_text"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textview_first" />

    <Button
        android:id="@+id/toast_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="24dp"
        android:layout_marginBottom="4dp"
        android:background="@color/buttonBackground"
        android:text="@string/toast_button_text"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textview_first" />

    <Button
        android:id="@+id/count_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:background="@color/buttonBackground"
        android:text="@string/count_button_text"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/random_button"
        app:layout_constraintStart_toEndOf="@+id/toast_button"
        app:layout_constraintTop_toBottomOf="@+id/textview_first" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

成果：

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/7.png?raw=true)

## 4. 修改第二页面fragment_second.xml的布局

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/8.png?raw=true)

修改完成代码：

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/screenBackground2"
    tools:context=".SecondFragment">

    <TextView
        android:id="@+id/textview_header"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="24dp"
        android:layout_marginTop="24dp"
        android:layout_marginEnd="24dp"
        android:text="@string/random_heading"
        android:textColor="@color/colorPrimaryDark"
        android:textSize="24sp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button_second"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="100dp"
        android:text="@string/previous"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/textView_random"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="R"
        android:textColor="@color/white"
        android:textSize="72sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button_second"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textview_header"
        app:layout_constraintVertical_bias="0.45" />


</androidx.constraintlayout.widget.ConstraintLayout>
```

成果：

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/9.png?raw=true)

（仅布局，参数后面实现）



## 5. 一些配合的xml文件

src/main/res/values/colors.xml

```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#FFBB86FC</color>
    <color name="purple_500">#FF6200EE</color>
    <color name="purple_700">#FF3700B3</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="screenBackground">#2196F3</color>
    <color name="buttonBackground">#BBDEFB</color>
    <color name="colorPrimaryDark">#3700B3</color>
    <color name="screenBackground2">#26C6DA</color>


</resources>
```

src/main/res/values/strings.xml

```
<resources>
    <string name="app_name">My Application</string>
    <string name="action_settings">Settings</string>
    <!-- Strings used for fragments for navigation -->
    <string name="first_fragment_label">First Fragment</string>
    <string name="second_fragment_label">Second Fragment</string>
    <string name="next">Random</string>
    <string name="previous">Previous</string>

    <string name="hello_first_fragment">0</string>
    <string name="random_heading">Here is a random number between 0 and %d.</string>
    <string name="toast_button_text">Toast</string>
    <string name="count_button_text">Count</string>
    <string name="random_button_text">Random</string>
</resources>
```

src/main/res/values/themes.xml

```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.MyApplication" parent="Theme.MaterialComponents.DayNight.DarkActionBar.Bridge">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>

    <style name="Theme.MyApplication.NoActionBar">
        <item name="windowActionBar">false</item>
        <item name="windowNoTitle">true</item>
    </style>

    <style name="Theme.MyApplication.AppBarOverlay" parent="ThemeOverlay.AppCompat.Dark.ActionBar" />

    <style name="Theme.MyApplication.PopupOverlay" parent="ThemeOverlay.AppCompat.Light" />
</resources>
```



## 6. 添加TOAST和COUNT动作

### Toast添加一个toast消息

打开FirstFragment.kt文件，有三个方法：onCreateView，onViewCreated和onDestroyView，在onViewCreated方法中使用绑定机制设置按钮的响应事件（创建应用程序时自带的按钮）。

```
binding.randomButton.setOnClickListener {
    findNavController().navigate(R.id.action_FirstFragment_to_SecondFragment)
}
```

接下来，为TOAST按钮添加事件，使用**findViewById()**查找按钮id，代码如下：

```
// find the toast_button by its ID and set a click listener
view.findViewById<Button>(R.id.toast_button).setOnClickListener {
   // create a Toast with some text, to appear for a short time
   val myToast = Toast.makeText(context, "Hello Toast!", Toast.LENGTH_LONG)
   // show the Toast
   myToast.show()
}
```



### count按钮实现数字增加

此步骤向Count按钮添加事件响应，更新Textview的文本显示。
在FirstFragment.kt文件，为count_buttion按钮添加事件：

```
view.findViewById<Button>(R.id.count_button).setOnClickListener {
   countMe(view)
}

```

countMe()为自定义方法，以View为参数，每次点击增加数字1，具体代码为：

```
private fun countMe(view: View) {
   // Get the text view
   val showCountTextView = view.findViewById<TextView>(R.id.textview_first)

   // Get the value of the text view.
   val countString = showCountTextView.text.toString()

   // Convert value to a number and increment it
   var count = countString.toInt()
   count++

   // Display the new value in the text view.
   showCountTextView.text = count.toString()
}
```





## 7. 实现random数据的传递和第二页面随机数生成

### 启用SafeArgs

1. 首先打开 Gradle Scripts > build.gradle (Project: My First App)

​		在plugins节添加

```
id 'androidx.navigation.safeargs.kotlin' version '2.5.0-alpha01' apply false

```

2. 接着打开 Gradle Scripts > build.gradle (Module: app)

​		在plugins节添加

```
id 'androidx.navigation.safeargs'
```



重新生成工程Build > Make Project



### 创建导航动作的参数

src/main/res/navigation/nav_graph.xml

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/10.png?raw=true)

分别点击FirstFragment和SecondFragment

在Arguments中添加参数myArg，类型为Integer



### FirstFragment添加代码，向SecondFragment发数据

打开FirstFragment.kt源代码文件

修改onViewCreated()方法：

```
binding.randomButton.setOnClickListener {
            //findNavController().navigate(R.id.action_FirstFragment_to_SecondFragment)
            val showCountTextView = view.findViewById<TextView>(R.id.textview_first)
            val currentCount = showCountTextView.text.toString().toInt()
            val action = FirstFragmentDirections.actionFirstFragmentToSecondFragment(currentCount)
            findNavController().navigate(action)

        }
```



### 添加SecondFragment的代码

导入navArgs包

```
import androidx.navigation.fragment.navArgs
```

修改 onViewCreated()方法：

```
override fun onViewCreated(view: View, savedInstanceState: Bundle?) {

    super.onViewCreated(view, savedInstanceState)

    val args: SecondFragmentArgs by navArgs()
    val count = args.myArg
    val countText = getString(R.string.random_heading, count)
    view.findViewById<TextView>(R.id.textview_header).text = countText

    val random = java.util.Random()
    var randomNumber = 0
    if (count > 0) {
        randomNumber = random.nextInt(count + 1)
    }

    view.findViewById<TextView>(R.id.textView_random).text = randomNumber.toString()

    binding.buttonSecond.setOnClickListener {
        findNavController().navigate(R.id.action_SecondFragment_to_FirstFragment)
    }
}
```





## 运行结果

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/11.png?raw=true)

![](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C2/12.png?raw=true)
