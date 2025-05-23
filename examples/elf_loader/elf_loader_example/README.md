## ELF Loader Example

This example shows how to use ELF loader to run ELF file.

## How to Use Example

Before project configuration and build, be sure to set the correct chip target using `idf.py set-target <chip_name>`.

* Note: Only ESP32, ESP32-S2, ESP32-S3 and ESP32-P4 are supported

### Hardware Required

* A development board based on espressif ESP32/ESP32-S2/ESP32-S3/ESP32-C6/ESP32-P4 SoC
* A USB cable for power supply and programming

### Configure the Project

Open the project configuration menu (`idf.py menuconfig`).

In the `Example Configuration` menu:

* Enable ELF input arguments in the `Support arguments for ELF main` option if necessary.
* Set the arguments in the `Arguments of ELF main` option.

### Generate the ELF File

The `test_xtensa.elf` or `test_riscv.elf` used for testing is corresponding ELF file generated by [build_elf_file_example](https://github.com/espressif/esp-iot-solution/tree/master/examples/elf_loader/build_elf_file_example), corresponding to the `xtensa` and `risc-v` processor architectures respectively.

In `build_elf_file_example` example, `hello_world.app.elf` will be generated, and you can copy this ELF file to the `elf_loader_example/main`, e.g.
```
    cp build/hello_world.app.elf ../elf_loader_example/main/test_xtensa.elf
```

You can refer to [build_elf_file_example](https://github.com/espressif/esp-iot-solution/tree/master/examples/elf_loader/build_elf_file_example) to generate the ELF file you need.

### Build and Flash

Run `idf.py -p PORT flash monitor` to build, flash and monitor the project.

(To exit the serial monitor, type ``Ctrl-]``.)

## Example Output

As you run the example, you will see the following log:

```
I (0) cpu_start: Starting scheduler on APP CPU.
I (382) elf_loader: Start to relocate ELF
I (392) elf_loader: Start to run ELF
hello world 0
hello world 1
hello world 2
hello world 3
hello world 4
hello world 5
hello world 6
hello world 7
hello world 8
hello world 9
I (10392) elf_loader: Success to exit from APP of ELF
```
