# IC Engineering Workspace

这是一个用于长期积累数字 IC、FPGA、MCU 和嵌入式工程的仓库模板。

仓库的核心原则是：**代码、设计依据、工程指标、上手步骤、改进过程和验证结果必须放在一起，并保持能够相互对应。**

## 快速开始

### 1. 新建工程

```bash
python scripts/new_project.py projects/my_first_fpga --type fpga --name "My First FPGA"
```

也可以直接复制 `projects/_template/`，再修改 `project.yaml` 和各个文档。

### 2. 开始工作

进入工程目录，依次阅读：

1. `README.md`
2. `project.yaml`
3. `docs/design.md`
4. `docs/spec.md`
5. `docs/getting-started.md`
6. `docs/verification.md`

### 3. 完成一次改动

```text
理解问题 → 修改代码 → 编译/仿真/上板验证 → 记录结果 → 更新文档 → 检查 git diff
```

每次具有实际意义的改动，都在 `docs/changes/` 新增一份记录。模板见 `docs/templates/change.md`。

## 推荐的工程结构

```text
projects/<project_name>/
├── README.md
├── project.yaml
├── AGENTS.md                 # 该工程的特殊规则，可选
├── docs/
│   ├── design.md             # 为什么这样设计
│   ├── spec.md               # 要达到什么指标
│   ├── getting-started.md    # 如何从零运行
│   ├── verification.md       # 如何证明它工作
│   └── changes/              # 每次改动的过程记录
├── rtl/                      # Verilog/SystemVerilog/VHDL
├── tb/                       # testbench、测试向量、参考模型
├── constraints/              # XDC/SDC/QSF/引脚和时序约束
├── firmware/                 # MCU 工程或嵌入式代码
├── hardware/                 # 原理图、PCB、接口和器件资料说明
├── scripts/                  # 仿真、构建、下载、数据处理脚本
└── results/                  # 可复现实验结果、波形截图、资源报告
```

不需要的目录可以保留为空并放置 `.gitkeep`，也可以删除；但一旦项目开始使用某类内容，应使用上述固定名称。

## 文档和代码的关系

- 代码回答“怎么实现”；
- `design.md` 回答“为什么这样实现”；
- `spec.md` 回答“需要达到什么程度”；
- `getting-started.md` 回答“别人怎样运行起来”；
- `verification.md` 回答“怎样确认它真的工作”；
- `changes/` 回答“这次为什么改、改了什么、效果怎样”。

## AI 工作流

完整的 AI 协作规则见 [`AGENTS.md`](AGENTS.md)，面向人的说明见 [`docs/ai-workflow.md`](docs/ai-workflow.md)。

## 给 AI 助手的入口

AI 助手必须先读根目录 `AGENTS.md`，再读当前工程中的 `AGENTS.md`（若存在）和工程文档。不要只根据用户一句话改代码，也不要自动重排文档格式。
