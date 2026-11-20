# 闲鱼商品文案配图助手

> 把一个商品的关键信息，整理为可编辑的中文闲鱼商品文案，并生成一组商品介绍图的脚本与图片。

作者：泽言  
版本：完整公开版  
授权：个人使用，不可转售

## 能做什么

- 通过循序提问收集商品名称、功能、交付物、适用人群、发货及售后等事实。
- 生成可直接修改发布的闲鱼商品标题、卖点、交付说明、适合谁与风险说明。
- 对容易造成误解、绝对化承诺或不清晰的表达进行改写；不保证任何平台审核结果。
- 内置 **30 种中文商品图风格**，可由用户选择。
- 默认规划并生成 5 张 3:4 竖版商品介绍图；也可按 6、8、10 张等指定数量自动拆分内容。
- 每张图只使用已确认的商品事实，不臆造功能、资质、价格或售后承诺。

## 包含的完整素材

本仓库包含技能运行所需的完整交付素材，不是删减演示版：

- 技能主说明 `SKILL.md`
- 信息收集表与文案合规改写规则
- 成套商品图工作流
- 30 种风格的完整提示词库 `references/styles.json`
- Codex 技能展示信息 `agents/openai.yaml`

## 给 Codex 的安装方式

发布到 GitHub 后，在 Codex 新开一个对话，粘贴下面这段话：

```text
请使用 $skill-installer 从这个 GitHub 地址安装技能：
https://github.com/zeyan-ai/xianyu-listing-kit/tree/main/skills/xianyu-listing-kit

安装完成后告诉我技能名称，以及怎样开始使用。
```

安装完成后，可在新对话中输入：

```text
$xianyu-listing-kit
我想做一个闲鱼商品，商品名称是：______
```

> 若你的 Codex 没有自动识别 `$skill-installer`，可将同一段安装请求直接发送给 Codex；它会按 GitHub 中的技能目录进行安装。安装后重新开启一个对话，确保加载到新技能。

## 给 WorkBuddy 的安装尝试

不同版本的 WorkBuddy 对 Agent Skills 的支持情况不同。可直接把下方内容发送给它：

```text
请从下面的 GitHub 地址安装这个 Agent Skill，并告诉我安装是否成功：
https://github.com/zeyan-ai/xianyu-listing-kit/tree/main/skills/xianyu-listing-kit
```

如果它提示不支持 GitHub 技能安装，请使用其导入本地文件/技能包功能，选择 `skills/xianyu-listing-kit` 这个目录或本仓库的 ZIP 包。

## 使用示例

```text
$xianyu-listing-kit
我要创建的商品名称是：小红书商品销量监控工作台保搭建教学含指令
```

接着如实回答技能提出的问题，例如：商品做什么、买家收到什么、适合谁、发货形式、是否虚拟交付、售后/退款规则。最后选择风格和图片数量即可。

## 目录结构

```text
skills/
  xianyu-listing-kit/
    SKILL.md
    agents/openai.yaml
    references/
      intake.md
      copy-compliance.md
      image-workflow.md
      styles.json
```

## 使用边界

本技能协助整理用户提供的事实与制作介绍图，不会自动发布商品，也不能代替用户确认商品真实性、平台规则或审核结果。请在发布前自行核对文案、价格、交付内容及售后规则。

## 授权说明

本项目为公开的完整个人使用版。你可以安装、学习和用于自己的个人/内部工作流；不得将本项目、其完整或部分提示词、风格库、素材或改编版本单独打包、转售、再分发或以付费形式提供给他人。详见 [LICENSE.md](LICENSE.md)。
