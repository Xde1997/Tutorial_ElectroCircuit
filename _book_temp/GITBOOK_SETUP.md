# GitBook设置说明

## 项目转换完成

电路分析教程已成功转换为GitBook格式，可以正常构建和部署。

## 目录结构

```
Electronics_tutorial/
├── book.json              # GitBook配置文件
├── README.md              # 项目介绍（原index.md）
├── SUMMARY.md             # 目录结构文件
├── LICENSE.md             # Creative Commons许可证
├── deploy.sh              # 部署脚本
├── chapters/              # 章节文件目录
│   ├── chapter1.md        # 第1章：电路基础与电学单位
│   ├── chapter2.md        # 第2章：欧姆定律与串并联电路
│   ├── chapter3.md        # 第3章：基尔霍夫定律（KVL/KCL）
│   ├── chapter4.md        # 第4章：电阻网络与等效变换
│   ├── chapter5.md        # 第5章：电容、电感基础与暂态响应
│   ├── chapter6.md        # 第6章：一阶RC/RL电路动态分析
│   ├── chapter7.md        # 第7章：正弦交流信号与相量表示
│   ├── chapter8.md        # 第8章：RLC交流电路与阻抗分析
│   ├── chapter9.md        # 第9章：交流功率与功率因数校正
│   ├── chapter10.md       # 第10章：运算放大器基础与典型电路
│   ├── chapter11.md       # 第11章：半导体器件（Diode, BJT, MOSFET）
│   ├── chapter12.md       # 第12章：放大器与偏置电路设计
│   ├── chapter13.md       # 第13章：滤波器设计基础
│   ├── chapter14.md       # 第14章：电源与稳压电路
│   └── chapter15.md       # 第15章：电路设计项目与案例集
└── _book/                 # 构建输出目录（自动生成）
```

## GitBook配置

### book.json配置说明

- **title**: "电路分析课程讲义"
- **description**: "从电路原理到工程应用的完整学习路径"
- **language**: "zh-hans"（简体中文）
- **plugins**: 包含搜索、代码高亮、分享、字体设置等插件

### 已安装的插件

- `search`: 全文搜索功能
- `highlight`: 代码语法高亮
- `sharing`: 社交媒体分享
- `fontsettings`: 字体设置
- `theme-default`: 默认主题
- `expandable-chapters`: 可展开章节
- `copy-code-button`: 代码复制按钮
- `back-to-top-button`: 返回顶部按钮

## 构建和部署

### 本地构建

```bash
# 安装GitBook CLI（如果未安装）
npm install -g gitbook-cli@2.3.0

# 安装插件
gitbook install

# 构建文档
gitbook build . _book

# 或者使用部署脚本
./deploy.sh
```

### 部署到GitHub Pages

```bash
# 部署到默认分支（gh-pages）
./deploy.sh deploy

# 部署到自定义分支
./deploy.sh deploy your-branch-name
```

## 许可证

本项目采用 [Creative Commons Attribution-ShareAlike 4.0 International License](LICENSE.md) 进行许可。

## 注意事项

1. **Node.js版本**: 建议使用Node.js v18.x，与GitBook CLI兼容性最好
2. **插件依赖**: 首次构建前需要运行 `gitbook install` 安装插件
3. **中文支持**: 已配置为简体中文，支持中文搜索和显示
4. **移动端适配**: GitBook自动适配移动设备

## 故障排除

### 常见问题

1. **构建失败**: 检查Node.js版本，建议使用v18.x
2. **插件错误**: 运行 `gitbook install` 重新安装插件
3. **中文乱码**: 确保文件编码为UTF-8
4. **部署失败**: 检查Git仓库配置和权限

### 日志查看

构建过程中的详细日志会显示在终端中，包括：
- 插件加载状态
- 页面生成数量
- 构建时间
- 错误信息（如果有）

## 更新维护

### 添加新章节

1. 在 `chapters/` 目录下创建新的 `.md` 文件
2. 在 `SUMMARY.md` 中添加章节链接
3. 重新构建文档

### 修改配置

1. 编辑 `book.json` 文件
2. 运行 `gitbook install` 安装新插件（如果需要）
3. 重新构建文档

### 更新内容

1. 修改相应的 `.md` 文件
2. 运行 `gitbook build . _book` 重新构建
3. 使用 `./deploy.sh deploy` 部署更新

---

*最后更新: 2024年* 