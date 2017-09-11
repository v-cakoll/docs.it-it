---
title: AttributeUsage (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c008c1a696e93bc3b756a926a046aa5a6942bc10
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="attributeusage-c"></a><span data-ttu-id="ae100-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="ae100-102">AttributeUsage (C#)</span></span>
<span data-ttu-id="ae100-103">Determina come usare una classe di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ae100-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="ae100-104">`AttributeUsage` è un attributo che può essere applicato alle definizioni di attributi personalizzati per controllare come può essere applicato il nuovo attributo.</span><span class="sxs-lookup"><span data-stu-id="ae100-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="ae100-105">Le impostazioni predefinite sono simili alle seguenti quando vengono applicate in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="ae100-105">The default settings look like this when applied explicitly:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="ae100-106">In questo esempio, la classe `NewAttribute` può essere applicata a qualsiasi entità di codice abilitata per l'attributo, ma può essere applicata solo una volta per ogni entità.</span><span class="sxs-lookup"><span data-stu-id="ae100-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="ae100-107">Viene ereditata dalle classi derivate quando applicata a una classe di base.</span><span class="sxs-lookup"><span data-stu-id="ae100-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="ae100-108">Gli argomenti `AllowMultiple` e `Inherited` sono facoltativi, pertanto questo codice ha lo stesso effetto:</span><span class="sxs-lookup"><span data-stu-id="ae100-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="ae100-109">Il primo argomento `AttributeUsage` deve consistere di uno o più elementi dell'enumerazione <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="ae100-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="ae100-110">Più tipi di destinazione possono essere collegati con l'operatore OR, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ae100-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 <span data-ttu-id="ae100-111">Se l'argomento `AllowMultiple` è impostato su `true`, l'attributo restituito può essere applicato più volte a una singola entità, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ae100-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 <span data-ttu-id="ae100-112">In questo caso `MultiUseAttr` può essere applicato più volte perché `AllowMultiple` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="ae100-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="ae100-113">Entrambi i formati illustrati per applicare più attributi sono validi.</span><span class="sxs-lookup"><span data-stu-id="ae100-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="ae100-114">Se `Inherited` è impostato su `false`, l'attributo non viene ereditato da classi che derivano da una classe con attributi.</span><span class="sxs-lookup"><span data-stu-id="ae100-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="ae100-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ae100-115">For example:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 <span data-ttu-id="ae100-116">In questo caso `Attr1` non viene applicato a `DClass` attraverso l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="ae100-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae100-117">Note</span><span class="sxs-lookup"><span data-stu-id="ae100-117">Remarks</span></span>  
 <span data-ttu-id="ae100-118">L'attributo `AttributeUsage` è un attributo monouso ovvero non può essere applicato più volte alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="ae100-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="ae100-119">`AttributeUsage` è un alias per <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ae100-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="ae100-120">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="ae100-120">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae100-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae100-121">Example</span></span>  
 <span data-ttu-id="ae100-122">L'esempio seguente illustra l'effetto degli argomenti `Inherited` e `AllowMultiple` nell'attributo `AttributeUsage` e come gli attributi personalizzati applicati a una classe possono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="ae100-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a><span data-ttu-id="ae100-123">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="ae100-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae100-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae100-124">See Also</span></span>  
 <span data-ttu-id="ae100-125"><xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="ae100-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="ae100-126"><xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="ae100-126"><xref:System.Reflection></span></span>   
 <span data-ttu-id="ae100-127">[Guida per programmatori C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae100-127">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ae100-128">[Attributi](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="ae100-128">[Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
 <span data-ttu-id="ae100-129">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="ae100-129">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 <span data-ttu-id="ae100-130">[Attributi](../../../../csharp/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae100-130">[Attributes](../../../../csharp/programming-guide/concepts/attributes/index.md) </span></span>  
 <span data-ttu-id="ae100-131">[Creazione di attributi personalizzati (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ae100-131">[Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
 <span data-ttu-id="ae100-132">[Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Accesso agli attributi tramite reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="ae100-132">[Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>

