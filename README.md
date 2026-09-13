# 🎛️📏 Potentiometer → TN TN Speed Control

في هذا المشروع سنستخدم **Potentiometer** للتحكم في سرعة تكرار صوت:

🔊 **TN TN**

ويتم استخدام **Ultrasonic Sensor** لاكتشاف الجسم القريب.

كلما تغيّرت قيمة الـ Potentiometer، تتغير سرعة تكرار صوت **TN TN**.

---

## 🎯 فكرة المشروع

```text id="7m1bqk"
🎛️ Potentiometer
       ↓
  التحكم في السرعة
       ↓
📏 Ultrasonic Sensor
       ↓
  جسم قريب < 50 cm
       ↓
💻 Python
       ↓
🔊 TN TN
```

---

## 🧰 المكونات

* Arduino Uno 🤖
* Potentiometer 10kΩ 🎛️
* Ultrasonic Sensor HC-SR04 📏
* Breadboard
* Jumper Wires
* USB Cable
* Computer 💻
* Python 🐍
* Audio file 🔊

---

## 🔌 التوصيل

### Potentiometer

| Potentiometer | Arduino |
| ------------- | ------- |
| الطرف الأول   | 5V      |
| الطرف الأوسط  | A0      |
| الطرف الثالث  | GND     |

### Ultrasonic Sensor

| HC-SR04 | Arduino |
| ------- | ------- |
| VCC     | 5V      |
| GND     | GND     |
| TRIG    | Pin 10  |
| ECHO    | Pin 11  |

---

## 💻 الفكرة البرمجية

يقرأ Arduino قيمة الـ Potentiometer:

```cpp
int value = analogRead(A0);
```

ثم تُستخدم هذه القيمة للتحكم في **delay** أو سرعة إرسال إشارة الصوت.

عندما تكون المسافة أقل من:

```text id="m5m6js"
50 cm
```

يرسل Arduino إشارة إلى الحاسوب.

يقوم برنامج Python باستقبال الإشارة وتشغيل صوت **TN TN**.

---

## 🎛️ التحكم في السرعة

يمكن للـ Potentiometer التحكم في سرعة تكرار الصوت.

مثال:

```text id="j9u5q3"
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

كلما تغيّرت قيمة الـ Potentiometer، تتغير مدة الانتظار بين الإشارات.

---

## 🐍 Python

يتم استخدام Python للتواصل مع Arduino عبر **Serial** وتشغيل الملف الصوتي عند وصول إشارة التنبيه.

يمكن وضع ملف الصوت داخل المشروع، مثل:

```text id="v4n0kg"
tn.mp3
```

---

## 🚀 ماذا تعلمنا؟

من خلال هذا المشروع تعلمنا:

* 🎛️ استخدام Potentiometer
* 📏 استخدام Ultrasonic Sensor
* 🔢 قراءة القيم التناظرية
* ⏱️ التحكم في السرعة باستخدام `delay`
* 💻 التواصل بين Arduino وPython
* 🔊 تشغيل صوت TN TN
* 🧠 الجمع بين أكثر من مكوّن في مشروع واحد

---

## 📚 في كتاب Arduino

هذا المشروع مرتبط بدرس:

**Potentiometer → التحكم في سرعة TN TN**
