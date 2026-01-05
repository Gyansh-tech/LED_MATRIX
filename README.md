# LED_MATRIX
Contains Essential Functions(Custom and Essential) for controlling LED Dot Matrix Displays with the MAX7221 and MAX7219 drivers. This also includes methods to draw words, numbers(with dp if needed), letters, based on custom fonts, along with other control essentials and the capability to draw custom symbols. 

Things to keep in Mind:
While creating the object for the library, 4 parameters need to be defined.
ex:
#include <LED_MATRIX.h>
LED_MATRIX display(1,2,3,5); // Params: DIN, CLK, CS, No. of Devices. Note: No of Devices can range till a maximum of 8, and minimum of 1;

The method draw_Word() accepts a pointer to a char array/ string as param: 
ex, :
draw_Word('HELLO'); // Note, use single quotes, not double.
or
char Word[4] = {'H','E','L','L','O'}; or char Word[4] = {'H','E','L','L','O'};

If not using all Letter Slots, please add \0 terminator at the end. You can also add spaces between Words.

Essential Methods provided include :

  void begin();
  void drawLetter(char letter, int matrix);
  void drawNumber(int num, bool dp_present, int dp); // if DP is not present, put the param as false and dp as 0;
  void draw_Word(char Word[]);
  void drawByte(byte Symbol[], int matrix);
  void draw_RedLight();
  void draw_Crosses();
  void clear();
  void clear(int matrix);
  void setBrightness(int matrix, int brightness);
  void set_collective_brightness(int brightness);
  void toggle_LED(int matrix, int row, int column, bool state);
  void setColumn(int addr, int col, byte value);
  void setRow(int addr, int row, byte value);
  void setDigit(int addr, int digit, byte value, boolean dp);
  void turnOff();
  void turnOff(int matrix);

  //
