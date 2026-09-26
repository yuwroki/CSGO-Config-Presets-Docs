---
title: 使用说明
order: 5
---

# {{ $frontmatter.title }}

## 备份游戏设置

### 方法一 另存设置

控制台输入 `host_writeconfig backup` 即可生成 `backup.cfg`，必要时 `exec backup` 恢复

### 方法二 手动备份

备份个人CFG文件夹的所有文件到另一位置

- `config.cfg` 和 `video.txt` 分别对应**游戏设置**和**画面设置**
- 个人设置文件夹 `...\Steam\userdata\Steam数字ID\730\local\cfg\`
- 游戏设置文件夹 `...\Steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg\`

::: warning
CS2个人设置文件夹无法在控制台执行
:::

#### Steam数字ID不知道怎么办？

- 打开 Steam 的 `添加好友` 页面，**ID=好友代码**
- 登录 [https://steamid.io/](https://steamid.io/)
  - 复制个人资料简介，如 `https://steamcommunity.com/id/1234567890/`
  - 第二行，如 SteamID3 [U:1:`146859713`] ，ID=`146859713`

### 方法三 工具箱

下载[CS工具箱](https://cstb.upup.cool)，自动获取路径、选择账号后可在 `CFG页`备份与还原

## 使用方法

### 修改

- 打开 `auto.cfg` 修改各快捷键和参数
- 打开 `crosshair.cfg` 修改准星参数
- 从[可选指令](/v1/optional.html)中挑选合适的指令写入cfg

提示

- 可以把游戏设置成**窗口模式**对应着改
- **准星、持枪参数**可从创意工坊地图导出或使用下文的方法

### 移动

修改完成后移动到CFG文件夹：

- 个人CFG文件夹仅该玩家使用，方便打包
- 游戏CFG所有本机账号共享，请自行取舍

### 注释说明

`//` 是**注释** 在它出现的那一行，之后的内容都不会被读取

```
   这是指令;    //这是注释
```

   如果不想用某条指令，就在指令前加上注释，或者直接删除:

```
   //这是指令;    //这是注释
```

## 准星&持枪参数导出

分开使用，复制到控制台，即可得到对应参数

```
echo ;echo "==================== 准星参数 ====================";echo ;sv_max_allowed_developer 2;developer 2;
con_filter_enable 1;con_filter_text cl_crosshair;host_writeconfig;
con_filter_text cl_fix;host_writeconfig;developer 0;con_filter_enable 0;
```

```
echo ;echo "==================== 持枪参数 ====================";echo ;sv_max_allowed_developer 2;developer 2;
con_filter_enable 1;con_filter_text viewmodel;host_writeconfig;
con_filter_text cl_bob;host_writeconfig;developer 0;con_filter_enable 0;
```

## 准星分享代码

控制台使用分享代码示例：

```
apply_crosshair_code CSGO-cS6Fv-iBc8r-sroTA-4jyik-OYTSH
```

> CS2 已经禁用了该指令，只有在解锁控制台隐藏指令后才能生效

![准星代码](./img/准星代码.png)
