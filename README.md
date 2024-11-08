This is an SSPI CRAM programming implementation of ice40 Ultralite using STM32

I used STM32's built-in HAL library for GPIO control and SPI bus communication.Unlike the previous example on the Raspberry Pi, where the array was divided into chunks before being sent to the driver, the STM32 HAL automatically handles data transmission in 4-byte (32-bit) chunks.

The instructions used for programming for this example is taken from FPGA-TN-02001-3.4( [ice40 Programming and Configuration](https://www.latticesemi.com/view_document?document_id=46502)) technical note. See below for the waveform instructions from the document.
![image](https://github.com/user-attachments/assets/d2f8afd1-0711-4ea5-af9f-bec0dd8c61b2)

In this implementation you can modify the array in data.c with your own bitstream. 
![image](https://github.com/user-attachments/assets/b7d6c45a-c028-4559-ae0d-efc05de4a22c)

The whole programmign process fits it only a few lines of codes using STM32 built in library.

![image](https://github.com/user-attachments/assets/25a0e989-3c99-4ed5-934a-36a2e1854f69)


See sample transactions below:
![image](https://github.com/user-attachments/assets/4acb897c-8715-405a-9849-af59c747271c)


![image](https://github.com/user-attachments/assets/1f89b301-61ad-4cc5-a2d0-a3b4c03e9a71)

For ice40UL, its bitstream can fit in the internal flash of my STM32F411 Discovery board. My board  has 512 kB of Flash memory while the bitstream is only around 30 kB. 

When using devices with higher density, an external memory might be needed such as an SPI Flash.
