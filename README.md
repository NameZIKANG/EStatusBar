# EStatusBar
用于沉浸式状态栏,引入后只需几行代码解决沉浸式问题.

## 这项目使用了MX东芝的  [Android 沉浸式状态栏完美解决方案](https://blog.csdn.net/u014418171/article/details/81223681)  进行封装


### 我就是个搬运工,回头得跟他要个二维码

    //build.gradle添加
    allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

	//app的build.gradle添加
    dependencies {
	       implementation 'com.github.NameZIKANG:EStatusBar:1.0.0'
	}

       在setContentView之后调用下面的方法:

      /**
     * 设置沉浸式
     * @param activity    上下文
     * @param isPadding   是否添加状态栏
     * @param isTextColor 状态栏字体颜色切换(true为浅色,false为深色)
     * @param colorId     状态栏背景色设置(设置为1会默认白色)
     */
     StatusBarUtil.setStutatusBar(this, true, true, 1);



       /**
     * 图片背景设置沉浸式
     * @param activity    上下文
     * @param isTextColor 状态栏字体颜色切换(false为浅色,true为深色)
     */
      StatusBarUtil.setImageStutatusBar(this, false);

      // 图片设置时这里需要在xml布局外包裹一层view


    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent">

		<!-- ImageView用于设置背景图片 -->

        <ImageView
            android:id="@+id/ll_bg"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

           <com.jac.estatusbar.statusbar.StatusBarHeightView
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:layout_alignParentEnd="true"
            android:orientation="vertical"
            app:use_type="use_padding_top">
            	...
            	//布局文件
            	...
           </com.jac.estatusbar.statusbar.StatusBarHeightView>

    </RelativeLayout>