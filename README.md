# 🎛️🔊 Potentiometer → TN TN Speed Control

في هذا المشروع سنستخدم **Potentiometer** للتحكم في سرعة تكرار صوت:

🔊 **TN TN**

يقوم Arduino بقراءة قيمة الـ Potentiometer وإرسالها إلى الحاسوب عبر **Serial**، ثم يمكن لبرنامج Python استخدام هذه القيمة للتحكم في سرعة صوت **TN TN**.

---

## 🎯 فكرة المشروع

```text
🎛️ Potentiometer
       ↓
   Arduino A0
       ↓
   قراءة القيمة
       ↓
 Serial Communication
       ↓
   💻 Python
       ↓
 🔊 TN TN
```

كلما قمنا بتدوير الـ Potentiometer، تتغير القيمة المرسلة إلى الحاسوب، وبالتالي يمكن تغيير سرعة صوت **TN TN**.

---

## 🧰 المكونات

* Arduino Uno 🤖
* Potentiometer 10kΩ 🎛️
* Breadboard
* Jumper Wires
* USB Cable
* Computer 💻
* Python 🐍
* Audio file 🔊

---

## 🔌 التوصيل

| Potentiometer | Arduino |
| ------------- | ------- |
| الطرف الأول   | 5V      |
| الطرف الأوسط  | A0      |
| الطرف الثالث  | GND     |

---

## 💻 كود Arduino

```cpp
int potPin = A0;

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  int potValue = analogRead(potPin);

  Serial.println(potValue);

  delay(30);
}
```

---

## 🧠 كيف يعمل الكود؟

يقرأ Arduino قيمة الـ Potentiometer باستخدام:

```cpp
analogRead(potPin);
```

القيمة تكون بين:

```text
0 → 1023
```

ثم يرسل Arduino القيمة إلى الحاسوب عبر:

```cpp
Serial.println(potValue);
```

---

## 🎛️ التحكم في سرعة TN TN

يستقبل برنامج Python قيمة الـ Potentiometer ويستخدمها للتحكم في سرعة تكرار الصوت.

مثال:

```text
🎛️ قيمة منخفضة
      ↓
🔊 TN ... TN ... TN

🎛️ قيمة متوسطة
      ↓
🔊 TN .. TN .. TN

🎛️ قيمة مرتفعة
      ↓
🔊 TN TN TN TN
```

يمكن لبرنامج Python تحويل قيمة الـ Potentiometer إلى **وقت انتظار (delay)** مناسب بين أصوات TN.

---

## 🐍 Python

يستقبل Python القيم القادمة من Arduino عبر **Serial** ويستخدمها للتحكم في سرعة تشغيل صوت **TN TN**.

ملف الصوت يمكن أن يكون مثل:

```text
tn.mp3
```

---

## 🚀 ماذا تعلمنا؟

من خلال هذا المشروع تعلمنا:

* 🎛️ استخدام Potentiometer
* 🔢 قراءة Analog Value
* 💻 إرسال البيانات عبر Serial
* 🐍 التواصل بين Arduino وPython
* ⏱️ التحكم في سرعة الصوت
* 🔊 إنشاء تأثير TN TN بسرعات مختلفة

---

## 📚 في كتاب Arduino

هذا المشروع مرتبط بدرس:

**Potentiometer → التحكم في سرعة TN TN**
