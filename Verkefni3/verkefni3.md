**Sonar og lightsensor vægi 10% af loka einkunn**

Munið að hafa alltaf rúðustrikaða verkefnabók þar sem þið byrjið á að teikna þrautina (vandamálið) til að gera ykkur grein fyrir því, takið síðan mynd og setjið á git í viðeigandi verkefnamöppu. Gerið síðan sauðakóða þ.e lýsingu á því hvernig þið leysið það.

## Keyra án þess að rekast á 50 stig

Lesið allt i Lesefni áður en þið hefjið verkefnið

Lesefni:
- [Ultrasonic-RangeFinder](https://kb.vex.com/hc/en-us/articles/360038608771-Using-the-V5-3-Wire-UltraSonic-Range-Finder)
- [LightSensor](https://kb.vex.com/hc/en-us/articles/360039338891-Using-the-V5-3-Wire-Light-Sensor)

Vægi þátta:
1. Kóði 20 stig
1. Flæðirit og eða sauðakóði 10 stig
1. Virkni (myndband) 20 stig

Sónar og lightsensor
Forritið vélmennið þannig að hann geti keyrt  endalaust um svæði án þess að rekast á aðra hluti, notið sónar og light sensor.  Forritið einnig lightsensor þannig að vélmennið fari af stað þegar ljós í stofu eru kveikt og stoppi ef slökkt. Buið til sér task sem sér um að birta heildarvegalengd (metrar) sem vélmennið hefur farið og meðalhraða(m/s) (nota timer og búa til föll sem reiknar þetta fyrir ykkur).
Hér eftir skulu öll verkefni vera þannig að hægt sé að stöðva vélmenni með því að þrýsta á einhvern takka á fjarstýringu og á vélmenni.
Gerið flæðiritið í http://draw.io þegar búið farið í  File-export as - image
Skilið video af vélmenni leysa allar þrautinar setjið á YouTube og skilið slóð á videóið í Innu
Skilið sauðakóða og eða flæðiriti https://www.draw.io/
#### Nýtið ykkur líka dæmi í vex C++ Detecting Distances og Detecting Light

## Finna lit hlutar og tengja vision við farsíma 20 stig

### krækja í vefútgáfu af Vex V5 til að stilla AI vision https://codev5.vex.com/
#### Ef myndavél virkar ekki prófið þá að sækja þennan rekil https://kb.vex.com/hc/en-us/articles/29372657581972-Installing-the-VEX-Drivers-Installer-for-VEX-V5

Lesið allt í lesefni áður en þið hefjið verkefni.
Ath að AI Vision tengist ekki síma með wifi ef þið eruð með AI Vision fylgið og lesið leiðbeiningar um AI vision í lesefni.

Lesefni
- [AI vision](https://kb.vex.com/hc/en-us/categories/360002333191-V5?sc=ai-vision-sensor)
- [Uppsetning og tenging á VisionSensor](https://kb.vex.com/hc/en-us/articles/360055918272--Connecting-the-V5-Vision-Sensor-to-a-Mobile-Device)
- [Festing á VisionSensor](https://kb.vex.com/hc/en-us/articles/360035954031-Mounting-and-Wiring-the-V5-Vision-Sensor)
- [Stillingar á VisionSensor](https://kb.vex.com/hc/en-us/articles/360035951911-Using-the-Vision-Utility-with-the-V5-Vision-Sensor)

Vægi þátta:
1. Kóði 10stig
1. Tengja vision við farsíma 5 stig
1. Virkni (myndband) 5 stig

Vision sensor er málið hér kynnið ykkur þetta **File - Open Turtorials - Configuring A VisionSensor**
og þetta **File - Open Turtorials - Tuning A Vision Sensor** . Nýtið ykkur svo þennan kóða **New Project-C++  -Select an Example Project - Detecting Objects(Vision)**
Skilið video af vélmenni leysa allar þrautinar setjið á YouTube og skilið slóð á videóið í repo
Hér er kóðin gefin en þið breytið þannig að öll skilaboð eru á íslensku. Sýnið kennara virkni vision og farsíma t.d keyra velmenni með fjarstýringu og nota farsíma hvert vélmennið er að fara.

## Vélmenni eltir hlut með ákveðin lit 30 stig
Vægi þátta:
1. Kóði 10stig
1. Flæðirit og eða sauðakóði 10 stig
1. Virkni (myndband) 10 stig

Notið vision sensor í kóðanum ykkar til að láta vélmenni elta hlut með ákveðin lit og stoppar ef hlutur er innan við 40 cm frá
og heldur áfram að elta ef meira en 40 cm. Vélmennið á að bakka ef of nálagt og stoppa og bíða ef engin hlutur er í sjónmáli.
Búið til sér task (thread) sem sér um að birta upplýsingar á skjá það sem vélmennið er að gera t.d beygi til hægri , fer áfram o.s.frv

#### dæmi um kóða
Ath þessi kóði er ókláraður og parametrar ekki fínstilltir hann er aðeins til að koma ykkur af stað
```C++
  const int CENTER_FOV =158;
  const int OFFSET_X = 15;
int main() {
  // Initializing Robot Configuration. DO NOT REMOVE!
  vexcodeInit();



  vexcodeInit();
  
  while(true){
    Brain.Screen.clearLine();
    Vision1.takeSnapshot(BLUE_2);
    if(Vision1.largestObject.exists){
      Brain.Screen.print(Vision1.largestObject.width);
      if(Vision1.largestObject.width < 50){
        RightMotor.spin(reverse);
        LeftMotor.spin(reverse);
      }
      else if(Vision1.largestObject.centerX > CENTER_FOV + OFFSET_X){
        RightMotor.spin(reverse);
        LeftMotor.spin(forward);
      }
      else if (Vision1.largestObject.centerX < CENTER_FOV - OFFSET_X) {
        RightMotor.spin(forward);
        LeftMotor.spin(reverse);
      }
      else{
        RightMotor.stop(brakeType::brake);
        LeftMotor.stop(brakeType::brake);
      }
  }
  
  }
}
```
