# standard amuse configuration include
# config.mk will be made after ./configure has run
ifeq ($(origin AMUSE_DIR), undefined)
  AMUSE_DIR := $(shell amusifier --get-amuse-dir)
endif
-include ${AMUSE_DIR}/config.mk

CC ?= gcc
CFLAGS ?= -O3

CFLAGS +=  -std=c99 -Wall -W -O3

all: mameclot_worker

mameclot_worker:
	make -C src CC="$(CC)" CFLAGS="$(CFLAGS)"  LDFLAGS="$(LDFLAGS)" F77="$(FC)" FFLAGS="$(FFLAGS)" F77FLAGS="$(F77FLAGS)"
	cp src/mameclot ./mameclot_worker

clean:
	make -C src clean
	rm -f mameclot_worker
	rm -f *.pyc *.o
