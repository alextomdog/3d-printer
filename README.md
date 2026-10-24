# 3d-printer

基于 1515 铝型材的 Cartesian FDM 3D 打印机整机结构设计，包含 SolidWorks 零件、装配体、DWG 加工图与 BOM。

A Cartesian FDM 3D printer design built on a 1515 aluminium extrusion frame, with SolidWorks parts/assemblies, DWG machining drawings and a bill of materials.

> 本项目完成的是**结构与机械设计**：整机建模、零件设计、装配、加工图和 BOM 选型。仓库不包含固件、切片参数或实物打印测试数据。

## 规格

| 项目 | 方案 |
|---|---|
| 结构 | Cartesian / 1515 铝型材框架 |
| 打印尺寸 | 220 × 220 mm 热床，200 × 200 mm 玻璃 |
| X/Y 传动 | GT2 同步带、2GT-20 同步轮、42-44 步进电机 |
| Z 轴 | 双 Z，T8 250 mm 丝杠、M6 光轴、SCS6UU 滑块、42-38 步进电机 |
| 直线导向 | MGN9 导轨（278 mm × 1、250 mm × 2）与 MGN9 滑块 × 3 |
| 挤出 | E3D V6 1.75 mm / 0.4 mm 12 V 40 W 远程挤出头 + MK8 挤出机 + 42-47 步进电机 |
| 主板 | RAMPS 1.4 + Arduino Mega 2560 + 5 × A4988 |
| 显示 | 2004 LCD |
| 电源 | 12 V 9 A |
| 热床 | MK3 铝基板热床 + NTC 温度传感器 |

## 仓库结构

```text
.
├── new_sw/
│   ├── 打印机.SLDASM              # 主装配体
│   ├── *.SLDPRT                   # 54 个零件
│   ├── *.SLDASM                   # 8 个装配体
│   ├── cadFiles/*.DWG             # 15 张加工图
│   └── vocano/                    # 火山喷头相关零件
├── material.xlsx                  # BOM（Excel）
├── material.ods                   # BOM（LibreOffice）
└── docs/
    ├── design.md                  # 设计说明
    ├── bom.md                     # 分类 BOM 摘要
    └── system-diagram.md          # 电气连接框图
```

## 设计要点

- **框架**：1515 铝型材，320 mm × 4、285 mm × 4、293 mm × 4、220 mm × 2、200 mm × 2；直角脚槽连接。
- **XY 传动**：42-44 步进电机驱动 GT2-6 同步带，2GT-20 同步轮/惰轮支撑；MGN9 导轨承担喷头与交叉方向导向。
- **双 Z**：两只 42-38 步进电机分别驱动 T8 丝杠，M6 光轴与 SCS6UU 滑块辅助导向；热床由四角弹簧与法兰螺母支撑。
- **挤出**：E3D V6 远程挤出头配 MK8 挤出机，42-47 步进电机驱动。
- **电控**：RAMPS 1.4 扩展 Arduino Mega 2560，5 个 A4988 分别驱动 X/Y/双 Z/挤出机；2004 LCD、NTC 与限位开关接入。

## 打开方式

- `.SLDPRT` / `.SLDASM`：SolidWorks 或兼容的 CAD 查看器。
- `.DWG`：AutoCAD、DWG TrueView 或其他支持 DWG 的 CAD 软件。
- BOM：`material.xlsx` 可用 Excel/LibreOffice 打开；分类摘要见 [`docs/bom.md`](docs/bom.md)。

## 项目范围

已完成：

- 整机结构方案与 1515 铝型材框架设计
- 54 个零件、8 个装配体的 SolidWorks 建模
- 15 张 DWG 加工图
- 47 项 BOM 选型与数量统计

未包含：

- Marlin/固件配置、切片参数、打印调参记录
- 实物装配照片、打印样件与性能测试
- 电气线束、接线图以外的 PCB 设计

因此，本仓库可以证明结构设计、零件建模、装配与出图能力，但不宣称机器已经制造或稳定打印。

## 许可

原创 CAD 模型、DWG 图纸、BOM 与文档采用 **CERN-OHL-S-2.0**，见 [`LICENSE`](LICENSE)。

E3D V6、MK8、MGN9、RAMPS、A4988、Arduino、42 步进电机等标准件/厂商模型的版权归各自厂商，仅用于装配参考，不在本项目授权范围内；详见 [`THIRD_PARTY.md`](THIRD_PARTY.md)。

## English

A Cartesian FDM 3D printer mechanical design based on a 1515 aluminium extrusion frame. The repository contains SolidWorks parts and assemblies, 15 DWG machining drawings and a BOM. It covers mechanical structure, part modelling and drawing generation; firmware, slicer profiles and build/test data are not included.
