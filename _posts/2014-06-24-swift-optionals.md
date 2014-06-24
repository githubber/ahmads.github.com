---
title : 'Swift: Optionals'
layout: post
---

من المبادئ المهمة في Swfit هو جعل اللغة آمنة، هذا يعني محاولة تجنب الأخطاء قدر الإمكان، وكذلك محاولة إيجاد الأخطاء في Compile Time وليس Run Time. أي عندما تقوم ببناء التطبيق وليس أثناء استخدامه.

الأنواع الاختيارية (Optionals) تختلف بأن الهدف منها هو التعبير عن امكانية وجود قيمة أو امكانية *عدم* وجود قيمة. يمكن التعبير عن حالة الأنواع الإختيارية بطريقتين "هناك قيمة، والقيمة هي *x*" أو "لا يوجد قيمة على الإطلاق".

كمثال، احدى خصائص النوع `String` هي دالة `toInt`، هذه الدالة تحاول تحويل النص إلى `Int`. لكن بالطبع ليس كل نص يمكن تحويله لعدد. النص `"123"` يمكن تحويله إلى القيمة العددية `123`. لكن نص مثل `"hello, world"` لا يمكن تحويله.

{% highlight javascript %}
let possibleNumber = "123"
let convertedNumber = possibleNumber.toInt()
{% endhighlight %}

في المثال أعلاه، الثابت `convertedNumber` ليس من نوع `Int` كما قد تظن، هو في  الواقع من نوع `Int?` ويعني `Optional Int`. نرمز للأنواع الاختيارية (Optionals) باضافة علامة استفهام `?` إلى اسم النوع.

### لماذا Optionals؟
من خصائص Swift أنها [Type-Safe Language][] فهي لن تسمح لك يتعيين قيمة تختلف عن النوع المُعرّف، سواء لمتغير أو ثابت أو عنصر لدالة أو ناتج لدالة.
  
في مثال الدالة `toInt`، في بعض الأحيان لن تتمكن من تحويل النص إلى قيمة 
عددية، ماذا ستكون النتيجة المُعادة من الدالة في تلك الحالة؟ قد نقترح `0` ولكن صفر نتيجة صحيحة للنص `"0"`، كذلك هو الحال للعدد `-1` أو أي عدد في الواقع. ولأن النوع `Int` فلا يمكننا استخدام غير الأعداد الصحيحة. هنا تتضح فائدة Optionals، بامكان استخدام القيمة الخاصة `nil` مع Optionals للعتبير عن عدم وجود قيمة.

###Forced Unwrapping
بامكانك تخيل أن Optionals تكوّن طبقة تغلف المتغير أو الثابت لتُعلمك قبل استخدامه بوجود قيمة من عدمها. استخدم  `if` مع المتغير أو الثابت من نوع Optional لتفحص وجود القيمة. اذا كان له قيمة ستكون النتيجة `true`، وان لم يكن له قيمة ستكون النتيجة `false`.

في حال تأكدت من وجود قيمة، استخدم علامة التعجب `!` في نهاية اسم المتغير أو الثابت لكشف القيمة. استخدام علامة التعجب هو كقولك: "أعرف أن لهذا المتغير قيمة، فضلا استخدمها". هذا يسمى Forced Unwrapping.

{% highlight javascript %}

let possibleNumber = "123"
let convertedNumber = possibleNumber.toInt()

if convertedNumber {
    println("\(possibleNumber) has an integer value of \(convertedNumber!)")
} else {
    println("\(possibleNumber) could not be converted to an integer")
}
// prints "123 has an integer value of 123"
{% endhighlight %}

###Optional Binding

تستخدم Optionals كثيرًا في Swift، لذلك هناك طريقة أسهل لاستخراج قيمها وهي Optional Binding. تستخدم هذه الطريقة لفحص اذا كان Optional يحمل قيمة، وفي حال كان يحمل قيمة، تعين القيمة لثابت أو متغير مؤقت. كلها في تعبير واحد. يمكنك استخدام Optional Binding مع `if` و `while`. 

تكتب Optional Binding مع `if` كالتالي:
{% highlight javascript %}
 if let <constantName> = <someOptional> {
    <statements>
}
{% endhighlight %}

يمكننا كتابة مثال `possibleNumber` السابق باستخدام Optional Binding بدلًا من Forced Unwrapping كالتالي:
{% highlight javascript %}
if let actualNumber = possibleNumber.toInt() {
    println("\(possibleNumber) has an integer value of \(actualNumber)")
} else {
    println("\(possibleNumber) could not be converted to an integer")
}
// prints "123 has an integer value of 123"
{% endhighlight %}

بامكانك قراءتها: "اذا كان `Optional Int` المعاد من `possibleNumber.toInt` يحتوي على قيمة، عرف ثابت جديد اسمه `actualNumber` واجعل قيمته هي القيمة الموجودة في Optional".

اذا نجح التحويل، الثابت `actualNumber` يصبح متوفرًا في الفرع الأول للعبارة الشرطية `if`. يكون معرفًا ويحمل القيمة الموجودة في Optional، ولا داعي لاستخدام علامة   التعجب `!` لاستخراج قيمته. كما في المثال، نستخدم `actualNumber` مباشرة لطباعة القيمة المحوّلة. 

يمكنك استخدام متغير عوضًا عن ثابت اذا احتجت للتحكم بقيمة `actualNumber`. ببساطة اكتب `if var actualNumber`.

###nil

تعين حالة عدم وجود قيمة لمتغير من نوع Optional باستخدام القيمة الخاصة `nil`
{% highlight javascript %}
var serverResponseCode: Int? = 404
// serverResponseCode يتحتوي على قيمة 404
serverResponseCode = nil
// serverResponseCode لا يحتوي على قيمة
{% endhighlight %}

لا يمكن استخدام `nil` مع غير Optionals. اذا كنت بحاجة للتعبير عن عدم وجود قيمة لمتغير أو ثابت في حالات معينة، عرفه دئمًا على أنه نوع اختياري (Optional).

{:.callout}
هذه التدوينة هي جزء من [سلسلة تدوينات](/2014/06/10/swift/) عن لغة البرمجة Swift

[Type-Safe Language]: http://en.wikipedia.org/wiki/Type-safety

{% include translation.ext %}