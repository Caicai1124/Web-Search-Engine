#
# Makefile for iigen
#

UNAME := $(shell uname)

CC = gcc
ifeq ($(UNAME), Linux)
CFLAGS = -g -O2 -Wall -D__DEBUG__ -D__LINUX__ -lpthread
else
CFLAGS = -g -O2 -Wall -D__DEBUG__ -D__MACOS__
endif

OBJS = iigen.o lexicon.o iindex.o utils.o warc.o merge.o tokenizer.o compress.o
BINS = iigen

all:  $(BINS)

iigen:  $(OBJS)
	$(CC) -o $@ $(OBJS) -lpthread

lexicon_test.o:  lexicon.c
	$(CC) -c $(CFLAGS) -D__TEST__ -o $@ $<

warc_test.o:  warc.c
	$(CC) -c $(CFLAGS) -D__TEST__ -o $@ $<

tokenizer.o:  tokenizer.c
	$(CC) -c $(CFLAGS) -D__TEST__ -o $@ $<

iindex_test.o:  iindex.c
	$(CC) -c $(CFLAGS) -D__TEST__ -o $@ $<

utils.o:  utils.c
	$(CC) -c $(CFLAGS) -D__TEST__ -o $@ $<

compress.o:  compress.c
	$(CC) -c $(CFLAGS) -D__TEST__ -o $@ $<

clean:  
	rm -fr $(BINS) $(OBJS) *.dSYM *.pyc tests/*.pyc *.o &>/dev/null

