# pcl2仕洋的自定义主页教程！
本文本仅针对于pcl2的xaml自定义主页！\
自定义主页教程（`pcl`）\
哈哈，欢迎来到由仕洋编写的自定义主页教程！\
首先你要有一款好用的编辑器，比如我在用的：[IDEA](https://raw.githubusercontent.com/shiyang0510/pcl2-sy/main/Help/%E5%AD%90%E9%A1%B5%E9%9D%A22.xaml)\
（没打钱，纯推荐）
我建议咱们 `边看` 然后打开你的XAML `边写`

---
## 第一章 纯文本（TextBlock）
- Text：设置显示的文本（如果要使用引号等特殊字符，自行百度 XAML 转义）
- TextWrapping：开启自动换行
- FontSize：设置字号
- FontWeight：设置为 Bold 时，文字加粗
- Foreground：调整前景颜色（ `十六进制` 字符串，例如 #FF010203 代表 ARGB 中的 255,1,2,3。前两位代表不透明度，FF 为全不透明，00 为全透明）
- HorizontalAlignment：设置对齐方式（Left、Center、Right）

解释：\
以上是龙猫在[XAML](https://raw.githubusercontent.com/shiyang0510/pcl2-sy/main/Help/%E5%AD%90%E9%A1%B5%E9%9D%A22.xaml)文件当中说的\
（我是认为比在自定义主页教程讲的，更加简洁 ）\
没办法给演示，因为这是 `Git`（bushi\
那就来个，源码展示：\
`<TextBlock Text="冷知识：仕洋team成立于2023/3/14" Foreground="#25D2F5" HorizontalAlignment="Left" Margin="0,0,0,10"/>`\
他输出的，大概就是：\
冷知识：仕洋team成立于2023/3/14
只是文字颜色不对

---
## 第二章 图片（Image）
- Source：要显示的图片的网址
- Foreground：调整前景颜色（`十六进制`字符串，例如 #FF010203 代表 ARGB 中的 255,1,2,3。前两位代表不透明度，FF 为全不透明，00 为全透明）
- HorizontalAlignment：设置对齐方式（Left、Center、Right）

解释：\
这个图片就好玩了，如果你想做联网更新\
大概率是要上传至 `git`的，再使用链接即可实现\
源码展示：\
`<Image Source="https://github.com/shiyang0510/pcl2-sy/blob/main/b.png?raw=true" HorizontalAlignment="Center"/>`\
他输出的大概是 :
![仕洋的背景](https://github.com/shiyang0510/pcl2-sy/blob/main/b.png?raw=true "背景")

---
## 第三章 卡片（local:MyCard）
- Title：设置显示的标题文本
- CanSwap：这张卡片是否可以折叠，True 为是，False 为否
- IsSwaped：这张卡片是否默认折叠，要求 CanSwap 必须为 True
- Foreground：调整前景颜色（`十六进制`字符串，例如 #FF010203 代表 ARGB 中的 255,1,2,3。前两位代表不透明度，FF 为全不透明，00 为全透明）
- HorizontalAlignment：设置对齐方式（Left、Center、Right）（使用时，CanSwap 属性需为 False）

解释：\
卡片可以说是最最最常用的一个控件，所以这个通常有了一个设置好了后，几乎都是`复制`-`粘贴`的
这个就没法演示了，因为`README.md`文件是无法表达这个控件的\
那就发个源码吧：\
`<local:MyCard Title="此设置，仅为仕洋team内部版本！看什么看，快去工作！" Margin="0,0,0,15" Height="35" CanSwap="False" IsSwaped="False" />`

---
## 第四章 提示条（local:MyHint）
- Text：设置显示的文本（&#xA; 代表换行）
- IsWarn：设置为 True 代表警告样式，False 代表提示样式
- HorizontalAlignment：设置对齐方式（Left、Center、Right）

解释：\
提示条还是很简单的（起码比前几个简单）\
前面说了`&#xA; `代表换行\
那么意思就是，大家在复制网址时如果含有`&#xA; `这些字符，`XAML`文件是会对爆红线的！
所以大家写的时候一定要注意！\
源码展示：\
`<local:MyHint Text="如你所见，仕洋这个B还没更新" Margin="0,0,0,8" IsWarn="False" />`

---
## 第五章 按钮（local:MyButton）
- Text：设置显示的文本
- Padding：设置内边距，格式与 Margin 一致
- ColorType：设置颜色主题（Highlight 为当前启动器的主题颜色，Red 为红色，默认为黑色）
- EventType、EventData：触发特定事件
- HorizontalAlignment：设置对齐方式（Left、Center、Right）

解释：\
按钮是除了卡片后，第二个常用的，也比较简单。\
但是哦，主题色这个东西，`Highlight`只能用在`ColorType`里面，不能用在`Foreground`！\
当然，也不是没有解决办法，在`Foreground`里写上`{DynamicResource ColorBrush2}`就好啦！
源码展示：\
第一个：\
`<local:MyButton Text="下载" Width="200" Margin="0,0,0,10" Height="35" HorizontalAlignment="Center" ColorType="Highlight" EventType="下载文件" EventData="https://www.jetbrains.com/zh-cn/idea/download" />  `\
第二个`Foregroun`的解决办法:\
`<TextBlock TextWrapping="Wrap" Margin="0,0,0,10" FontSize="15" Foreground="{DynamicResource ColorBrush2}"
Text="不知道写什么"/>`

---
## 第六章 文本按钮（local:MyTextButton）
- Text：设置显示的文本
- EventType、EventData：触发特定事件
- Foreground：调整前景颜色（`十六进制`字符串，例如 #FF010203 代表 ARGB 中的 255,1,2,3。前两位代表不透明度，FF 为全不透明，00 为全透明）
- HorizontalAlignment：设置对齐方式（Left、Center、Right）

解释：\
和按钮类似，这里不过多赘述。\
源码展示：\
`<local:MyTextButton Foreground="{DynamicResource ColorBrush2}" EventType="打开网页" EventData="https://space.bilibili.com/1151723944" Text="文本按钮" HorizontalAlignment="Center" />`

---
## 未完待续...
