set(BaseClasses_SRCS
    amextra.cpp
    amextra.h
    amfilter.cpp
    amfilter.h
    amvideo.cpp
    arithutil.cpp
    cache.h
    checkbmi.h
    CMakeLists.txt
    combase.cpp
    combase.h
    cprop.cpp
    cprop.h
    ctlutil.cpp
    ctlutil.h
    ddmm.cpp
    ddmm.h
    dllentry.cpp
    dllsetup.cpp
    dllsetup.h
    dxmperf.h
    fourcc.h
    measure.h
    msgthrd.h
    mtype.cpp
    mtype.h
    outputq.cpp
    outputq.h
    perflog.cpp
    perflog.h
    perfstruct.h
    pstream.cpp
    pstream.h
    pullpin.cpp
    pullpin.h
    refclock.cpp
    refclock.h
    reftime.h
    renbase.cpp
    renbase.h
    schedule.cpp
    schedule.h
    seekpt.cpp
    seekpt.h
    source.cpp
    source.h
    streams.h
    strmctl.cpp
    strmctl.h
    sysclock.cpp
    sysclock.h
    transfrm.cpp
    transfrm.h
    transip.cpp
    transip.h
    videoctl.cpp
    videoctl.h
    vtrans.cpp
    vtrans.h
    winctrl.cpp
    winctrl.h
    winutil.cpp
    winutil.h
    wxdebug.cpp
    wxdebug.h
    wxlist.cpp
    wxlist.h
    wxutil.cpp
    wxutil.h
)

#add_pch(BaseClasses_SRCS)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
add_library(strmbase ${BaseClasses_SRCS})
target_include_directories(
  strmbase
  INTERFACE
  "$<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>"
  "$<INSTALL_INTERFACE:include>"
)
target_link_libraries(strmbase Winmm strmiids)
set_property(TARGET strmbase PROPERTY ARCHIVE_OUTPUT_NAME_DEBUG "")
install(TARGETS strmbase EXPORT BaseClassesTargets
  DESTINATION lib
  COMPONENT strmbase
  CONFIGURATIONS ${CMAKE_CONFIGURATION_TYPES}
)
