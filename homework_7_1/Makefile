.PHONY := clean
bin := main
sources := main.c
dynamicLib := libFunctions.so
object := main.o
objects = add.o div.o mult.o sub.o 


$(bin): $(sources) $(dynamicLib)
		gcc $(sources) -o $(bin) -L. -lFunctions
		export LD_LIBRARY_PATH=$PWD:$LD_LIBRARY_PATH

$(object): $(sources)
		gcc $(sources) -c

$(dynamicLib): $(objects)
		gcc -shared $(objects) -o $(dynamicLib)


$(objects):%.o: %.c
		gcc $< -fPIC -c

.PHONY := clean
clean:
		rm -rf $(objects) $(object) $(dynamicLib) $(bin)

