#include <FEHLCD.h>
//#include <FEHIO.h>
#include <stdio.h>
#include <FEHUtility.h>
#define YMAX 240;
#define BUTTONTEXT "Play Game"
#define BUTTON2TEXT "Stats"
#define BUTTON3TEXT "Instructions"
#define BUTTON4TEXT "Credits"
 
class Avatar{
private:
   int a, b;
public:
   Avatar(int, int);
   void DrawAvatar();
   void AvatarMoveDown();
   void AvatarMoveUp();
   void DrawBase(int, int);
   void DrawBackground();
   void DrawBackground2();
   void DrawBackground3();
   void DrawTree(int, int, int, int);
   void DrawCloud(int, int, int);
};
 
 
void button();
 
void PlayGame(Avatar*);
void ButtonTouch(Avatar*);
void DrawCar(int, int, int, int);
void MoveCar1(Avatar*, int);
void DrawMenu(Avatar*);
void PlayGame();
void ShowStats();
void Instructions();
void Credits();
 
int main()
{
float x,y;
Avatar Avatar1(170,210);
while(true){
DrawMenu(&Avatar1);
while (!LCD.Touch(&x,&y)) {
   // Screen is not being touched
}
LCD.ClearBuffer();
   if (y>=0 && y<60) {
       LCD.Update();
       PlayGame(&Avatar1);
       Sleep(1.0);
        while (!LCD.Touch(&x,&y)) {
   // Screen is not being touched
}
LCD.Clear();
DrawMenu(&Avatar1);
   }
   else if (y>=60 && y< 120) {
       ShowStats();
       Sleep(1.0);
       while (!LCD.Touch(&x,&y)) {
// Screen is not being touched
}
LCD.Clear();
DrawMenu(&Avatar1);
   }
   else if (y>=120 && y< 180) {
       Instructions();
       Sleep(1.0);
        while (!LCD.Touch(&x,&y)) {
   // Screen is not being touched
}
LCD.Clear();
DrawMenu(&Avatar1);
   }
   else {
       Credits();
       Sleep(1.0);
        while (!LCD.Touch(&x,&y)) {
   // Screen is not being touched
}
LCD.Clear();
DrawMenu(&Avatar1);
   }
}
while (true){
   LCD.Update();
}
return 0;
}
void DrawMenu(Avatar *Avatar1) {
   LCD.SetFontColor(TURQUOISE);
   LCD.FillRectangle(0,0,319,239);
   LCD.SetFontColor(ORANGE);
   LCD.FillRectangle(80,12,170,30);
   LCD.FillRectangle(80,72,170,30);
   LCD.FillRectangle(80,132,170,30);
   LCD.FillRectangle(80,192,170,30);
   LCD.SetFontColor(BLACK);
   LCD.DrawRectangle(80,12,170,30);
   LCD.DrawRectangle(80,72,170,30);
   LCD.DrawRectangle(80,132,170,30);
   LCD.DrawRectangle(80,192,170,30);
   LCD.SetFontColor(DARKVIOLET);
   LCD.WriteAt("Play Game", 110, 22);
   LCD.WriteAt("Instructions", 90, 82);
   LCD.WriteAt("Stats", 130, 142);
   LCD.WriteAt("Credits", 120, 202);
   Avatar1->DrawCloud(20,30,WHITESMOKE);
   Avatar1->DrawCloud(20, 170, WHITESMOKE);
   Avatar1->DrawCloud(290, 40, WHITESMOKE);
   Avatar1->DrawCloud(290, 200, WHITESMOKE);
   DrawCar(20,100,CRIMSON,TURQUOISE);
   DrawCar(270,130,CRIMSON,TURQUOISE);
}
void ShowStats() {
 
   LCD.WriteLine("Stats");
}
void PlayGame(Avatar *Avatar1){
  
   int i;
 
   LCD.WriteLine("Play Game");
   LCD.Clear();
   Avatar1->DrawBackground3();
   button();
   Avatar1->DrawAvatar();
   for (i=0;i<10000; i=i+5)
  {
   MoveCar1(Avatar1, i);
   ButtonTouch(Avatar1);
  }
 
}
void Instructions(){
   LCD.WriteLine("Instructions");
}
void Credits(){
   LCD.WriteLine("Credits");
}
 
 
 
 
 
void Avatar::DrawBackground(){
   DrawBase(CORNFLOWERBLUE, SPRINGGREEN);
   DrawTree(50,50,BLACK,FORESTGREEN);
   DrawTree(290,50,BLACK,FORESTGREEN);
   DrawTree(20,190,BLACK,FORESTGREEN);
   DrawTree(230,115,BLACK,FORESTGREEN);
   DrawTree(90,115,BLACK,FORESTGREEN);
   DrawCloud(20,20,WHITE);
   DrawCloud(100,20,WHITE);
   DrawCloud(190,20,WHITE);
}
 
void Avatar::DrawBase(int a, int b){
   int i;
   LCD.SetFontColor(a);
   LCD.FillRectangle(0,0,320,32);
   LCD.SetFontColor(b);
   LCD.FillRectangle(0,32,320,34);
    LCD.SetFontColor(DIMGRAY);
   LCD.FillRectangle(0,66,320,32);
   LCD.SetFontColor(b);
   LCD.FillRectangle(0,98,320,34);
   LCD.SetFontColor(DIMGRAY);
   LCD.FillRectangle(0,132,320,32);
   LCD.SetFontColor(b);
   LCD.FillRectangle(0,164,320,75);
   for (i = 20; i<280; i=i+20){
   LCD.SetFontColor(GHOSTWHITE);
   LCD.DrawLine(i+20,148,i+30,148); 
   }
   for (i = 20; i<280; i=i+20){
   LCD.SetFontColor(GHOSTWHITE);
   LCD.DrawLine(i+20,82,i+30,82); 
   }
}
 
