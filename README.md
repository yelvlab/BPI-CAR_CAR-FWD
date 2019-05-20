# BPI-BIT CAR (Four Wheel Drive)

设计过程记录：[如何给BPI-BIT设计一个扩展板(指导向)](https://blog.yelvlab.cn/archives/458/)

### 电机对应PCA9685通道
|电机|PCA9685通道编号|
|:--|:--:|
|左前|CH12 CH13|
|右前|CH14 CH15|
|左后|CH08 CH09|
|右后|CH10 CH11|

### 如何控制电机
通常电机都会采用PWM(脉冲宽度调制)方式控制，这种方式简单来说呢就是在直流电机的两条线中的一条给一个低(或者高)电平，而另一条线给一个固定频率、指定占空比的方波信号，当然占空比是什么请字行学习，这个方波信号中的高(或者低)电平部分就会和零一条线产生压差，这样电机就会转动，而低(或者高)电平部分就没有压差，也就相当于没有给电机供电，这样电机实际工作的时间就和占空比一致，占空比越高实际工作时间就越长，电机速度就越快。

### PCA9685驱动库
PCA9685是一块I2C扩展16路PWM信号的芯片。它的应用也很多，避免重复造轮子，我们直接使用Adafruit家的开源库即可。
[Adafruit_Python_PCA9685](https://github.com/adafruit/Adafruit_Python_PCA9685)
[micropython-adafruit-pca9685](https://github.com/adafruit/micropython-adafruit-pca9685)
[Adafruit-PWM-Servo-Driver-Library(Adafruit_Arduino_PCA9685)](https://github.com/adafruit/Adafruit-PWM-Servo-Driver-Library)