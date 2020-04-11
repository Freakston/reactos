
list(APPEND SOURCE
    ubsan.c)

add_library(ksanitize ${SOURCE})
target_compile_definitions(ksanitize PUBLIC LIBSAN_KMODE)
target_compile_features(ksanitize PRIVATE c_std_11)
add_importlibs(ksanitize ntoskrnl)

add_library(ksanitize_w32k ${SOURCE})
target_compile_definitions(ksanitize_w32k PUBLIC LIBSAN_W32K)
target_compile_features(ksanitize_w32k PRIVATE c_std_11)
add_importlibs(ksanitize_w32k win32k)
