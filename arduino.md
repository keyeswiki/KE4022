# Arduino


## 1. Arduino简介  

Arduino是一款开源的电子原型平台，由硬件和软件组成，旨在让爱好者、学生及专业开发者能够轻松地构建互动项目。Arduino的硬件部分主要由微控制器（如ATmega系列）构成，用户可以通过这些微控制器与各种传感器、执行器等电子部件互动。Arduino IDE（集成开发环境）提供了一个简洁的编程界面，用户可以使用C/C++语言编写代码，并将其上传到Arduino板中。因为其易于学习和使用，加上丰富的配件及社区支持，Arduino被广泛应用于学生学习、Maker文化及各类电子项目中，如机器人、自动化控制、传感器监测等。  

## 2. 连接图  

![](media/eff5c82377876a3e10b972b46f45f49c.png)  

## 3. 测试代码  

```cpp  
#include <Servo.h> // 导入舵机库  

Servo servo1; // 定义两个舵机的名称  
Servo servo2;  

void setup() {  
    // 两个舵机分别连到D9 D10  
    servo1.attach(9);  
    servo2.attach(10);  
}  

void loop() { // 反复循环  
    for(int i = 0; i < 180; i++) { // 从0度转到180度  
        servo1.write(i); // 舵机1转动到i度  
        servo2.write(i); // 舵机2转动到i度  
        delay(10); // 延时10ms  
    }  
    delay(1000); // 等待1s  
    for(int i = 180; i > 0; i--) { // 从180度转到0度  
        servo1.write(i);  
        servo2.write(i);  
        delay(10);  
    }  
    delay(1000);  
}  
```  

## 4. 测试结果  

按照上图接好线，烧录好代码，上电后，舵机将从0度转到180度，再从180度转动到0度。


