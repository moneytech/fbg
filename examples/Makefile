CC=gcc
STANDARD_FLAGS=-std=c11 -pedantic -D_GNU_SOURCE -D_POSIX_SOURCE -Wno-unused-value -Wno-unknown-pragmas
DEBUG_FLAGS=-DDEBUG -g -Wall
RELEASE_FLAGS=-O2 -Wall
DEFP=-DFBG_PARALLEL
SRC_LIBS=../src/lodepng/lodepng.c ../src/nanojpeg/nanojpeg.c ../src/fbgraphics.c
SRC1=$(SRC_LIBS) quickstart.c
SRC2=$(SRC_LIBS) simple_parallel_example.c
SRC3=$(SRC_LIBS) perlin.c full_example.c
SRC4=$(SRC_LIBS) tunnel.c
SRC5=$(SRC_LIBS) earth.c
SRC6=$(SRC_LIBS) flags.c
SRC7=$(SRC_LIBS) compositing.c
OUT1=quickstart
OUT2=simple_parallel_example
OUT3=full_example
OUT4=tunnel
OUT5=earth
OUT6=flags
OUT7=compositing
LIBS1=-lm
LIBS2=-lm -lpthread
LIBS3=-lm -lpthread
LIBS_LFDS_711=liblfds711.a
LIBS_LFDS_720=liblfds720.a
INCS=-I ../src/ -I.
INCS3=-I ../src/ -I.
INCS_LFDS_711=-Iliblfds711
INCS_LFDS_720=-Iliblfds720

tiny:
	$(CC) ../src/fbgraphics.c simple_parallel_example.c $(INCS) $(STANDARD_FLAGS) $(DEFP) -fdata-sections -ffunction-sections -flto -DFBG_LIGHT -Os -lpthread -o $(OUT2) -Wl,--gc-sections,-flto

all:
	$(CC) $(SRC1) $(INCS) $(STANDARD_FLAGS) $(RELEASE_FLAGS) $(LIBS1) -o $(OUT1)
	$(CC) $(SRC2) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT2)
	$(CC) $(SRC3) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT3)
	$(CC) $(SRC4) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT4)
	$(CC) $(SRC5) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT5)
	$(CC) $(SRC6) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT6)
	$(CC) $(SRC7) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT7)

debug:
	$(CC) $(SRC1) $(INCS) $(STANDARD_FLAGS) $(DEBUG_FLAGS) $(LIBS1) -o $(OUT1)
	$(CC) $(SRC2) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(DEBUG_FLAGS) $(LIBS2) -o $(OUT2)
	$(CC) $(SRC3) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(DEBUG_FLAGS) $(LIBS2) -o $(OUT3)
	$(CC) $(SRC4) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(DEBUG_FLAGS) $(LIBS2) -o $(OUT4)
	$(CC) $(SRC5) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(DEBUG_FLAGS) $(LIBS2) -o $(OUT5)
	$(CC) $(SRC6) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(DEBUG_FLAGS) $(LIBS2) -o $(OUT6)
	$(CC) $(SRC7) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(DEBUG_FLAGS) $(LIBS2) -o $(OUT7)

lfds711:
	$(CC) $(SRC2) $(INCS3) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS3) -DLFDS711 -o $(OUT2)
	$(CC) $(SRC3) $(INCS3) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS3) -DLFDS711 -o $(OUT3)
	$(CC) $(SRC4) $(INCS3) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS3) -DLFDS711 -o $(OUT4)
	$(CC) $(SRC5) $(INCS3) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS3) -DLFDS711 -o $(OUT5)
	$(CC) $(SRC6) $(INCS3) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS3) -DLFDS711 -o $(OUT6)
	$(CC) $(SRC7) $(INCS3) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS3) -DLFDS711 -o $(OUT7)

quickstart: $(SRC1)
	$(CC) $(SRC1) $(INCS) $(STANDARD_FLAGS) $(RELEASE_FLAGS) $(LIBS1) -o $(OUT1)

simple: $(SRC2)
	$(CC) $(SRC2) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT2)

full: $(SRC3)
	$(CC) $(SRC3) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT3)

tunnel: $(SRC4)
	$(CC) $(SRC4) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT4)

earth: $(SRC5)
	$(CC) $(SRC5) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT5)

flags: $(SRC6)
	$(CC) $(SRC6) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT6)

compositing: $(SRC7)
	$(CC) $(SRC7) $(INCS) $(STANDARD_FLAGS) $(DEFP) $(RELEASE_FLAGS) $(LIBS2) -o $(OUT7)

clean:
	rm -f *.o $(OUT)
	rm $(OUT1) $(OUT2) $(OUT3) $(OUT4) $(OUT5) $(OUT6) $(OUT7)
