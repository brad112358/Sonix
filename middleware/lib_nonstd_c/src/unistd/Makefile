include ../Makefile.in

PWD		:= $(shell pwd)
INSTALL_DIR	?= $(PWD)/target
INSTALL_INC_DIR	:= $(INSTALL_DIR)/include/libmid_nonstdc
INSTALL_LIB_DIR := $(INSTALL_DIR)/lib
OBJ_DIR		?= $(PWD)/obj

ARCH            ?= arm
TARGET          ?= $(ARCH)-linux
CROSS_COMPILE   ?= $(TARGET)-
CC		= $(CROSS_COMPILE)gcc
AR		= $(CROSS_COMPILE)ar

CFLAGS		= $(PRJ_CFLAGS) -std=c99
CFLAGS		+= -I$(PWD)
CFLAGS		+= -I$(KERNEL_INC_DIR)
CFLAGS		+= -I$(DRIVER_INC_DIR)
CFLAGS		+= -I../include  -nostdinc


OBJS_FILES = $(UNISTD_OBJ_FILES)
OBJS = $(addprefix $(OBJ_DIR)/, $(OBJS_FILES))

.PHONY:all clean distclean install    
all: $(OBJS)


$(OBJ_DIR)/usleep.o:$(PWD)/usleep.c
	$(CC) -c $(CFLAGS) $< -o $@

clean:
	rm -rf $(OBJ_DIR) $(OBJS)

