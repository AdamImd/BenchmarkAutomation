TARGET = RADIOSITY

OBJS = display.o elemman.o modelman.o patchman.o rad_main.o rad_tools.o room_model.o smallobj.o taskman.o visible.o
HHS = model.H parallel.H patch.H radiosity.H task.H
HS = model.h parallel.h patch.h radiosity.h task.h

include ../../Makefile.config

CFLAGS := $(CFLAGS) -I./glibdumb -I./glibps

#CCOPTS = -I -float -I/usr/include $(CFLAGS)
#LDFLAGS = -lm -lpthread
#CFLAGS = $(CINCLUDE) -O4 -march=i686 -mcpu=i686 -malign-double -funroll-loops -finline-functions -fomit-frame-pointer -D_REENTRANT
#CINCLUDE = -I$(GLIBDIR) -I./glibps

LOADLIBES = glibdumb/glib.a glibps/glibps.a

$(TARGET): $(OBJS) $(LOADLIBES)
	$(CC) $(OBJS) $(CFLAGS) $(LOADLIBES) -o $(TARGET) $(LDFLAGS)

radiosity.h: patch.h model.h parallel.h task.h
rad_main.c: rad_main.C $(HS)
patchman.c: patchman.C $(HS)
elemman.c: elemman.C $(HS)
taskman.c: taskman.C $(HS)
modelman.c: modelman.C $(HS)
smallobj.c: smallobj.C $(HS)
display.c: display.C $(HS)
visible.c: visible.C $(HS)
rad_tools.c: rad_tools.C $(HS)
room_model.c: room_model.C $(HS)

glibdumb/glib.a:
	$(MAKE) -C glibdumb

glibps/glibps.a:
	$(MAKE) -C glibps
