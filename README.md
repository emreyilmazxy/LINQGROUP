# LINQ GroupJoin Uygulaması

Bu C# konsol uygulamasında, öğrenciler (`students`) ve sınıflar (`classes`) listeleri `GroupJoin` kullanılarak eşleştirilmiştir.

## 🔹 Amaç
Her sınıfa ait öğrencileri gruplayarak sınıf adı ve o sınıfa kayıtlı öğrencileri ekrana yazdırmak.

## 🧩 Kullanılan LINQ Yapısı

```csharp
var result = classes.GroupJoin(
    students,
    cls => cls.ClassId,
    std => std.ClassId,
    (cls, studentGroup) => new
    {
        className = cls.ClassName,
        students = studentGroup.Select(s => s.StudentName)
    });
