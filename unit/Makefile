BINS=$(patsubst %.c,%,$(wildcard *.c))
OBJS=$(addsuffix .o,$(BINS))
LDFLAGS += $(shell pkg-config --libs r_core)
CFLAGS += $(shell pkg-config --cflags r_core) -g

all: $(BINS)

%: %.o
	$(CC) $(CFLAGS) $(LDFLAGS) $@.c -o $@


run:
	r=0 ; for a in $(BINS) ; do ./$$a || r=1; done ; exit $r

clean:
	rm -f $(OBJS) $(BINS)

.PHONY: all
