# Visual Studio Code project template for Linux kernel

## Download and install [Visual Studio Code](https://code.visualstudio.com/)

## Install C/C++ extension for Visual Studio Code (`Ctrl`+`Shift`+`X`, search "`C/C++`")

## Built your kernel first

```sh
make <defconfig> # usually in arch/<arch>/configs/ folder
make -j$(nproc)
```

## Copy `.vscode` to the linux kernel folder

## Modify `.vscode/c_cpp_properties.json` to make IntelliSense work

### Change ***&lt;arch>*** to target architecture, for examples:

* `arm` for ARM 32bit
* `arm64` for ARM 64bit
* `x86` for both x86 32bit and 64bit

### Change ***&lt;gcc-compile-path>*** to your gcc compile path, for examples:

* `/usr/bin/aarch64-linux-gnu-gcc` for ARM 64bit
* `/usr/bin/x86_64-linux-gnu-gcc` for x86 64bit

### Change ***&lt;IntelliSenseMode>*** to the one of following:

* `linux-gcc-arm`
* `linux-gcc-arm64`
* `linux-gcc-x86`
* `linux-gcc-x64`

## (Optional) Modify `.vscode/tasks.json` to make build tasks work

### Change ***&lt;arch>*** to target architecture, for examples:

* `arm` for ARM 32bit
* `arm64` for ARM 64bit
* `x86` for both x86 32bit and 64bit

### Change **&lt;cross-compile>** to your cross compile path, for examples:

* `aarch64-linux-gnu-` for ARM 64bit
* `x86_64-linux-gnu-` for x86 64bit

### Change ***defconfig*** to your own kernel config

## Open with Visual Stdio Code

```sh
code .
```

## Appendix

### kernel build

* Show kernel build commands and defines

  ```sh
  make V=1
  ```

* Specific kernel build output dir

  ```sh
  make O=output [extra_args]
  ```

* For more info

  ```sh
  make help
  ```

### VSCode

* `Ctrl`+`P`: Search files by name
* `Ctrl`+`Shift`+`F`: Search text in files

## References

* https://stackoverflow.com/a/64479335
* https://github.com/amezin/vscode-linux-kernel
* https://github.com/microsoft/vscode-cpptools/issues/5588
* https://stackoverflow.com/questions/5820303/how-do-i-force-make-gcc-to-show-me-the-commands
