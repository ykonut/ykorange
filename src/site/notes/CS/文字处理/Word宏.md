---
{"dg-publish":true,"permalink":"/CS/文字处理/Word宏/","tags":["word"],"created":"2025-09-12 19:18","updated":"2025-11-21 19:39"}
---


标题自动编号

```VBA
Sub ApplyHeadingNumbering()
    Dim oListTempl As ListTemplate
    Dim oStyle As Style
    
    ' 创建新的多级列表模板
    Set oListTempl = ActiveDocument.ListTemplates.Add(True)
    
    With oListTempl
        ' 设置标题1（级别1）
        With .ListLevels(1)
            .NumberFormat = "%1"
            .NumberStyle = wdListNumberStyleArabic
            .TrailingCharacter = wdTrailingSpace
            .NumberPosition = 0
            .Alignment = wdListLevelAlignLeft
            .TextPosition = CentimetersToPoints(0.75)
            .ResetOnHigher = 0
            .StartAt = 1
        End With
        
        ' 设置标题2（级别2）
        With .ListLevels(2)
            .NumberFormat = "%1.%2"
            .NumberStyle = wdListNumberStyleArabic
            .TrailingCharacter = wdTrailingSpace
            .NumberPosition = CentimetersToPoints(0.75)
            .Alignment = wdListLevelAlignLeft
            .TextPosition = CentimetersToPoints(1.5)
            .ResetOnHigher = 1
            .StartAt = 1
        End With
        
        ' 设置标题3（级别3）
        With .ListLevels(3)
            .NumberFormat = "%1.%2.%3"
            .NumberStyle = wdListNumberStyleArabic
            .TrailingCharacter = wdTrailingSpace
            .NumberPosition = CentimetersToPoints(1.5)
            .Alignment = wdListLevelAlignLeft
            .TextPosition = CentimetersToPoints(2.25)
            .ResetOnHigher = 2
            .StartAt = 1
        End With
        
        ' 设置标题4（级别4）
        With .ListLevels(4)
            .NumberFormat = "%1.%2.%3.%4"
            .NumberStyle = wdListNumberStyleArabic
            .TrailingCharacter = wdTrailingSpace
            .NumberPosition = CentimetersToPoints(2.25)
            .Alignment = wdListLevelAlignLeft
            .TextPosition = CentimetersToPoints(3.0)
            .ResetOnHigher = 3
            .StartAt = 1
        End With
    End With

    ' 将样式链接到列表级别
    For Each oStyle In ActiveDocument.Styles
        Select Case oStyle.NameLocal
            Case "标题 1"
                oStyle.LinkToListTemplate oListTempl, 1
            Case "标题 2"
                oStyle.LinkToListTemplate oListTempl, 2
            Case "标题 3"
                oStyle.LinkToListTemplate oListTempl, 3
            Case "标题 4"
                oStyle.LinkToListTemplate oListTempl, 4
        End Select
    Next oStyle
End Sub
```
