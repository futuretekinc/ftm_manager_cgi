################################################################################
## qDecoder - http://www.qdecoder.org
##
## Copyright (c) 2000-2012 Seungyoung Kim.
## All rights reserved.
##
## Redistribution and use in source and binary forms, with or without
## modification, are permitted provided that the following conditions are met:
##
## 1. Redistributions of source code must retain the above copyright notice,
##    this list of conditions and the following disclaimer.
## 2. Redistributions in binary form must reproduce the above copyright notice,
##    this list of conditions and the following disclaimer in the documentation
##    and/or other materials provided with the distribution.
##
## THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
## AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
## IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
## ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE
## LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
## CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
## SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
## INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
## CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
## ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
## POSSIBILITY OF SUCH DAMAGE.
################################################################################
## $Id: Makefile.in 636 2012-05-07 23:40:43Z seungyoung.kim $
################################################################################

prefix		= /home/xtra/Work/FTMB-S1/ramdisk/apps/target/usr
exec_prefix	= ${prefix}

## Compiler options
CC			= arm-openwrt-linux-gcc -std=gnu99
#CC	= gcc -std=gnu99
CFLAGS		= -Wall -fPIC -g -I. -DDEBUG
CPPFLAGS	= -Iqdecoder-12.0.4/src/  -I./ -D_GNU_SOURCE
LIBS		= qdecoder-12.0.4/src/libqdecoder.a 
CMD_OBJS	= forcedch.o storedcelllist.o securitymode.o hsdpa.o qos.o apn.o network_state.o \
				module.o config.o init.o cnum.o usim.o pppdata.o pppip.o
REQ_OBJS	= main.o $(CMD_OBJS)
TARGETS		= iot.cgi

iot.cgi: $(REQ_OBJS)
	${CC} ${CFLAGS} ${CPPFLAGS} -o $@ $(REQ_OBJS) ${LIBS}

## Compile Module
.c.o:
	${CC} ${CFLAGS} ${CPPFLAGS} -c -o $@ $<
