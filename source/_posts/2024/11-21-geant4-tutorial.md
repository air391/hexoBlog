---
title: geant4-tutorial
date: 2024-11-21 17:40:38
tags:
 - geant4
 - 文档
 - 教程
categories: geant4
---

## 探测器几何

除了cpp代码生成外，还可以使用gdml导入与ascii text方式。

### gdml

推荐的生成方法是[freeCAD workbench](https://github.com/KeithSloan/GDML)建模后导出gdml。
其github 讨论区有部分[教程](https://github.com/KeithSloan/GDML/discussions/149#js-repo-pjax-container)可供参考

gdml文档可以在[这里](https://gdml.web.cern.ch/GDML/)找到，geant4关于gdml的[说明](https://geant4-userdoc.web.cern.ch/UsersGuides/ForApplicationDeveloper/html/Detector/Geometry/geomXML.html)，参考位于[examples/extended/persistency/gdml](https://geant4-userdoc.web.cern.ch/Doxygen/examples_doc/html/Examples_gdml.html)

root 对gdml也有支持，但未尝试。

### ascii text

geant4关于ascii text的[说明](https://geant4-userdoc.web.cern.ch/UsersGuides/ForApplicationDeveloper/html/Detector/Geometry/geomASCII.html)，[详细文档](https://geant4.web.cern.ch/collaboration/working_groups/persistency/docs/textgeom.pdf)，参考位于[examples/extended/persistency](https://geant4-userdoc.web.cern.ch/Doxygen/examples_doc/html/Examples_persistency.html)

一个备用参考[GAMOS](https://fismed.ciemat.es/GAMOS/GAMOS_doc/GAMOS.6.0.0/Geometry/Geometry.html)

## 数据采集

一个参考[教程](https://indico.cern.ch/event/294651/sessions/55918/attachments/552022/760640/UserActions.pdf)

## 封装工具

[gears](https://physino.xyz/gears/)提供了对geant4的封装，虽然未经尝试，但其中关于ascii text生成探测器几何而非cpp代码的方式值得参考

## 教程

cern的[教程](https://indico.cern.ch/event/294651/sessions/55918/attachments/552022/)，以及[文档](https://indico.cern.ch/category/5389/)