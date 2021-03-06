# 1 点名前端页面使用说明

## 1.1 前期准备

项目中有一个`student.csv`的文件, 请在该文件中添加相关必要的数据。

### 1.1.1 csv文件说明
csv,全称Comma-Separated Values, 指的是用逗号（英文逗号）分隔的文本文件，可以通过excel打开和编辑，逗号分隔单元格，也可以通过文本编辑器打开和编辑。  

**注意：**  请始终保持文件格式为csv，文件名可以任意，文件甚至可以任意存储到你希望的地方，但请务必记住上诉地址。

### 1.1.2 必要数据说明

目前只解析了学号，姓名，图片地址三个字段。学号姓名最终展示在页面上，没有限制，请自己确保数据对应。图片指的是图片的文件名，含后缀，最终的图片请保存在images文件夹下。自己对应相关关系。

对于单行数据缺失的情形，将会忽略该学生。这里的数据缺失指的是一行没有两个逗号分隔符（excel打开的话指的是单行中有效单元格没有三个)， 如果需要知道是否有错误数据，请看1.2.

对于单行数据超过三个的，超过的将忽略。

## 1.2 使用

准备完毕前期数据之后，请通过双击`index.html`打开，如果有确认打开方式，选择任意浏览器即可。

打开`index.html`之后，注意到页面有一个 *选择文件*  按钮，点击，选择前期准备中的文件。

## 1.3 功能说明

目前的功能有随机选择一名学生，和点击列表中的某个学生两个功能

### 1.3.1 随机选择

点击页面的随机选择按钮，将会随机选择一名学生并大图展示，再次点击任意点后将退出大图显示。

### 1.3.2 指定学生

点击列表中任意一名学生的头像，将会大图显示该学生，再次点击任意点后将推出大图显示

## 1.4 问题说明和解决方案

| 问题编号 | 问题描述 | 解决方案 |
| :---: | :---: | :---: |
| 1 | 点击学生或随机选择不弹出学生照片 | 请检查学生配置文件是否正确 |
| 2 | 打开程序之后页面乱码 | 请确保csv最终的保存格式为utf8, 选中csv文件，右击，选中打开方式，选中记事本，打开后点击菜单栏的文件，另存为，选择编码UTF-8，保存，注意，通过记事本打开的文件如果乱码会无效，请确保你看到的文件不算乱码，你可以，通过新建文本文件，设置编码为ANSI，然后通过excel打开，配置完成后继续通过记事本打开，只要此时没有乱码，就可以执行上述过程将格式转换为UTF-8|
| 3 | 用excel打开和创建的csv文件正常，但是页面乱码，或者通过excel打开目标配置文件乱码 ，修改成正常的保存后总有某个地方乱码 | 请参照2 | 
| 4 | 学生的照片是一张很奇怪的图片 | 请核对配置文件的图片地址是否正确 |
| 5 | 有学生缺失 | 请在页面中按F12(或者ctrl + shift + i 或者在浏览器功能中选择开发者模式，然后点击控制台查看报错信息，检查配置是否正确 |

其他错误请联系本人


# 2 技术方案和未来规划

## 2.1 现有技术

目前采用的是vue作为前端框架。通过`html5`的文件`API`来实现加载配置

## 2.2 技术瓶颈和预期解决方案
`html5`的文件`API`虽然能够实现从指定文件中加载配置，但是，加载配置每次都需要选择，这不方便，这不合适。

未来将采用`node.js`来实现配置自动加载。

## 2.3 更多可能

- 在引入`node.js`之后，计划实现一个配置页面，通过在web中输入用户来实现存储和修改用户信息的功能。
- 计划实现班级座位表功能，前端展示的用户是实际的教室的座位。
- 在引入座位表功能后， 计划实现一个配置页面，能够在web中调整学生座位。
- 在引入座位表功能之后，计划实现一个自动排座功能。

更多可能和更新，请关注[github](https://github.com/zhifeiyv666/Call)