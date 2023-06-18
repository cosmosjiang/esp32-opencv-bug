# esp32-opencv-bug


The compiling command to reproduct this issue
> xtensa-esp32-elf-g++ -fPIC -O3  -c chessboard.cpp

Then, xtensa-esp32-elf-g++ reports internal bug:

    chessboard.cpp:482:1: error: insn does not satisfy its constraints:
    482 | }
        | ^
    (insn 1117 528 1420 55 (set (reg/v:SF 21 f2 [orig:201 val ] [201])
            (mem/u/c:SF (symbol_ref/u:SI ("*.LC1487") [flags 0x2]) [0  S4 A32])) "chessboard.cpp":255:16 49 {movsf_internal}
         (nil))
    during RTL pass: postreload
    chessboard.cpp:482:1: internal compiler error: in extract_constrain_insn, at recog.cc:2692
    0x7f85b0abdd8f __libc_start_call_main
    	../sysdeps/nptl/libc_start_call_main.h:58
    0x7f85b0abde3f __libc_start_main_impl
    	../csu/libc-start.c:392
    Please submit a full bug report, with preprocessed source (by using -freport-bug).
    Please include the complete backtrace with any bug report.
    See <https://gcc.gnu.org/bugs/> for instructions.

