##关于Lambda

####概念
1. Lambda是第十一个希腊字母,大写Λ，小写λ。
2. Lambda表达式 是Java8的新特性之一。
3. 简单来说，编程中提到的 lambda 表达式，通常是在需要一个函数，但是又不想费神去命名一个函数的场合下使用，也就是指匿名函数。
4. 在android中使用需要gradle-retrolambda插件。

####简单语法
1. () -> {}
2. 设置监听事件

			mFab.setOnClickListener(new View.OnClickListener() {
		            @Override
		            public void onClick(View v) {
		                doSomething();
		            }
		        });
		        
		   //使用Lambda,`v`代表onClick传递的参数v,参数不能省略,但是可以随意命名.
		   mFab.setOnClickListener(v->doSomething());

3. 实现Runnable


			new Thread(new Runnable() {
	            @Override
	            public void run() {
	                doSomething();
	            }
	        }).start();
	        
	        //使用Lambda
	        new Thread(() -> doSomething()).start();
	        //另外实例化Runnable成员变量也可以这么写
	        Runnable runnable = ()->doSomething();

4. 使用Lambda进行迭代

			// Java 8之前：
			List features = Arrays.asList("Lambdas", "Default Method", "Stream API", "Date and Time API");
			for (String feature : features) {
			    System.out.println(feature);
			}
			
			// Java 8之后：
			List features = Arrays.asList("Lambdas", "Default Method", "Stream API", "Date and Time API");
			features.forEach(n -> System.out.println(n));
			 
			// 使用Java 8的方法引用更方便，方法引用由::双冒号操作符标示，
			// 看起来像C++的作用域解析运算符
			features.forEach(System.out::println);

5. 结合Rxjava来让代码更简洁

