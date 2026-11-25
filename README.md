# ColorOS 日历增强

把课程表放进 ColorOS 日历主页。在底栏点「课程表」就能看课、调课，不需要换一个课表应用。早晨和下午的闹钟各自独立，按当前课表在系统时钟里安排。

[下载最新 APK](https://github.com/Xposed-Modules-Repo/io.github.yuangug.coursealarm/releases/latest) · [更新记录](https://github.com/Xposed-Modules-Repo/io.github.yuangug.coursealarm/releases) · [源码与使用文档](https://github.com/yuangug/coloros-calendar-enhance)

## 第一次使用

1. 安装 APK，在支持 **modern libxposed API 102** 的框架中启用模块，勾选推荐作用域 **日历**（`com.coloros.calendar`）。
2. 强行停止日历后重新打开，进入底栏的 **课程表 → 右下角 ⋮ → 导入课表**。
3. 学校教务系统可选「拾光课表」，搜学校、登录并打开课表，再点「解析课表」；已有 `.xlsx` 或 `.ics` 文件可直接导入。核对预览后再决定追加、替换还是新建。备份时选「导出课表」。

## 常用入口

| 入口 | 可以做什么 |
| --- | --- |
| 课程表 | 点课程看详情；长按可复制，长按空白处可添加或粘贴。导入、删除和调课后有 3 秒撤回时间。 |
| ⋮ → 课程提醒 | 设置课前提醒，分别开启早晨或下午闹钟，选择提前多久响。 |
| ⋮ → 课表设置 | 开启长按拖动调课，或在本周已没课时提前查看下一周。 |
| ⋮ → 课表主题 | 换背景图片或 GIF、调整遮罩，选择凝光或液态玻璃。 |

## 课程卡片

点卡片看详情后，课程活动默认继续保留。上课时可查看进度和剩余时间；使用兼容的星河岛展开卡时，连堂课的每次实际课间都有一个圆点，休息时能看到下一节还有多久开始。单节课沿用普通进度条。

日历是普通功能唯一推荐的作用域。通知栏的原生实时活动增强另需「系统界面」作用域；星河岛卡片需要兼容的星流环境。

## 兼容与反馈

日历 **17.3.70、17.6.20、17.8.0** 做过相关接口检查，具体功能的实机覆盖见[兼容记录](https://github.com/yuangug/coloros-calendar-enhance/blob/main/compatibility/README.md)。模块包名：`io.github.yuangug.coursealarm`。

遇到问题请到[源码仓库的 Issues](https://github.com/yuangug/coloros-calendar-enhance/issues)反馈，并注明日历版本、模块版本和复现步骤。
