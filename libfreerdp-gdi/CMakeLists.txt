# FreeRDP: A Remote Desktop Protocol Client
# libfreerdp-gdi cmake build script
#
# Copyright 2011 O.S. Systems Software Ltda.
# Copyright 2011 Otavio Salvador <otavio@ossystems.com.br>
# Copyright 2011 Marc-Andre Moreau <marcandre.moreau@gmail.com>
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

set(FREERDP_GDI_SRCS
	8bpp.c
	16bpp.c
	32bpp.c
	bitmap.c
	brush.c
	clipping.c
	dc.c
	drawing.c
	line.c
	palette.c
	pen.c
	region.c
	shape.c
	gdi.c)

add_library(freerdp-gdi ${FREERDP_GDI_SRCS})

target_link_libraries(freerdp-gdi freerdp-cache)
target_link_libraries(freerdp-gdi freerdp-common)
target_link_libraries(freerdp-gdi freerdp-rfx)

set_target_properties(freerdp-gdi PROPERTIES VERSION ${FREERDP_VERSION_FULL} SOVERSION ${FREERDP_VERSION} PREFIX "lib")

install(TARGETS freerdp-gdi DESTINATION ${CMAKE_INSTALL_LIBDIR})
