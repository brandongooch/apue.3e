ROOT=../..
PLATFORM=$(shell $(ROOT)/systype.sh)
include $(ROOT)/Make.defines.$(PLATFORM)

ifeq "$(PLATFORM)" "solaris"
  EXTRALIBS=-lsocket -lnsl
endif

PROGS = opend.poll opend.select

all:	$(PROGS)

$(PROGS):	$(LIBAPUE)

opend.poll:	main.o request.o cliargs.o client.o loop.poll.o
	$(CC) $(CFLAGS) -o opend.poll main.o cliargs.o client.o request.o loop.poll.o \
		$(LDFLAGS) $(LDLIBS)

opend.select:	main.o request.o cliargs.o client.o loop.select.o
	$(CC) $(CFLAGS) -o opend.select main.o cliargs.o client.o request.o loop.select.o \
		$(LDFLAGS) $(LDLIBS)

clean:
	rm -f $(PROGS) $(TEMPFILES) *.o

include $(ROOT)/Make.libapue.inc
