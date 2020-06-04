---
title: AttributeUsage
ms.date: 07/20/2015
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
ms.openlocfilehash: 677d49aba38801f2adf42cc745983af30b3eddc5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400732"
---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)

Determina come usare una classe di attributi personalizzati. `AttributeUsage` è un attributo che può essere applicato alle definizioni di attributi personalizzati per controllare come può essere applicato il nuovo attributo. Le impostazioni predefinite sono simili alle seguenti quando vengono applicate in modo esplicito:

```vb
<System.AttributeUsage(System.AttributeTargets.All,
                   AllowMultiple:=False,
                   Inherited:=True)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

In questo esempio, la classe `NewAttribute` può essere applicata a qualsiasi entità di codice abilitata per l'attributo, ma può essere applicata solo una volta per ogni entità. Viene ereditata dalle classi derivate quando applicata a una classe di base.

Gli argomenti `AllowMultiple` e `Inherited` sono facoltativi, pertanto questo codice ha lo stesso effetto:

```vb
<System.AttributeUsage(System.AttributeTargets.All)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

Il primo argomento `AttributeUsage` deve consistere di uno o più elementi dell'enumerazione <xref:System.AttributeTargets>. Più tipi di destinazione possono essere collegati con l'operatore OR, nel modo seguente:

```vb
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>
Class NewPropertyOrFieldAttribute
    Inherits Attribute
End Class
```

Se l'argomento `AllowMultiple` è impostato su `true`, l'attributo restituito può essere applicato più volte a una singola entità, nel modo seguente:

```vb
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>
Class MultiUseAttr
    Inherits Attribute
End Class

<MultiUseAttr(), MultiUseAttr()>
Class Class1
End Class
```

In questo caso `MultiUseAttr` può essere applicato più volte perché `AllowMultiple` è impostato su `true`. Entrambi i formati illustrati per applicare più attributi sono validi.

Se `Inherited` è impostato su `false`, l'attributo non viene ereditato da classi che derivano da una classe con attributi. Ad esempio:

```vb
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>
Class Attr1
    Inherits Attribute
End Class

<Attr1()>
Class BClass

End Class

Class DClass
    Inherits BClass
End Class
```

In questo caso `Attr1` non viene applicato a `DClass` attraverso l'ereditarietà.

## <a name="remarks"></a>Commenti

L'attributo `AttributeUsage` è un attributo monouso ovvero non può essere applicato più volte alla stessa classe. `AttributeUsage` è un alias per <xref:System.AttributeUsageAttribute>.

Per altre informazioni, vedere [Accesso agli attributi tramite reflection (Visual Basic)](accessing-attributes-by-using-reflection.md).

## <a name="example"></a>Esempio

L'esempio seguente illustra l'effetto degli argomenti `Inherited` e `AllowMultiple` nell'attributo `AttributeUsage` e come gli attributi personalizzati applicati a una classe possono essere enumerati.

```vb
' Create some custom attributes:
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>
Class A1
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class)>
Class A2
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>
Class A3
    Inherits System.Attribute
End Class

' Apply custom attributes to classes:
<A1(), A2()>
Class BaseClass

End Class

<A3(), A3()>
Class DerivedClass
    Inherits BaseClass
End Class

Public Class TestAttributeUsage
    Sub Main()
        Dim b As New BaseClass
        Dim d As New DerivedClass
        ' Display custom attributes for each class.
        Console.WriteLine("Attributes on Base Class:")
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)

        For Each attr In attrs
            Console.WriteLine(attr)
        Next

        Console.WriteLine("Attributes on Derived Class:")
        attrs = d.GetType().GetCustomAttributes(True)
        For Each attr In attrs
            Console.WriteLine(attr)
        Next
    End Sub
End Class
```

## <a name="sample-output"></a>Output di esempio

```console
Attributes on Base Class:
A1
A2
Attributes on Derived Class:
A3
A3
A2
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Guida per programmatori Visual Basic](../../index.md)
- [Attributi](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../reflection.md)
- [Attributi (Visual Basic)](../../../language-reference/attributes.md)
- [Creazione di attributi personalizzati (Visual Basic)](creating-custom-attributes.md)
- [Accesso agli attributi tramite reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)
