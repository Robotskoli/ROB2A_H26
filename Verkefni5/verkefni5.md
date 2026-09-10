QRcode / AprilTag,  vægi 15% af loka einkunn

***AprilTag***

Lesið allt í lesefni áður en þið byrjið verkefnið það er nauðsynlegt að þið skiljið efnið og tækin sem þið eruð að vinna með.

Lesefni:
- [AI Vision](https://kb.vex.com/hc/en-us/articles/24616769643924-Coding-with-the-AI-Vision-Sensor-in-VEXcode-V5-C#id-header-4)
- [AprilTag](https://api.vex.com/v5/home/cpp/Smart_Port_Devices/AI_Vision_Sensor.html)


Vægi þátta:
1. Sýna kennara að allt virkar 30 stig
1. Kóði 30 stig
1. Virkni (myndband) 40 stig

#### Sýna kennara
1. Farið í Brain og devices veljið port sem þið tengduð AI vision í veljið eitthvað AprilTag og setjið fyrir framan AI vision
hann á að sýna ID AprilTags.
1. Búið til V5 verkefni sem er tómt (empty template project), þið sjáið í Include er bara vex.h skrá og í src er main.cpp
   setjið þennan kóða í stað þess sem fyrir er:
```c++
   /*----------------------------------------------------------------------------*/
/*                                                                            */
/*    Module:       main.cpp                                                  */
/*    Author:       ebe                                                       */
/*    Created:      9/10/2026, 7:37:24 AM                                     */
/*    Description:  V5 project                                                */
/*                                                                            */
/*----------------------------------------------------------------------------*/
#include "vex.h"

using namespace vex;

// A global instance of vex::brain used for printing to the V5 brain screen
vex::brain       Brain;

vex::aivision AIVision1(PORT1, aivision::ALL_TAGS, aivision::ALL_AIOBJS);


// define your global instances of motors and other devices here


int main() {


   
    while(1) {
         Brain.Screen.clearScreen();
    Brain.Screen.setCursor(1, 1);
    // Take a snapshot of all AprilTags.
    AIVision1.takeSnapshot(aivision::ALL_TAGS);
    // Check to see if an AprilTag exists in this snapshot.
    if (AIVision1.objectCount > 0) {
      // Determine which AprilTag is detected.
      if (AIVision1.objects[0].id == static_cast<int>(1.0)) {
        // Conditional based on finding TagID #1.
        Brain.Screen.print("Found TagID 1");
      } else if (AIVision1.objects[0].id == static_cast<int>(2.0)) {
        // Conditional based on finding TagID #2.
        Brain.Screen.print("Fann TagID 2");
      } else {
        // Else condition will print any other TagID found.
        Brain.Screen.print("Fann TagID");
        Brain.Screen.newLine();
        Brain.Screen.print("TagID: ");
        Brain.Screen.print(static_cast<float>(AIVision1.objects[0].id));
      }
    }
    else {
      // If no AprilTags are found in this snapshot, display a message.
      Brain.Screen.print("Ekkert AprilTag");
    }
    // Wait some time and restart loop.
    wait(0.3, seconds);
  wait(5, msec);
  }
  return 0;

    
}
```



### Reikna lyftigetu arma

Dæmi:

Rauður mótor vex V5 torq 2,1Nm breyti yfir í kgcm 21kgcm þettar er án gíra í armi
1. ef armur er 10 cm langur þá er lyftigetan  21kg / 10 = 2,1 kg
1. ef armur er 45 cm þá er lyftigetan 21kgcm / 45 =  0,46 kg
í armi er tannhjól m 12T og annað 48T 48T / 12T  = 4 sinnum meira torq og 4 sinnum minni hraði
ef við erum með 45cm arm og rauðan mótor 0,46kg x 4 þá er lyftigetan 1,86 kg (stall) og til að vera örugg með að eyðileggja ekki mótor
þá deilum við með 2 eða 0,933 kg

sýnið ykkar útreikninga á lyfrigetu þ.e með grænum mótor og mælið ykkar arm og tannhjól sem tengjast armi.
Finnið hlut sem er jafn þungur og reiknuð lyftigeta arms og látið vélmennið lyfta, takið video af því og skilið.

Hér eftir skulu öll verkefni vera þannig að hægt sé að stöðva vélmenni með því að þrýsta á einhvern takka á fjarstýringu og neyðarrofa á vélmenni.

