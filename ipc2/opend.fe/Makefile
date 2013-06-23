ROOT=../..
PLATFORM=$(shell $(ROOT)/systype.sh)
include $(ROOT)/Make.defines.$(PLATFORM)

ifeq "$(PLATFORM)" "solaris"
  EXTRALIBS=-lsocket -lnsl
endif

PROGS =	opend

all:	$(PROGS)

$(PROGS):	$(LIBAPUE)

opend:	main.o request.o cliargs.o
	$(CC) $(CFLAGS) -o opend main.o cliargs.o request.o $(LDFLAGS) $(LDLIBS)

clean:
	rm -f $(PROGS) $(TEMPFILES) *.o

include $(ROOT)/Make.libapue.inc
