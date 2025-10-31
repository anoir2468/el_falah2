# دليل تحويل التطبيق إلى تطبيق موبايل باستخدام Capacitor

## المتطلبات الأساسية

1. **Node.js** (الإصدار 18 أو أحدث)
2. **Android Studio** (لبناء تطبيق Android)
3. **Xcode** (لبناء تطبيق iOS - Mac فقط)

---

## خطوات التثبيت

### 1. تثبيت Capacitor

\`\`\`bash
npm install @capacitor/core @capacitor/cli
npm install @capacitor/android @capacitor/ios
\`\`\`

### 2. بناء التطبيق

\`\`\`bash
npm run build
\`\`\`

هذا سينشئ مجلد `out` يحتوي على ملفات التطبيق الثابتة.

### 3. إضافة المنصات

#### لـ Android:
\`\`\`bash
npx cap add android
\`\`\`

#### لـ iOS:
\`\`\`bash
npx cap add ios
\`\`\`

### 4. مزامنة الملفات

\`\`\`bash
npx cap sync
\`\`\`

---

## فتح المشروع في IDE

### Android Studio:
\`\`\`bash
npx cap open android
\`\`\`

ثم:
1. انتظر حتى يكتمل Gradle Sync
2. اضغط على زر "Run" لتشغيل التطبيق على محاكي أو جهاز حقيقي

### Xcode (Mac فقط):
\`\`\`bash
npx cap open ios
\`\`\`

ثم:
1. اختر جهاز المحاكاة أو جهاز حقيقي
2. اضغط على زر "Play" لتشغيل التطبيق

---

## تخصيص التطبيق

### تغيير اسم التطبيق والأيقونة

1. **Android**: 
   - افتح `android/app/src/main/res/values/strings.xml`
   - غير `app_name`
   - ضع الأيقونات في `android/app/src/main/res/mipmap-*`

2. **iOS**:
   - افتح المشروع في Xcode
   - اختر Target → General
   - غير Display Name
   - اسحب الأيقونات إلى App Icon

### تغيير معرف التطبيق (App ID)

في ملف `capacitor.config.json`:
\`\`\`json
{
  "appId": "dz.yourcompany.farmername"
}
\`\`\`

---

## بناء التطبيق للنشر

### Android (APK/AAB):

1. افتح Android Studio
2. Build → Generate Signed Bundle/APK
3. اتبع الخطوات لإنشاء Keystore
4. اختر "release" build variant
5. سيتم إنشاء ملف APK أو AAB

### iOS (IPA):

1. افتح Xcode
2. Product → Archive
3. اتبع خطوات التوقيع والتصدير
4. سيتم إنشاء ملف IPA

---

## النشر على المتاجر

### Google Play Store:

1. أنشئ حساب مطور (25$ مرة واحدة)
2. ارفع ملف AAB
3. املأ معلومات التطبيق
4. انتظر المراجعة (عادة 1-3 أيام)

### Apple App Store:

1. أنشئ حساب مطور (99$/سنة)
2. استخدم App Store Connect
3. ارفع ملف IPA
4. املأ معلومات التطبيق
5. انتظر المراجعة (عادة 1-7 أيام)

---

## التحديثات

عند تحديث التطبيق:

\`\`\`bash
npm run build
npx cap sync
\`\`\`

ثم أعد بناء التطبيق من Android Studio أو Xcode.

---

## نصائح مهمة

1. **اختبر على أجهزة حقيقية** قبل النشر
2. **راجع سياسات المتاجر** (Google Play و App Store)
3. **أضف Privacy Policy** (مطلوب للنشر)
4. **اختبر على شبكات مختلفة** (WiFi, 4G, 5G)
5. **تأكد من الأداء** على أجهزة منخفضة المواصفات

---

## الدعم والمساعدة

- [Capacitor Documentation](https://capacitorjs.com/docs)
- [Android Developer Guide](https://developer.android.com)
- [iOS Developer Guide](https://developer.apple.com)

---

## الملفات المهمة

- `capacitor.config.json` - إعدادات Capacitor
- `public/manifest.json` - إعدادات PWA
- `next.config.mjs` - إعدادات Next.js للتصدير الثابت
- `out/` - مجلد التطبيق المبني (بعد npm run build)

---

**ملاحظة**: هذا التطبيق جاهز الآن للتحويل إلى تطبيق موبايل أصلي!
