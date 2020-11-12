# I2C-Verilog
Verilog Code for I2C Protocol
All codes have been written in Xilinx
Details can be found at 
*****
http://www.shashisuman.com/2017/04/i2c-verilog-code.html

****
An I2C basically consists of a master micro controller and a slave device which responds to the requests of the master. A slave cannot operate on its own. It can't even communicate with other slave without having nay permission from the master.
You may have come across multi master schematic but it become much more complex to handle such situation because of data leakage and also it requires more than 1 micro controllers. So if you are using an I2C you cannot use any other non-I2C device on the same bus as bothe SDA and SCL lines are in conjunction with the I2C module. If you find this facility somewhere you are being fooled seriously !!!
 I2C works on 2 signals as SCL and SDA
                                           SCL - Serial Clock
                                           SDA- Serial Data 
When SDA is having negedge and SCL is positive level triggered then we have start signal and with every SCL clock a bit is transferred. Combining up to eight bit the slave receives an address. Then come the R/W signal means whether the slave has to read or write from/to address. AT the very moment after R/W bit the last bit known as acknowledgement bit is sent. Then the slave sends bit by bit data and finalizing by the acknowledge bit and the process comes to a STOP.

Do remember that when SDA changes the SCL lines must remain stable hence SDA doesn't change at posedge or nedge of SCL and only on the level of SCL i.e. either 1 or 0.

**Terminologies**

clk = Normal clock
sda = serial data
scl = serial clock
data_wr = data that has to be written if rw = 0;
address = address of slave
register = address of register which has to be read
rw = read or write pin

temp = to copy address incoming
register2 = to copy register value
scl2x = clock with which sda works to change sda while scl is 0
i = internal counter
n = single counter for start and stop conditions




