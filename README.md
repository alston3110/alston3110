# mcu test code
<p>
	this repository is the source code for lpuart tests.
</p>

## Project Name & Folder
	SDK_fpga_test

## Test iteam 2
- uar0 loopback test,
	- uart0 rx operation until character "\n" is received
	- uart0 tx send string "TAIWON_1234567890\n"
	- compare rx data with original data
- lpuart configuration :
```
const uart_user_config_t LPUART_0_uart_pal_config0 = {
  .baudRate = 115200UL,
  .parityMode = UART_PARITY_DISABLED,
  .bitCount = UART_8_BITS_PER_CHAR,
  .stopBitCount = UART_TWO_STOP_BIT,
  .transferType = UART_USING_INTERRUPTS,
  .rxDMAChannel = 2UL,
  .txDMAChannel = 0UL,
  .rxCallback = rx0Callback,
  .rxCallbackParam = NULL,
  .txCallback = NULL,
  .txCallbackParam = NULL,
  .extension = NULL
};
const uart_user_config_t LPUART_1_uart_pal_config0 = {
  .baudRate = 115200UL,
  .parityMode = UART_PARITY_DISABLED,
  .bitCount = UART_8_BITS_PER_CHAR,
  .stopBitCount = UART_ONE_STOP_BIT,
  .transferType = UART_USING_INTERRUPTS,
  .rxDMAChannel = 1UL,
  .txDMAChannel = 3UL,
  .rxCallback = rx1Callback,
  .rxCallbackParam = NULL,
  .txCallback = NULL,
  .txCallbackParam = NULL,
  .extension = NULL
};
```
- check console

<img src="https://https://github.com/alston3110/test/blob/main/pattern1.png">

## Communication interface
- test port : UART0, baud rate 115200
- console port : UART1, baud rate 115200

## Console message
```
DATA match/Total = 1/1 times
DATA match/Total = 2/2 times
DATA match/Total = 3/3 times
DATA match/Total = 4/4 times
DATA match/Total = 5/5 times
DATA match/Total = 6/6 times
DATA match/Total = 7/7 times
DATA match/Total = 8/8 times
DATA match/Total = 9/9 times
DATA match/Total = 10/10 times
...
DATA match/Total = 991/991 times
DATA match/Total = 992/992 times
DATA match/Total = 993/993 times
DATA match/Total = 994/994 times
DATA match/Total = 995/995 times
DATA match/Total = 996/996 times
DATA match/Total = 997/997 times
DATA match/Total = 998/998 times
DATA match/Total = 999/999 times
DATA match/Total = 1000/1000 times
End of test uart
```

