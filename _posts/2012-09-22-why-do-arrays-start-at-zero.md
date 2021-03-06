---
layout: post
title: لماذا تبدأ المصفوفات من الصفر؟
---
من أول ما يتفاجأ به من يتعلم البرمجة هو أنه في أغلب لغات البرمجة ترقيم عناصر مصفوفات الحاسب يبدأ من الصفر. فالعنصر الأول يفترض به أن يكون رقم 1، أليس كذلك؟ لكن رقم 1 هو للعنصر الثاني والعنصر الأول هو رقم 0، والعنصر الأخير هو طول المصفوفة - 1.

لجعل الأمر منطقيًا علينا أولًا معرفة كيف يتم التعامل مع المصفوفات في الذاكرة. الأمر سهل، وممتع في الواقع. كل ما تفعله عند تعريف مصفوفة هو حجز مساحة لكامل المصفوفة مقسمة بين العناصر. كل نوع من البيانات يتطلب مساحة محددة من الذاكرة، ولكل مصفوفة طول محدد. اذا كان integer يتطلب 4 بايت والمصفوفة ذات 3 خانات، إجمالي المساحة المطلوبة هي 12 بايت. بامكاننا استخدام دالة `sizeof` في C لمعرفة المساحة المطلوبة لكل نوع. لنجرب إنشاء مصفوفة:  
{% highlight c %}
	int array[] = {1,3,5};
{% endhighlight %}
لدينا `(3 * 4)` بايت من الذاكرة، `1` يشغل الأربع الأولى، `3` الأربع الثانية و `5` الأربع التي تليها.

الجميل في الموضوع هو أننا الآن لا نحتاج إلا لمعرفة عنوان أول عنصر في المصفوفة بعد ذلك يمكننا الوصول لأي عنصر بضرب المساحة المتطلبة بعنوان العنصر `sizeof(type) * index` وإضافة ذلك لعنوان الذاكرة.  
{% highlight c %}
	int *ptr = &array[0]; // == &array
{% endhighlight %}
حسنًا، لدينا pointer لعنوان أول عنصر في المصفوفة، ماذا إذا أردنا طباعة العنصر الثاني؟
{% highlight c %}
	int second = *(ptr + 1);
	printf("%d", second);
	// => 3
{% endhighlight %}
لأننا حددنا `ptr` من نوع `int` فكل عملية نقوم بها عليه يضاف إليها `* sizeof(int)` تلقائيَا.  
إذَا هو كما لو أننا قمنا بطلب `array[1]`! فالعدد بين الأقواس يمثل بعد العنصر عن العنصر الأول. والعنصر الأول يبعد عن نفسه 0 خانة - لأنه هو نفسه، مما يجعل الصفر خيارًا منطقيًا جدًا.