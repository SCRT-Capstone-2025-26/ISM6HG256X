# ISM6HG256X
Arduino library to support the ISM6HG256X.

## API

This sensor uses I2C or SPI to communicate.
For I2C it is then required to create a TwoWire interface before accessing to the sensors:  

    TwoWire dev_i2c(I2C_SDA, I2C_SCL);  
    dev_i2c.begin();

For SPI it is then required to create a SPI interface before accessing to the sensors:  

    SPIClass dev_spi(SPI_MOSI, SPI_MISO, SPI_SCK);  
    dev_spi.begin();

An instance can be created and enabled when the I2C bus is used following the procedure below:  

    ISM6HG256XSensor sensor(&dev_i2c);
    sensor.begin();
    sensor.Enable_X();
    sensor.Enable_G();

An instance can be created and enabled when the SPI bus is used following the procedure below:  

    ISM6HG256XSensor sensor(&dev_spi, CS_PIN);  
    sensor.begin();
    sensor.Enable_X();
    sensor.Enable_G();

The access to the sensor values is done as explained below:  

    ISM6HG256X_Axes_t accel, angrate;
    sensor.Get_X_Axes(accel);
    sensor.Get_G_Axes(&angrate);  

## Examples

* ISM6HG256X_DataLog_Terminal: This application shows how to get data from ISM6HG256X and print them on terminal.

* ISM6HG256X_6D_Orientation: This application shows how to use ISM6HG256X to find out the 6D orientation and display data on a hyperterminal.

* ISM6HG256X_Double_Tap_Detection: This application shows how to detect the double tap event using the ISM6HG256X.

* ISM6HG256X_FIFO_Polling: This application shows how to get data from FIFO in pooling mode and print them on terminal.

* ISM6HG256X_FIFO_Interrupt: This application shows how to get data from FIFO using interrupt and print them on terminal.

* ISM6HG256X_Free_Fall_Detection: This application shows how to detect the free fall event using the ISM6HG256X.

* ISM6HG256X_Pedometer: This application shows how to use ISM6HG256X to count steps.

* ISM6HG256X_Single_Tap_Detection: This application shows how to detect the single tap event using the ISM6HG256X.

* ISM6HG256X_Tilt_Detection: This application shows how to detect the tilt event using the ISM6HG256X.

* ISM6HG256X_Wake_Up_Detection: This application shows how to detect the wake-up event using the ISM6HG256X.

## Documentation

You can find the source files at  
https://github.com/stm32duino/ISM6HG256X

The ISM6HG256X datasheet is available at  
https://www.st.com/content/st_com/en/products/mems-and-sensors/accelerometers/ISM6HG256X.html
