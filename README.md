# Rime 配置说明

这是当前用户的 Rime / 小狼毫（Weasel）输入法配置目录，主要用于定制候选词数量、输入方案、切换中英文行为以及界面样式。

## 文件说明

- `default.custom.yaml`：全局配置补丁。
- `luna_pinyin_simp.custom.yaml`：朙月拼音·简化字方案配置补丁。
- `weasel.custom.yaml`：小狼毫界面样式配置补丁。
- `user.yaml`：Rime 自动维护的用户状态文件，一般不需要手动修改。

## 关键配置

### 全局配置：`default.custom.yaml`

```yaml
patch:
  "menu/page_size": 6
  "ascii_composer/switch_key/Shift_L": noop
  "ascii_composer/switch_key/Shift_R": noop
  schema_list:
    - {schema: luna_pinyin_simp}
```

含义：

- 候选词每页显示 `6` 个。
- 左右 `Shift` 不再用于切换中英文。
- 仅启用 `luna_pinyin_simp` 输入方案。

### 输入方案配置：`luna_pinyin_simp.custom.yaml`

```yaml
patch:
  "switches/@0/reset": 1
```

含义：

- 朙月拼音·简化字方案启动时默认进入英文 / ASCII 模式。

### 小狼毫界面：`weasel.custom.yaml`

```yaml
patch:
  "style/color_scheme": steam
  "style/font_face": "微软雅黑"
  "style/font_point": 13
  "style/horizontal": true
```

含义：

- 使用 `steam` 配色方案。
- 候选栏字体为 `微软雅黑`，字号 `13`。
- 候选栏横向显示。

## 使用方式

修改配置后，右键小狼毫托盘图标，选择 **重新部署** 使配置生效。
