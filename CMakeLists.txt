# Copyright (C) 2007-2012 LuaDist.
# Submitted by David Manura
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( bzip2 C )
cmake_minimum_required ( VERSION 2.6 )
include ( cmake/dist.cmake )

add_definitions ( -D_FILE_OFFSET_BITS=64 )

# Library
set ( BZIP2_SRCS blocksort.c huffman.c crctable.c randtable.c compress.c decompress.c 
  bzlib.c )

add_library ( bz2 ${BZIP2_SRCS} libbz2.def )

install_library ( bz2 )
install_header ( bzlib.h )
