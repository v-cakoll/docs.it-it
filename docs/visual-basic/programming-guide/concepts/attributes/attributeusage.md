---
title: AttributeUsage (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c91f2686a03d2590e1aaf166d27c49744bb13c9b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="5cd95-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd95-102">AttributeUsage (Visual Basic)</span></span>
<span data-ttu-id="5cd95-103">Determina come è possibile utilizzare una classe di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5cd95-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="5cd95-104">`AttributeUsage`è un attributo che può essere applicato alle definizioni di attributo personalizzato per controllare come può essere applicato il nuovo attributo.</span><span class="sxs-lookup"><span data-stu-id="5cd95-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="5cd95-105">Le impostazioni predefinite simile al seguente quando applicato in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="5cd95-105">The default settings look like this when applied explicitly:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="5cd95-106">In questo esempio, la `NewAttribute` classe può essere applicato a qualsiasi entità di codice in grado di attributo, ma può essere applicato solo una volta per ogni entità.</span><span class="sxs-lookup"><span data-stu-id="5cd95-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="5cd95-107">Viene ereditata dalle classi derivate quando applicato a una classe di base.</span><span class="sxs-lookup"><span data-stu-id="5cd95-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="5cd95-108">Il `AllowMultiple` e `Inherited` gli argomenti sono facoltativi, pertanto questo codice ha lo stesso effetto:</span><span class="sxs-lookup"><span data-stu-id="5cd95-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="5cd95-109">Il primo `AttributeUsage` argomento deve essere uno o più elementi del <xref:System.AttributeTargets>enumerazione.</xref:System.AttributeTargets></span><span class="sxs-lookup"><span data-stu-id="5cd95-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="5cd95-110">Più tipi di destinazione possono essere collegati con l'operatore OR, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5cd95-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 <span data-ttu-id="5cd95-111">Se il `AllowMultiple` argomento è impostato su `true`, quindi l'attributo risulta può essere applicato più volte per una singola entità, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5cd95-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
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
  
 <span data-ttu-id="5cd95-112">In questo caso `MultiUseAttr` può essere applicato più volte perché `AllowMultiple` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="5cd95-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="5cd95-113">Entrambi i formati indicati per applicare più attributi sono validi.</span><span class="sxs-lookup"><span data-stu-id="5cd95-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="5cd95-114">Se `Inherited` è impostato su `false`, quindi l'attributo non viene ereditato da classi che derivano da una classe con attribuita.</span><span class="sxs-lookup"><span data-stu-id="5cd95-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="5cd95-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5cd95-115">For example:</span></span>  
  
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
  
 <span data-ttu-id="5cd95-116">In questo caso `Attr1` non viene applicata ai `DClass` tramite ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="5cd95-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cd95-117">Note</span><span class="sxs-lookup"><span data-stu-id="5cd95-117">Remarks</span></span>  
 <span data-ttu-id="5cd95-118">Il `AttributeUsage` è un attributo monouso ovvero non può essere applicato più volte alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="5cd95-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="5cd95-119">`AttributeUsage`è un alias per <xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute></span><span class="sxs-lookup"><span data-stu-id="5cd95-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="5cd95-120">Per ulteriori informazioni, vedere [accesso agli attributi tramite Reflection utilizzando (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="5cd95-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cd95-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="5cd95-121">Example</span></span>  
 <span data-ttu-id="5cd95-122">Nell'esempio seguente viene illustrato l'effetto di `Inherited` e `AllowMultiple` argomenti per il `AttributeUsage` attributo, e come è possono enumerare gli attributi personalizzati applicati a una classe.</span><span class="sxs-lookup"><span data-stu-id="5cd95-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
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
  
## <a name="sample-output"></a><span data-ttu-id="5cd95-123">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="5cd95-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cd95-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cd95-124">See Also</span></span>  
 <span data-ttu-id="5cd95-125"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="5cd95-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="5cd95-126"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="5cd95-126"><xref:System.Reflection></span></span>   
<span data-ttu-id="5cd95-127"> [Guida per programmatori Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5cd95-127"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="5cd95-128"> [Attributi](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="5cd95-128"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="5cd95-129"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="5cd95-129"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="5cd95-130"> [Attributi (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="5cd95-130"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="5cd95-131"> [Creazione di attributi personalizzati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="5cd95-131"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="5cd95-132"> [Accesso agli attributi tramite Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="5cd95-132"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
