## --gc-sections
how to use:
    --gc-sections should use in link cmd with -ffunction-sections and -fdata-sections in complie cmd.
    makefile:
        .PHONY: test_section test_normal

        all: test_section test_normal

        test_section:
            gcc -ffunction-sections -fdata-sections -c section_test.c
            gcc -WL,--gc-sections -o $@ section_test.o
            mv section_test.o with_section.o
        
        test_normal:
            gcc -c section_test.c
            gcc -o $@ section_test.o
            mv section_test.o no_section.o

        clean:
            rm -rf *.o main_sections main_normal

ref link:    https://blog.csdn.net/wuu19/article/details/100725025

