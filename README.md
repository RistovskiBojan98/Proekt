# MemoryGame
Проект направен со Windows forms од Душко Брезовски, Бојан Ристовски и Филип Поповски.

## Опис
Ние одлучивме да ја рекреираме многу познатата игра **Memory Match game** во која освен основните функционалности, за подобро искуство на играчот додадовме повеќе нивоа, секое со различни опции за тежина. Имплементиравме едноставен дизајн во кој сите елементи се јасно покажани.

## Правила на играта
При старт на играта се отвара едно мени во кое се одбира кое ниво ќе се игра.


![Слика1](https://i.imgur.com/SuYnDLB.png)


По селетирање на ниво се крие почетното мени и се уклучува соодветното ниво каде се чека селектирање на тежина.Има три различни тежини, каде потежките имаат помалку време за победување.

![Слика2](https://i.imgur.com/QQqowXY.png)


Секоја од тежините е прилагодена за соодветното ниво каде што се користи.Тие се:
* Easy (лесно)
* Medium (средно)
* Hard (тешко)
После селекција на тежина играта почнува, а со тоа и тајмерот. На почеток сите слики се сокриени и играчот одбира две слики и селектираните слики се превртуваат. Ако се исти сликите остануваат превртени до крајот на играта и се оневозможува повторен клик и се зголемува бројот на поени. Во спротивно остануваат превртени одредено време и потоа се враќаат назад.
Играта трае додека не се погодат сите парови или не снема време. Играчот добива соодветн порака во зависност дали победил или снемал време(а има и посебна порака ако на најтешката тежина победи). Откако заврши играта се овозможува повторно почнување на играта или при гасење на тој прозорец се враќа на првичниот прозорец каде играчот може да одбере друго ниво или да ја изгаси играта. 


![Слика3](https://i.imgur.com/qHUZZyB.png)


## Претставување на играта
Секое ниво како и почетното мени претставуваат различен```Form() ``` и главните компоненти на играта(сликите кои се кликаат) се ```Picuturebox()``` и се чува во вид на низа што олеснува рандомизација. За пополнување на низата се чува инферфејс ```Ienumerable<Image>``` кој ги содржи сликите кои ќе бидат користени.
```c#
public partial class Level3 : Form

private PictureBox[] pictureBoxes

private static IEnumerable<Image> images
```

## Функции
При клик за одбирање на тежина се повикува функцијата ```start()``` при што се доделуваат соодветни параметри според одбраната тежина. Таа функција ги ресетира сите слики и променливи и ја почнува играта.
Функцијата ```getEmpty()``` враќа слободен ```Picturebox``` (за слободен се смета оној кој вредноста на ```Tag``` е null).
Функцијата ```Randomize()``` со повикување на функцијата ```getEmpty()``` два пати за секоја слика ја пополнува низата и може да започне играта.
