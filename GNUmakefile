
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

clean:
	rm *.o *.so
