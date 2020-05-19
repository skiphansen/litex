include ../include/generated/variables.mak
include $(SOC_DIRECTORY)/software/common.mak

OBJECTS += adler32.o crc32.o tinfgzip.o tinflate.o tinfzlib.o

#CFLAGS += -Ofast

all: libuz.a

libuz.a: $(OBJECTS)
	$(AR) crs libuz.a $(OBJECTS)

# pull in dependency info for *existing* .o files
-include $(OBJECTS:.o=.d)

%.o: $(LIBUZ_DIRECTORY)/%.c
	$(compile)

%.o: %.S
	$(assemble)

.PHONY: all clean

clean:
	$(RM) $(OBJECTS) libuz.a .*~ *~
