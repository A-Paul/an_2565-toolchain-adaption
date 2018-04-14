PATH_SRC := ./

MCU   := atmega328p
F_CPU := 16000000

CC = avr-gcc
CFLAGS += -Wall -std=c99 -Os
CFLAGS += -mmcu=${MCU} -DF_CPU=${F_CPU}
CFLAGS_DEBUG += -g -DDEBUG
#CFLAGS += -I/usr/lib/avr/include 
#CFLAGS += -save-temps

OBJCOPY = avr-objcopy
RM = rm -vf --

TARGET = i2c-slave
OBJECTS = main.o TWI_Slave.o

all: image_hex

image_elf: $(TARGET).elf

$(TARGET).elf: $(OBJECTS)
	@$(CC) $(CFLAGS) -o $@ $^
	avr-size -C  $@

image_hex: $(TARGET).hex

$(TARGET).hex: $(TARGET).elf
	@$(OBJCOPY) --verbose -j .text -j .data -O ihex $< $@


./%.o: $(PATH_SRC)/%.c
	@$(CC) $(CFLAGS) -c -o $@ $<

./%.o: $(PATH_SRC)/%.c $(PATH_SRC)/%.h
	@$(CC) $(CFLAGS) -c -o $@ $<

.PHONY: clean

clean:
	$(RM) $(TARGET).elf $(TARGET).hex $(OBJECTS) *~
