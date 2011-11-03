CC = gcc
CFLAGS += -c -Wall -O3 -fno-strict-aliasing
LDFLAGS += -lz -pthread

SOURCES=traceroute-th.c
OBJECTS=$(SOURCES:.c=.o)
EXECUTABLE=passive-trace

all: clean $(SOURCES) $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS) 
		$(CC) $(LDFLAGS) $(OBJECTS) -o $@

.c.o:
		$(CC) $(CFLAGS) $< -o $@

clean:
	rm -rf *.o $(EXECUTABLE)

