# ColorOS 日历增强 · CourseAlarm

> LSPosed 模块（modern libxposed API 102），给 ColorOS 日历补上「真正的课程表」：导入、主题、导出，以及第二天自动设闹钟。

**目标应用**：ColorOS 日历 `com.coloros.calendar`（16.24.2 /17.0.0.101实测，Android 16/17 / arm64）、时钟 `com.coloros.alarmclock`
**模块包名**：`io.github.yuangug.coursealarm`　|　**API**：102（staticScope）

## 功能

### 一、课程表就在主页
底栏变成「日历 | 待办 | 课程表」三段，切到「课程表」是在主页内换内容区，**不打开新页面**，底栏仍在。
课表本身**直接复用宿主的 `TableView`**（`CourseWeekViewPagerAdapter` + `calendars_json_extensions` / `events_json_extensions`），
配色、非本周灰显、午休条都与原生课表页一致。

### 二、底栏左右钮按页独立
- 日历 / 待办：左＝视图菜单，右＝新建（宿主原样）
- 课程表：左＝周次选择，右＝课表 ⋮（创建课表 / 课表管理 / 分享课表 / 课程提醒 / 创建桌面快捷方式 / 导入 / 导出 / 课表主题 / 回到本周 / 刷新）

### 三、课表主题
无背景 / 纯色 / 渐变 / **图片（png jpg webp gif 动图）** + 遮罩三档；
有主题时顶栏白底、底栏底衬、页面留白条全部透明，课表文字按背景亮度自动反色。

### 四、导入 / 导出
- 教务系统网页登录导入（内嵌浏览器，账号不落盘）、`.xlsx`、`.ics`、粘贴课表 HTML / `kbList` JSON
- 导出 `.xlsx`（与原版式一致）/ `.ics`

### 五、早八闹钟
每晚 21:00 检查第二天第一节，按设定提前量在系统时钟里建一次性闹钟（走 Clock 的 AI ContentProvider）。

## 兼容性
- Android 16/17 / ColorOS 16/17 实测（PLC110/PLR110）；宿主版本 16.24.2/17.3.70
- LSPosed 2.2.1（API 102）；staticScope，作用域：`com.coloros.calendar`、`com.coloros.alarmclock`

## 已知限制
- 课表页暂无日视图（左钮是周次选择）
- GIF 背景走 `Movie` 自绘，未做逐帧优化
- 依赖宿主类名/资源名，宿主大版本升级可能需要适配

## 注意
本模块只改宿主进程内的界面与数据，不替换 App、不改桌面图标；卸载模块即恢复原样。
