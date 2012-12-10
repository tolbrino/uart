PRIVDIR := ../priv

all : $(PRIVDIR)/uart_drv.so

override CFLAGS += -fpic -shared

OBJ := dosmap.o  uart_drv.o uart_modem_state.o uart_unix.o uart_buf.o uart_ftdi.o uart_options.o uart_win32.o uart_com_state.o uart_message.o uart_queue.o


$(PRIVDIR)/uart_drv.so : $(OBJ)
	$(CC) -shared -fpic $(LDFLAGS) -o $@ $^

clean:
	$(RM) -f $(PRIVDIR)/uart_drv.so $(OBJ)
