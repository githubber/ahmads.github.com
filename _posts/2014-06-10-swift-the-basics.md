---
title : 'Swift: الأساسيات'
layout: post
---

توفر Swift أنواع قيم أساسية خاصة بها لكل الأنواع الموجودة في C و Objective-C. النوع `Int` لتعريف Integers؛ النوعين `Double` و `Float` لتعريف Floating-point values؛ النوع `String` لتعريف Strings؛ النوع `Bool` لتعريف Booleans. توفر كذلك نوعين من المجموعات الأساسية، هما Arrays وDictionaries.

بالإضافة للأنواع المألوفة، توفر Swift أنواع متقدمة مثل Tuples، هذا النوع يعطيك القدرة على التعامل مع مجموعة من القيم مرة واحدة. يمكن مثلًا إعادة مجموعة من القيم من دالة كقيمة مركبة.

###المتغيرات والثوابت

المتغيرات والثوابت تعطي اسمًا لكل قيمة من نوع محدد.
استخدم `let`  لتعريف ثابت  (Constant) و `var` لتعريف متغير (Variable). ليس بالضرورة أن يكون للثابت قيمة في Compile Time، لكن يجب تعيين قيمتة مرة واحدة فقط. هذا يعني أن تستخدم الثوابت لتعريف القيم المحسوبة مرة واحدة لكن مستخدمة عدة مرات.

{% highlight javascript %}
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
{% endhighlight %}

اذا كانت القيمة لن تتغير، عرفها دائمًا على أنها ثابت `let`. استخدم المتغير `var` في حالة احتجت لتغيير القيمة فقط. في المثال أعلاه، `maximumNumberOfLoginAttempts` العدد الأقصى لمحاولات الدخول لن يتغير. بينما المحاولة الحالية `currentLoginAttempt` ستتغير. 

محاولة تغيير قيمة ثابت ينتج عنها خطأ

{% highlight javascript %}
let languageName = "Swift"
languageName = "Swift++"
// خطأ في وقت الترجمة compile-time error
{% endhighlight %}

لتعريف أكثر من متغير أو ثابت دفعة واحدة، ضعها في سطر واحد وبينها فاصلة `,`.

{% highlight javascript %}
var x = 0.0, y = 0.0, z = 0.0
{% endhighlight %}

يمكنك استخدام أي حرف تقريبًا في اسم المتغير أو الثابت. يستثنى من ذلك علامات العمليات الرياضية، الأسهم، وحروف رسم الخطوط والمربعات. ولايمكن أن يبدأ الاسم برقم.

{% highlight javascript %}
let π = 3.14159
let اللغة = "Arabic"
let 🐶🐮 = "dogcow"
{% endhighlight %}

 نوع الثابت أو المتغير يجب أن يطابق نوع القيمة التي تريد تعيينها له. لست بحاجة لكتابة النوع دومًا. تعيين قيمة في وقت التعريف يعطي Compiler القدرة على 
 استنتاج النوع (Type inference). يستنتج المترجم أن نوع الثابت `meaningOfLife` هو `Int` لأن القيمة الأولية له `42` هي من نوع `Int`.

{% highlight javascript %}
let meaningOfLife = 42
{% endhighlight %}

اذا كانت القيمة الأولية لا توفر معلومات كافية (أو ليس هناك قيمة أولية)، بامكانك تحديد النوع بكتابة نقطتين رأسيتين متبوعة بمسافة ثم النوع بعد اسم المتغير أو الثابت. يمكنك قراءة النقطتين الرأسيتين على أنها "*... من نوع ...*". المتغير `welcomeMessage` من نوع `String`.

{% highlight javascript %}
var welcomeMessage: String
{% endhighlight %}

بمجرد تعريف مثغير أو ثابت لا يمكن تعريفه مجددًا بنفس الاسم، أو تغيير نوعه. ولا يمكنك إعادة تعريف ثابت لمتغير أو العكس.

لا يتم تحويل نوع القيم تلقائيًا. اذا أردت تحويل النوع عليك فعل ذلك بشكل صريح.

{% highlight javascript %}
let three = 3
let pointOneFourOneFiveNine = 0.14159
let pi = Double(three) + pointOneFourOneFiveNine
// pi تساوي 3.14159، ويستنتج أنها من نوع Double
{% endhighlight %}

###الأعداد

الأعداد الصحيحة -بدون فواصل العشرية- (Integers) سواء موجبة، سالبة، أو صفر تكون من نوع `Int`.  
لأعداد الفاصلة العائمة -تحتوي على فاصلة عشرية- سواء موجبة أو سالبة استخدم النوع `Double` للأعداد الكبيرة جدًا أو التي تتطلب دقة عالية، و `Float` للأعداد التي لا تتطلب دقة أكثر من ٦ خانات عشرية.

###Booleans

لتعريف متغير أو ثابت Boolean استخدم النوع `Bool`. تستخدم Swift القيمتين `true` و `false` كقيم منطقية. 

{% highlight javascript %}
let orangesAreOrange = true
var turnipsAreDelicious = false
{% endhighlight %}

###Strings

يمكنك تعريف ثابت أو متغير من نوع `String` بقيمة مباشرة باستخدام String literals، وهي أي نص بين علامتي تنصيص `""`. 

{% highlight javascript %}
let someString = "Some string literal value”
{% endhighlight %}

بإمكانك إدراج القيم في النصوص بسهولة، Swift تدعم توليد النص (String interpolation). اكتب القيمة داخل قوسين وأسبقها بشرطة مائلة `\`.

{% highlight javascript %}
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
{% endhighlight %}

###Tuples

  هي مجموعة من القيم في قيمة واحدة مُركبة. القيم داخل Tuple يمكن أن تكون من أنواع مختلفة.
في المثال أدناه `(404, "Not Found")` هو Tuple من نوع `(Int, String)`

{% highlight javascript %}
let http404Error = (404, "Not Found")

let (statusCode, statusMessage) = http404Error

statusCode // 404
statusMessage // "Not Found"
{% endhighlight %}

###طباعة المتغيرات والثوابت

استخدم الدالة `println` لطباعة واستعراض قيمة أي متغير أو ثابت
{% highlight javascript %}
var name = "Ahmad"
println("Hello, \(name)!")
// تطبع Hello, Ahmad!
{% endhighlight %}

{:.callout}
  هذه التدوينة هي جزء من [سلسلة تدوينات](/2014/06/10/swift/) عن لغة البرمجة Swift

{% include translation.ext %}