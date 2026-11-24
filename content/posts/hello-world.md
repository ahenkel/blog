---
title: "Hello, World"
date: 2026-11-24
draft: true
tags: ["meta", "al", "csharp"]
summary: "A sample post showing AL and C# code blocks. Rewrite or delete it before publishing."
---

This is a sample post. It stays a draft (`draft: true`), so it shows up when you run the
local server but is not published to GitHub Pages.

## AL

```al
codeunit 50100 "Hello World"
{
    trigger OnRun()
    var
        Customer: Record Customer;
    begin
        if Customer.FindFirst() then
            Message('Hello, %1!', Customer.Name);
    end;
}
```

## C#

```csharp
var greeting = $"Hello from .NET {Environment.Version}";
Console.WriteLine(greeting);
```
