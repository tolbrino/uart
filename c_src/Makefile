PRIVDIR := ../priv

all : $(PRIVDIR)/uart_drv.so

override CFLAGS += -DDLOG_DEFAULT=DLOG_NONE -fpic -shared -I ../../../erlang-dthread-*/git/include/

# OBJ := dosmap.o  uart_drv.o uart_modem_state.o uart_unix.o uart_buf.o uart_ftdi.o uart_options.o uart_com_state.o uart_message.o uart_queue.o
OBJ := uart_drv.o uart_modem_state.o uart_unix.o uart_buf.o uart_options.o uart_com_state.o uart_message.o uart_queue.o


$(PRIVDIR)/uart_drv.so : $(OBJ)
	$(CC) -shared -fpic $(LDFLAGS) \
	../../../erlang-dthread-*/git/c_src/dthread.o \
	../../../erlang-dthread-*/git/c_src/dlib.o \
	../../../erlang-dthread-*/git/c_src/dterm.o \
	 -lutil -o $@ $^

clean:
	$(RM) -f $(PRIVDIR)/uart_drv.so $(OBJ)
