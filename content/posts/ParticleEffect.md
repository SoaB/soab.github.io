---
title: "ParticleEffect"
author: "SoaB"
type: "post"
draft: true
date: 2024-11-29T18:32:15+08:00
subtitle: ""
image: ""
tags: [zig, raylib]
---
# Particle Effect

Learning Zig programming language ...

Particle effect for learning zig's struct random and raylib implementation ect. 

![O_o](images/screenpar.gif)
<!--more-->
```c
const rl = @cImport({
    @cDefine("SUPPORT_GIF_RECORDING", "1");
    @cInclude("Raylib.h");
});

const std = @import("std");
const math = std.math;
const print = std.debug.print;
const effect1 = @import("effect1.zig").Effect1;
const rand = @import("rand.zig");

const scrWidth = 800;
const scrHeight = 600;

pub fn main() !void {
    rand.init();
    rl.InitWindow(scrWidth, scrHeight, "Noise for FUN");
    rl.SetTargetFPS(60);
    effect1.init(scrWidth, scrHeight);
    while (!rl.WindowShouldClose()) {
        rl.BeginDrawing();
        rl.ClearBackground(rl.BLACK);
        effect1.update();
        effect1.draw();
        rl.EndDrawing();
    }
    rl.CloseWindow();
}
```
[完整的在這裏](https://github.com/SoaB/pAnim)