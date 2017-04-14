
CXX = g++

CXXFLAGS = -fPIC -g

INCFLAGS = -I.

LDLIBS = -lm -lstdc++

LDFLAGS = -shared

all: libLEEPreCutsAlgo.so

%.o: %.cxx %.h
	$(CXX) $(CXXFLAGS) $(INCFLAGS) -c $< -o $@

libLEEPreCutsAlgo.so: LEEPreCutAlgo.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o $@ $^ $(LDLIBS)

install_ups: libLEEPreCutsAlgo.so
	@echo "<<install into UPS build folder `ups flavor`>>"
	@cp -r ups ../
	@mkdir -p ../`ups flavor`/lib
	@mkdir -p ../`ups flavor`/include
	@cp libLEEPreCutsAlgo.so ../`ups flavor`/lib/
	@cp *.h ../`ups flavor`/include/

clean:
	rm *.o *.so
