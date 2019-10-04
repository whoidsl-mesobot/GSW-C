AM_CFLAGS = -O3 -Wall -std=gnu99

dist_doc_DATA = README LICENSE
dist_noinst_DATA = gsw_data_v3_0.nc

lib_LTLIBRARIES = libgswteos-10.la
include_HEADERS = gswteos-10.h

libgswteos_10_la_SOURCES = gsw_internal_const.h \
			   gsw_oceanographic_toolbox.c gsw_saar.c
libgswteos_10_la_CFLAGS = $(AM_CFLAGS)
libgswteos_10_la_LDFLAGS = -module -shared -export-dynamic \
			   -version-info 3:5:0

TESTS = gsw_check_functions
check_PROGRAMS = $(TESTS)
gsw_check_functions_SOURCES = gsw_check_data.h gsw_saar_data.h \
			      gsw_check_functions.c

gsw_check_functions_LDADD = -lgswteos-10 -lm

.PHONY: test
test: check
