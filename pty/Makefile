ROOT=..
PLATFORM=$(shell $(ROOT)/systype.sh)
include $(ROOT)/Make.defines.$(PLATFORM)

ifeq "$(PLATFORM)" "solaris"
  EXTRALIBS=-lsocket -lnsl
endif

PROGS =	pty

all:	$(PROGS)

$(PROGS):	$(LIBAPUE)

pty:	main.o loop.o driver.o
	$(CC) $(CFLAGS) -o pty main.o loop.o driver.o $(LDFLAGS) $(LDLIBS)

clean:
	rm -f $(PROGS) $(TEMPFILES) *.o

include $(ROOT)/Make.libapue.inc
