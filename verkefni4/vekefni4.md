Fylgja línu,  vægi 15% af loka einkunn

***Linsensor linetracking***

Lesið allt í lesefni áður en þið byrjið verkefnið það er nauðsynlegt að þið skiljið efnið og tækin sem þið eruð að vinna með.

Lesefni:
- [Linesensor](https://kb.vex.com/hc/en-us/articles/360039287611-Using-the-V5-3-Wire-Line-Tracker)


Vægi þátta:
1. Kóði 30 stig
1. Flæðirit og eða sauðakóða 20 stig
1. Virkni (myndband) 40 stig
2. Reikna lyftigetu arms 10 stig

Róbot á að fylgja línu sem er sett á golfið.
Setjið upp línu-sensora, þeir eru 3, notið sample program- Line followe Triple Sensor line tracking til að koma ykkur af stað og UltraSonic  Range Modul. 
Skoðið þetta dæmi **Line Tracking**.
Gerið sér task sem birtir á skjá hvort vélmennið er hægrimegin, vinstrimegin eða á miðju línu og ef engin lína þá birtist
**"Leita af línu"** Gerið ráðstafanir svo vélmennið finni línuna aftur má vera sér task :-)
- Byrjið á því að gera sauðakóða og eða flæðirit https://www.draw.io/. þegar búið farið í  File-export as - image .png
- Gerið kóða í samræmi við sauðakóða/flæðirit og vistið á github
- Takið upp video og setjið tengil í það á github (t.d youtube).
- Skilið sló af github ykkar í Innu verkefni 4

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

