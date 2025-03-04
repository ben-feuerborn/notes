$T_{d} =$ Time Delay
$P_{s} =$ Prescaler
$f_{\text{clk}} =$ Clock Frequency
$\text{OCR0A} =$ Number of Counts

$$
T_{d} = \frac{\text{OCR0A} \times P_{s}}{f_{\text{clk}}}
$$

Clock Select Bit Description

| `CSn2` | `CSn1` | `CSn0` | Definition | Description |
| :---: | :---: | :---: | :--- | :--- |
| 0 | 0 | 0 | No clock Source  (Timer/Counter stopped) | Uses the connected clock, or if no clock connected, timer is off |
| 0 | 0 | 1 | $\text{clk}_{I/O}/1$ (No prescaling) | Regular system clock |
| 0 | 1 | 0 | $\text{clk}_{I/O}/8$ (From prescaler) | Available prescaler |
| 0 | 1 | 1 | $\text{clk}_{I/O}/64$ (From prescaler) | Available prescaler |
| 1 | 0 | 0 | $\text{clk}_{I/O}/256$ (From prescaler) | Available prescaler |
| 1 | 0 | 1 | $\text{clk}_{I/O}/1024$ (From prescaler) | Available prescaler |
| 1 | 1 | 0 | External clock source on `T0` pin. Clock on falling edge. | Other signal can be connected and used |
| 1 | 1 | 1 | External clock source on `T0` pin. Clock on rising edge. | Other signal can be connected and used |


8-bit timers: 0 and 2
16-bit timers: 1, 3, 4, and 5

## Timer 0 (8-bit)
Setting up Timer 0 for a millisecond delay using CTC mode
```cpp
void initTimer0() {
    /*
        for a millisecond timer:
        prescaler = 64 (CSn = 011)
        OCRnA = 249
    */

    // configure Timer0 in CTC mode
    // WGM0 = 010 for CTC mode
    TCCR0B &= ~(1 << WGM02); // 0
    TCCR0A &= ~(1 << WGM01); // 0
    TCCR0A |= (1 << WGM00);  // 1

    // define the prescaler
    // 64 prescaler (CS0 = 011)
    TCCR0B &= ~(1 << CS02);  // 0
    TCCR0B |= (1 << CS01);   // 1
    TCCR0B |= (1 << CS00);   // 1

    // define the output compare register
    OCR0A = 249;
}

void delayMs(unsigned int delay) {
    unsigned int delayCount = 0;

    while (delayCount < delay) {
    
    }
}
```

## Timer n (16-bit)
Setting up a Timer n (in this example 1) for microsecond delay using CTC mode
```cpp
void initTimer1() {
    /*
        for a microsecond timer:
        prescaler = 1 (CSn = 001)
        OCRnA = 15
    */

    // configure Timer1 in CTC mode
    // WGM1 = 0100 for CTC mode
    TCCR1B &= ~(1 << WGM13); // 0
    TCCR1B |= (1 << WGM12);  // 1
    TCCR1A &= ~(1 << WGM11); // 0
    TCCR1A &= ~(1 << WGM10); // 0

    // define the prescaler
    // no prescaler (CS1 = 001)
    TCCR1B &= ~(1 << CS12);  // 0
    TCCR1B &= ~(1 << CS11);  // 0
    TCCR1B |= (1 << CS10);   // 1

    // define the output compare register
    // OCRn is 16 bits, so we need to define both high and low bits
    OCR1AH = 0;
    OCR1AL = 15;
}

void delayUs(unsigned int delay) {
    unsigned int delayCount = 0;

    while (delayCount < delay) {
    
    }
}
```