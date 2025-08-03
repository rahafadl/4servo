# 🔧 التحكم في 4 محركات سيرفو باستخدام Arduino

## 📌 فكرة المشروع:
تم في هذا المشروع برمجة 4 محركات سيرفو لتؤدي الحركات التالية:
- تتحرك بحركة Sweep (ذهابًا وإيابًا) لمدة ثانيتين.
- بعد ذلك، يتم تثبيت جميع المحركات على زاوية 90 درجة.

---

## 🧰 الأدوات المستخدمة:
- لوحة Arduino UNO
- 4 × محركات سيرفو (Servo Motors)
- أسلاك توصيل
- محاكي TinkerCAD أو تجربة واقعية
- برنامج Arduino IDE

---

## 💻 الكود المستخدم:

```cpp
#include <Servo.h>

Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;

void setup() {
  servo1.attach(3);
  servo2.attach(5);
  servo3.attach(6);
  servo4.attach(9);

  unsigned long startTime = millis();

  while (millis() - startTime < 2000) {
    for (int pos = 0; pos <= 180; pos += 5) {
      servo1.write(pos);
      servo2.write(pos);
      servo3.write(pos);
      servo4.write(pos);
      delay(15);
    }

    for (int pos = 180; pos >= 0; pos -= 5) {
      servo1.write(pos);
      servo2.write(pos);
      servo3.write(pos);
      servo4.write(pos);
      delay(15);
    }
  }

  servo1.write(90);
  servo2.write(90);
  servo3.write(90);
  servo4.write(90);
}

void loop() {}