void button(){
   LCD.SetFontColor(SLATEBLUE);
   LCD.FillRectangle(270,210,20,20);
   LCD.FillRectangle(270,180,20,20);
   LCD.SetFontColor(BLACK);
   LCD.DrawRectangle(270,210,20,20);
   LCD.DrawRectangle(270,180,20,20);
}
 
void Avatar::DrawAvatar(){
LCD.SetFontColor(PLUM);
LCD.FillCircle(a,b,7);
LCD.SetFontColor(BLACK);
LCD.DrawCircle(a,b,7);
LCD.SetFontColor(PLUM);
LCD.FillRectangle(a-3,b+7,6,8);
LCD.SetFontColor(BLACK);
LCD.DrawRectangle(a-3,b+7,6,8);
LCD.DrawHorizontalLine(b+10,a+3,a+6);
LCD.DrawHorizontalLine(b+10,a-3,a-6);
LCD.DrawLine(a+2,b+15,a+6,b+19);
LCD.DrawLine(a-2,b+15,a-6,b+19);
}
 
void Avatar::DrawCloud(int a,int b, int c){
LCD.SetFontColor(c);
LCD.FillCircle(a,b,9);
LCD.FillCircle(a+15,b,7);
LCD.FillCircle(a+6,b-9,8);
}
 
void Avatar::DrawTree(int a,int b, int c, int d){
   LCD.SetFontColor(SIENNA);
   LCD.FillRectangle(a,b,10,15);
   LCD.SetFontColor(c);
   LCD.DrawRectangle(a,b,10,15);
   LCD.SetFontColor(d);
   LCD.FillRectangle(a-5,b-8,20,8);
   LCD.SetFontColor(c);
   LCD.DrawRectangle(a-5,b-8,20,8);
   LCD.SetFontColor(d);
   LCD.FillRectangle(a,b-13,10,5);
   LCD.SetFontColor(c);
   LCD.DrawRectangle(a,b-13,10,5);
}
 
void ButtonTouch(Avatar *Avatar1) {
   float x, y;
   if(LCD.Touch(&x,&y)){
       printf("1\n");
     if(y>=180 && y<=200) {
         printf("2\n");
       if (x>=270 && x<=290) {
           Avatar1->AvatarMoveUp();
           Sleep(500);
       }
   }
   else if (y>=210 && y<=230) {
       if (x>=270 && x<=290){
           Avatar1->AvatarMoveDown();
           Sleep(500);
   }
   }
   else {
       Avatar1->DrawBackground3();
       Avatar1->DrawAvatar();
   }
  
}
LCD.Update();
}
 
void Avatar::AvatarMoveUp(){
   DrawBackground3();
    b=b-12;
   DrawAvatar();
   LCD.Update();
 
}
void Avatar::AvatarMoveDown(){
   DrawBackground3();
   b=b+12;
   DrawAvatar();
   LCD.Update();
}
 
 
void Avatar::DrawBackground2(){
   DrawBase(DARKSLATEBLUE, DARKGREEN);
   DrawTree(50,50,BLACK,ORANGERED);
   DrawTree(290,50,BLACK,ORANGERED);
   DrawTree(20,190,BLACK,ORANGE);
   DrawTree(230,115,BLACK,SCARLET);
   DrawTree(90,115,BLACK,SCARLET);
   DrawCloud(20,20,WHITESMOKE);
   DrawCloud(100,20,WHITESMOKE);
   DrawCloud(190,20,WHITESMOKE);
}
void Avatar::DrawBackground3(){
   DrawBase(MIDNIGHTBLUE, DARKRED);
   DrawTree(70,50,BLACK,OLIVE);
   DrawTree(260,50,BLACK,OLIVE);
   DrawTree(30,190,BLACK,OLIVEDRAB);
   DrawTree(200,115,BLACK,PURPLE);
   DrawTree(80,115,BLACK,PURPLE);
   DrawCloud(20,20,WHITESMOKE);
   DrawCloud(100,20,WHITESMOKE);
   DrawCloud(190,20,WHITESMOKE);
}
 
 
void DrawCar(int a, int b, int c, int d){
LCD.SetFontColor(BLACK);
LCD.FillCircle(a+6,b+16,4);
LCD.FillCircle(a+24,b+16,4);
LCD.SetFontColor(c);
LCD.FillRectangle(a,b,30,15);
LCD.SetFontColor(c);
LCD.FillRectangle(a+30,b+9,6,6);
LCD.SetFontColor(d);
LCD.FillRectangle(a+21,b+5,5,3);
LCD.Update();
}
 
void MoveCar1(Avatar *Avatar1,int i){
 
  
     DrawCar(2+i,136,PURPLE,WHITESMOKE);
     DrawCar(2+i,70,PURPLE,WHITESMOKE);
     Sleep(150);
     Avatar1->DrawBackground3();
     button();
     Avatar1->DrawAvatar();
     Sleep(1);
 
  
  
  
 
}
 
Avatar::Avatar(int c, int d)
{
   a=c;
   b=d;
}
