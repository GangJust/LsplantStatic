# Lsplant Static

为Lsplant编译出静态链接库`.a`文件。

## 参考项目/资料

<https://github.com/cinit/QAuxiliary>

```cmd
  git clone https://github.com/GangJust/LsplantStatic
  cd LsplantStatic
  git submodule update --init
  git -C "LSPlant" config "submodule.test/src/main/jni/external/lsprism.update" none
  git -C "LSPlant" config "submodule.test/src/main/jni/external/lsparself.update" none
  git -C "LSPlant" config "submodule.docs/doxygen-awesome-css.update" none
  git submodule foreach git submodule update --init --recursive
```

## 编译环境

- 采用目前最新版本,低版本无法通过编译，可见: [app/build.gradle.kts#externalNativeBuild](app/build.gradle.kts)

- NDK Version: 29.0.13599879-beta2

- Cmake Version: 4.0.2

```cmake
cmake_minimum_required(VERSION 3.28) #与 Lsplant:lsplant 的cmake最小版本保持一致即可
```

接下来，你只需要执行 `app:build` 任务，然后就能在 `.cxx/Debug/<abi>/lsplant_static`找到 `liblsplant_static.a` 啦。
