# Licensed to the Apache Software Foundation (ASF) under one or more
# contributor license agreements.  See the NOTICE file distributed with
# this work for additional information regarding copyright ownership.
# The ASF licenses this file to You under the Apache License, Version 2.0
# (the "License"); you may not use this file except in compliance with
# the License.  You may obtain a copy of the License at
# 
#     http://www.apache.org/licenses/LICENSE-2.0
# 
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

APPVER = 5.0 # Need WINVER=0x0500 to get HMONITOR defined.
HY_BIN=$(HY_TARGET)\build\classlib\awt\native\gl\# trailing slash
!include <$(HY_TARGET)\hdk\build\make\defines.mak>

PNG_DIR=$(HY_PNG_DIR)\# avoid continuation

LIBBASE=gl
DLLNAME=$(DLLPATH)$(LIBBASE).dll
LIBNAME=$(LIBPATH)$(LIBBASE).lib
HYLDFLAGS = $(HYLDFLAGS) -def:$(LIBBASE).def

HYCFLAGS = $(HYCFLAGS) /D_WIN32_WINNT=0x0500 /I$(SHAREDSUB)include /I$(SHAREDSUB) \
           /I$(PNG_DIR) /Iinclude

BUILDFILES = \
  $(HY_BIN)BitmapSurface.obj \
  $(HY_BIN)GDIBlitter.obj \
  $(HY_BIN)WinGDIGraphics2D.obj \
  $(HY_BIN)WinGDIPGraphics2D.obj \
  $(HY_BIN)WinGraphicsEnvironment.obj \
  $(HY_BIN)WinThemeGraphics.obj \
  $(HY_BIN)LockingKeys.obj \
  $(HY_BIN)blitter.obj \
  $(HY_BIN)gifdecoder.obj \
  $(HY_BIN)LUTTables.obj \
  $(HY_BIN)pngdecoder.obj \
  $(HY_BIN)SurfaceDataStructure.obj \

VIRTFILES = $(LIBBASE).res
SYSLIBFILES = ws2_32.lib Iphlpapi.lib \
              Msimg32.lib gdiplus.lib User32.lib uxTheme.lib 

MDLLIBFILES = $(MDLLIBFILES) \
  $(LIBPATH)hyzlib$(HY_LINKLIB_SUFFIX) $(PNG_DIR)libpng$(HY_LINKLIB_SUFFIX)

DLLBASE=0x13300000

!include <$(HY_HDK)\build\make\rules.mak>
