Write Character
```cpp
void writeCharacter() {

}
```

Write String
```cpp
void writeString(const char *string) {
    while (*string != '\0') {
        writeCharacter(*string);
        string++;
    }
}
```

Move Cursor
```cpp
// x is the
// y is the 
void moveCursor(unsigned char x, unsigned char y) {
    // DDRAMaddress = (0x80) | (x << 6) | (y);
    eightBitCommandWithDelay((0x80) | (x << 6) | (y), 53);
}
```

Custom Characters
```cpp
// in main
setCGRAM(0x40);

void setCGRAM
```