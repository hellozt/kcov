set (kcov_SRCS
    arch/arch
    arch/i386
    arch/mips32
    arch/x86_64
    kc
    kc_addr
    kc_elf
    kc_file
    kc_line
    kc_ptrace
    kprobe_coverage
    main
    report
    utils)
include_directories (include/)

add_executable (${PROJECT_NAME} ${kcov_SRCS})
target_link_libraries (${PROJECT_NAME}
    elf
    dwarf
    ${GLIB2_LIBRARIES}
    pthread)
install (TARGETS ${PROJECT_NAME} ${INSTALL_TARGETS_DEFAULT_ARGS})