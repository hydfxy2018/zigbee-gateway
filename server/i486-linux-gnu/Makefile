
SBU_REV= "0.1"

GCC=gcc

CFLAGS = -Wall -DVERSION_NUMBER=${SBU_REV}
OBJECTS = zbSocController.o zbSocCmd.o interface_devicelist.o interface_grouplist.o interface_scenelist.o interface_srpcserver.o socket_server.o SimpleDB.o SimpleDBTxt.o
LIBS = -lrt -lcurses

DEFS += -D_GNU_SOURCE -DxHAL_UART_SPI

APP_NAME=zbGateway.bin

.PHONY: all, clean

${APP_NAME}: ${OBJECTS}
	$(GCC) $(CFLAGS) $(OBJECTS) $(LIBS) -o ${APP_NAME}

%.o: ../Source/%.c
	${GCC} ${CFLAGS} ${INCLUDE} ${DEFS} -c -o $@ $<

all: ${APP_NAME}

clean:
	rm -rf *.o ${APP_NAME}
