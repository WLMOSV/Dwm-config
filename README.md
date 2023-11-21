# dwm 配置

这是我的个人 dwm（动态窗口管理器）配置。请注意，该配置符合我的特定需求和偏好，可能并不适合每个人。

## 特性

- 修改图标：我对一些图标进行了定制，以提升 dwm 的视觉效果。
- Slatatus 状态栏配置：我集成了 slatatus，一个用于 dwm 的状态栏，用于显示相关系统信息，提高整体可用性。
- 额外快捷键：我添加了一些额外的快捷键，以增强窗口管理和导航体验。
- 音量控制脚本：我编写了一些简单的脚本，用于方便地控制系统的音量。

## 安装

1. 克隆 我的 dwm 仓库：

   ````shell
   git clone git@github.com:WLMOSV/Dwm-config.git
   
2. 使用我的定制化 `config.h` 文件替换默认的 dwm 配置文件。

3. 编译并安装 dwm：

   ````shell
   make clean install
   
4. 确保已安装 slatatus 所需的依赖项。

5. 将 slatatus 的配置信息添加到你的 `config.h` 文件中。

6. 重新编译并重新安装 dwm。

7. 重新启动 X11 或重新登录，以开始使用修改后的 dwm 配置。

## 快捷键

以下是我添加的一些额外快捷键示例：

- Mod 键 + Shift 键 + Enter 键：启动终端仿真器。
- Mod 键 + d 键：打开 dmenu，用于启动应用程序。
- Mod 键 + Shift 键 + q 键：退出当前窗口。
- Mod 键 + Shift 键 + c 键：关闭焦点窗口。
- Mod 键 + j 键：聚焦到下一个窗口。
- Mod 键 + k 键：聚焦到上一个窗口。
- Mod 键 + h 键：减小主窗口尺寸。
- Mod 键 + l 键：增大主窗口尺寸。
- Mod 键 + Shift 键 + j 键：将焦点窗口在堆栈中向下移动。
- Mod 键 + Shift 键 + k 键：将焦点窗口在堆栈中向上移动。
- Mod 键 + Control 键 + j 键：增加主窗口数量。
- Mod 键 + Control 键 + k 键：减少主窗口数量。
- Mod 键 + Shift 键 + 加号键：增加窗口之间的间隔。
- Mod 键 + Shift 键 + 减号键：减小窗口之间的间隔。

请参考 `config.h` 文件以获取完整的快捷键列表及其对应的操作。

## 音量控制脚本

我包含了一些简单的脚本，用于控制系统的音量。这些脚本可以绑定到 dwm 配置中的快捷键上。以下是这些脚本：

- `volume_up.sh`：增大音量。

  ```bash
  #!/bin/bash
  
  amixer sset Naster 5%+ unmute
  ```

- `volume_down.sh`：减小音量。

  ```bash
  #!/bin/bash
  amixer sset Master 5%- unmute
  ```

- `volume_toggle.sh`：切换静音状态。

  ```bash
  #!/bin/bash
  if amixer get Master | grep -Fq "[on]"; then
      amixer set Master mute
  else
      amixer set Master unmute
  fi
  ```

  

确保这些脚本具有可执行权限，并放置在系统的 `$PATH` 可访问的目录中。

## 声明

此配置高度个性化，可能不适合每个人的需求或硬件配置。建议在尝试使用此设置之前，对 dwm 及其配置过程有一定的了解。请自行承担使用风险。

## 鸣谢

- dwm：[suckless.org/dwm](https://dwm.suckless.org/)
- slatatus：[github.com/moetunes/slatatus](https://github.com/moetunes/slatatus)

## 许可此配置提供"如现"，不提供任何明示或暗示的担保。你可以根据 [MIT许可证](https://opensource.org/licenses/MIT) 进行修改和分发。
