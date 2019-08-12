
# clang++ -std=c++11 test.cpp \
#  -I/usr/local/include/opencv4 \
#  -L/usr/local/Cellar/opencv/4.1.0_2/lib \
#  -lopencv_highgui -lopencv_imgcodecs -lopencv_core


# specify compiler here,
#CXX := g++
CXX := clang++ -lstdc++ -std=c++11

#CXXFLAGS  = -O2 -pipe -Wall -W -Woverloaded-virtual $(ROOTCFLAGS) 
CXXFLAGS := -O2 -pipe -Wall -W -Woverloaded-virtual  
INCLUDES := -I/usr/local/Cellar/opencv/4.1.0_2/include/opencv4/ 
LIBS    := -L/usr/local/Cellar/opencv/4.1.0_2/lib 
LIBS    += -lopencv_core -lopencv_imgcodecs -lopencv_imgproc -lopencv_highgui 
LIBS    += -lopencv_ml -lopencv_video -lopencv_calib3d -lopencv_objdetect -lopencv_flann
# -lopencv_contrib -lopencv_features3d -lopencv_legacy

INCLUDES += -I/usr/include/python2.7 
INCLUDES += -I/usr/local/lib/python2.7/site-packages/numpy/core/include # to include <numpy/arrayobject.h>
LIBS     += -lpython2.7

# memo on pkg-config
# /usr/local/lib/pkgconfig/ 以下を見にいく 
# pkg-config --cflags opencv4 : 実行するとOpenCVを利用したビルドに必要な-Iフラグを表示。
# pkg-config --libs   opencv4 : を実行するとOpenCVを利用したビルドに必要な-Lと-lを表示。

# If Package opencv was not found in the pkg-config search path.
# then, export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig

#CXXFLAGS += `pkg-config --cflags opencv`
#LDFLAGS  += `pkg-config --libs opencv`


SRCS := $(wildcard *.cpp)
#TARGET := $(SRCS:.cpp=)
TARGET := excute


all:$(TARGET)

$(TARGET):$(SRCS)
#	$(CXX) $< $(LDFLAGS) $(CFLAGS) -o $@
	$(CXX) $(CXXFLAGS) $(INCLUDES) $(LIBS) $(SRCS) -o $@ 

clean:
	rm -f *.o* *~ $(TARGET)

