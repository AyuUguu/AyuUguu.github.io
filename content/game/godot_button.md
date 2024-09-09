---
title: GodotのButtonに関して
date: 2024-09-10T03:35:46+09:00
draft: false
toc: false
images:
tag:
- Godot
---

## ボタンに関する資料

[公式ドキュメント](https://docs.godotengine.org/en/4.3/classes/class_button.html)はここ。


## 作成と簡易的な設定例



```gdscript

var button = Button.new()
button.text = "Click me"
button.icon = load("res://image.png")
button.name = "button_1"
button.icon_alignment = HORIZONTAL_ALIGNMENT_CENTER
button.position = Vector2(100, 500)

#通常・カーソル・押した状態別のスタイル
var normal_style = StyleBoxFlat.new()
var hover_style = StyleBoxFlat.new()
var pressed_style = StyleBoxFlat.new()
button.add_theme_stylebox_override("normal", normal_style)
button.add_theme_stylebox_override("hover", hover_style)
button.add_theme_stylebox_override("pressed", pressed_style)
    
#シグナルの接続
button.pressed.connect(self._button_pressed)
add_child(button)

func _button_pressed():
    print("Hello world!")

  ```
