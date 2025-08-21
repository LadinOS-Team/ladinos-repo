# LadinOS 软件源包目录规范  

本目录遵循 **Debian/Ubuntu APT 仓库结构**：  
包需按 **「首字母 + 包名」** 分类存放，例如：  
- 包名 `ladinos-default-settings` → 存放路径 `pool/main/l/ladinos-default-settings/`  


### 如何正确上传包？  
1. **建分类目录**：  
   比如包名 `ladinos-tux`，首字母是 `l`，需先建 `pool/main/l/ladinos-tux/` 目录；  
2. **传deb包**：  
   把 `.deb` 包拖进上述目录；  
3. **更新索引**：  
   通过 `reprepro` 或 GitHub Action 生成 APT 索引（否则APT无法识别包）。  


### 为什么要这样？  
Debian/Ubuntu 的 APT 工具 **通过目录结构扫描包** ，乱序存放会导致：  
- `apt update` 报错“无法定位软件包”；  
- `reprepro` 无法自动生成索引文件。  


更多细节参考：[Debian 仓库结构官方文档](https://wiki.debian.org/DebianRepository)  
