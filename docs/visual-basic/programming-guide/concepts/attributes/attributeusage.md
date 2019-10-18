---
title: AttributeUsage (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
ms.openlocfilehash: dbfbfaa6124eacfd9e4043eab9e4769103e554ca
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524311"
---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="7589b-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7589b-102">AttributeUsage (Visual Basic)</span></span>

<span data-ttu-id="7589b-103">Determina come usare una classe di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7589b-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="7589b-104">`AttributeUsage` è un attributo che può essere applicato alle definizioni di attributi personalizzati per controllare come può essere applicato il nuovo attributo.</span><span class="sxs-lookup"><span data-stu-id="7589b-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="7589b-105">Le impostazioni predefinite sono simili alle seguenti quando vengono applicate in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="7589b-105">The default settings look like this when applied explicitly:</span></span>

```vb
<System.AttributeUsage(System.AttributeTargets.All,
                   AllowMultiple:=False,
                   Inherited:=True)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

<span data-ttu-id="7589b-106">In questo esempio, la classe `NewAttribute` può essere applicata a qualsiasi entità di codice abilitata per l'attributo, ma può essere applicata solo una volta per ogni entità.</span><span class="sxs-lookup"><span data-stu-id="7589b-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="7589b-107">Viene ereditata dalle classi derivate quando applicata a una classe di base.</span><span class="sxs-lookup"><span data-stu-id="7589b-107">It is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="7589b-108">Gli argomenti `AllowMultiple` e `Inherited` sono facoltativi, pertanto questo codice ha lo stesso effetto:</span><span class="sxs-lookup"><span data-stu-id="7589b-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>

```vb
<System.AttributeUsage(System.AttributeTargets.All)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

<span data-ttu-id="7589b-109">Il primo argomento `AttributeUsage` deve consistere di uno o più elementi dell'enumerazione <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="7589b-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="7589b-110">Più tipi di destinazione possono essere collegati con l'operatore OR, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7589b-110">Multiple target types can be linked together with the OR operator, like this:</span></span>

```vb
Imports System
```

```vb
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>
Class NewPropertyOrFieldAttribute
    Inherits Attribute
End Class
```

<span data-ttu-id="7589b-111">Se l'argomento `AllowMultiple` è impostato su `true`, l'attributo restituito può essere applicato più volte a una singola entità, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7589b-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>

```vb
Imports System
```

```vb
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>
Class MultiUseAttr
    Inherits Attribute
End Class

<MultiUseAttr(), MultiUseAttr()>
Class Class1
End Class
```

<span data-ttu-id="7589b-112">In questo caso `MultiUseAttr` può essere applicato più volte perché `AllowMultiple` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="7589b-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="7589b-113">Entrambi i formati illustrati per applicare più attributi sono validi.</span><span class="sxs-lookup"><span data-stu-id="7589b-113">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="7589b-114">Se `Inherited` è impostato su `false`, l'attributo non viene ereditato da classi che derivano da una classe con attributi.</span><span class="sxs-lookup"><span data-stu-id="7589b-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="7589b-115">Esempio:</span><span class="sxs-lookup"><span data-stu-id="7589b-115">For example:</span></span>

```vb
Imports System
```

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

<span data-ttu-id="7589b-116">In questo caso `Attr1` non viene applicato a `DClass` attraverso l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="7589b-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="7589b-117">Note</span><span class="sxs-lookup"><span data-stu-id="7589b-117">Remarks</span></span>

<span data-ttu-id="7589b-118">L'attributo `AttributeUsage` è un attributo monouso ovvero non può essere applicato più volte alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="7589b-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="7589b-119">`AttributeUsage` è un alias per <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7589b-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="7589b-120">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="7589b-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="7589b-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7589b-121">Example</span></span>

<span data-ttu-id="7589b-122">L'esempio seguente illustra l'effetto degli argomenti `Inherited` e `AllowMultiple` nell'attributo `AttributeUsage` e come gli attributi personalizzati applicati a una classe possono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="7589b-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

```vb
Imports System
```

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

## <a name="sample-output"></a><span data-ttu-id="7589b-123">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="7589b-123">Sample Output</span></span>

```console
Attributes on Base Class:
A1
A2
Attributes on Derived Class:
A3
A3
A2
```

## <a name="see-also"></a><span data-ttu-id="7589b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7589b-124">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="7589b-125">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7589b-125">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="7589b-126">Attributi</span><span class="sxs-lookup"><span data-stu-id="7589b-126">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="7589b-127">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7589b-127">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="7589b-128">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7589b-128">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="7589b-129">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7589b-129">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="7589b-130">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7589b-130">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
