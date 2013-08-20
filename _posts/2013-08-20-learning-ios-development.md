---
title : تعلم تطوير تطبيقات iOS
layout: post
---
أكثر سؤال يوجه لي هو "كيف يمكنني تعلم تطوير تطبيقات iPhone؟". وضعت هنا ما يشابه خارطة طريق صغيرة لتساعدك على بدء تعلم تطوير تطبيقات iOS.

#### احصل على الأدوات
ستحتاج لجهاز ماك لتطوير أي شيء ل iOS. آسف ولكن هذا الواقع.
ابدأ بتحميل بيئة تطوير البرمجيات 
[Xcode][Xcode] المقدمة من Apple والتي يمكنك الحصول عليها مجانًا من [متجر تطبيقات ماك][xcode-appstore].
Xcode سيقدم لك كل ما تحتاجه. حزمة تطوير البرامج، محرر نصوص، مصمم الواجهات، debugger ،simulator والعديد من الأدوات الأخرى. في البداية **لا** تحتاج [لعضوية مطوري iOS][developer-membership] من أبل، لكن حين تريد تجربة التطبيق على جهاز iOS أو إطلاق التطبيق في المتجر فستحتاج للحصول على العضوية والتي تكلف 99$ سنويًا للأفراد.

#### تعلم اللغة
لغة Objective-C هي اللغة الرسمية لبرمجة ماك أو iOS. هناك العديد من الأدوات لكتابة التطبيقات بلغات أخرى مثل JavaScript أو Ruby، لكن، ومن تجربة، ابذل الجهد اللازم مرة واحدة وتعلم Objective-C بدلًا من إضاعة جهدك  مرات عديدة وأنت تحاول تخطي العقبات التي تواجهها بإستخدامك تلك الأدوات محاولًا تجنب تعلم اللغة. Objective-C هي لغة المنصة الحقيقية، تعلمها.

* [مقدمة من Apple][objective-c0]
* [درس مفصل ومبسط][objective-c1]
* [درس للأساسيات بالفديو][objective-c2]
* [سلسلة دروس مفصلة مع أمثلة][objective-c3]

#### تعلم الأطر
بعد أن تعلمت اللغة، حان الوقت لإستخدامها. كتابة أي تطبيق ل iOS يكون بالإعتماد على SDK (حزمة تطوير البرامج) التي تحصل عليها مع Xcode. الحزمة  تحتوي على الأطر التي ستسخدمها في بناء أي تطبيق. عدد الأطر كبير واستخدام أحدها يعتمد على التطبيق الذي تحاول بناءه. أي أنك لن تستخدمها جميعًا وقد لا تستخدم بعضها أبدًا. محاولة تعلمها كلها قبل البدء مضيعة للوقت. أفضل طريقة لتعلمها هي [البدء في عمل تطبيق][first-app] ثم [تطبيق آخر][simple-app] وآخر وتعلم الأجزاء التي تحتاجها وأنت تتقدم. حين تصل لهذه المرحلة، يجب أن يكون توثيق حزمة التطوير (SDK Documentation) صديقك الصدوق.

#### تعلم التصميم
تصميم التطبيق [لا يقتصر على الواجهة][app-design] فقط، بل يتعدى ذلك لتجربة المستخدم كاملة لتشمل أشياء كالسعر وخصوصية المستخدم مثلًا. تصميم تطبيقك بعناية من أهم عوامل نجاحه على منصة iOS.  ستسمع كثيرًا عن [HIG][hig] (Human Interface Guidlines) ويعتبر مرجعًا لا يستغنى عنه في تصميم تطبيقات iOS.  

* [درس مفصل في تصميم الواجهات][desgin-tutorial]
* [أنماط التصميم للواجهات][design-patterns]

#### مصادر أخرى
* من **أفضل** المصادر، دورة فديو كاملة لتطوير iOS مجانًا من Stanford على [iTunesU]
[stanford-course]
* لمن يفضلون الكتب، كتاب [Learning Cocoa with Objective-C][learn-cocoa-book]
* دروس [RayWenderlich][ray] وبعضها مترجم [للعربية][ray-ar]
* دروس [Mobile tuts+][mobile-tuts+]
 * دروس [AppCoda][appcoda]
* وسم Objective-C و iOS في [StackOverflow][stackoverflow]

[xcode]: https://developer.apple.com/xcode/

[xcode-appstore]: macappstore://itunes.apple.com/us/app/xcode/id497799835?mt=12

[developer-membership]: https://developer.apple.com/programs/ios/

[objective-c0]: https://developer.apple.com/library/mac/referencelibrary/GettingStarted/Learning_Objective-C_A_Primer/index.html

[objective-c1]: http://cocoadevcentral.com/d/learn_objectivec/

[objective-c2]: http://nsscreencast.com/episodes/1-objective-c-basics

[objective-c3]: http://mobile.tutsplus.com/series/learn-objective-c/

[first-app]: http://www.raywenderlich.com/25561/learn-to-code-ios-apps-3-your-first-app

[simple-app]: http://www.raywenderlich.com/1797/ios-tutorial-how-to-create-a-simple-iphone-app-part-1

[app-design]: https://developer.apple.com/library/ios/documentation/userexperience/conceptual/mobilehig/AppDesign/AppDesign.html

[hig]: https://developer.apple.com/library/ios/documentation/userexperience/conceptual/mobilehig/Introduction/Introduction.html

[desgin-tutorial]: http://taybenlor.com/2013/05/21/designing-for-ios.html

[design-patterns]: http://pttrns.com/

[stanford-course]: https://itunes.apple.com/itunes-u/ipad-iphone-application-development/id473757255?mt=10

[learn-cocoa-book]: http://shop.oreilly.com/product/0636920023203.do

[ray]: http://www.raywenderlich.com/tutorials
[ray-ar]: http://www.raywenderlich.com/ar/

[mobile-tuts+]: http://mobile.tutsplus.com/category/tutorials/iphone/

[appcoda]: http://www.appcoda.com/

[stackoverflow]: http://stackoverflow.com/questions/tagged/objective-c+ios