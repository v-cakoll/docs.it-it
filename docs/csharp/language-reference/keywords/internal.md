---
title: internal - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: e5a5ca18828b689241abbb6d80c5adc51efb073c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173601"
---
# <a name="internal-c-reference"></a><span data-ttu-id="e22ad-102">internal (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e22ad-102">internal (C# Reference)</span></span>
<span data-ttu-id="e22ad-103">La parola chiave `internal` è un [modificatore di accesso](./access-modifiers.md) per tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="e22ad-103">The `internal` keyword is an [access modifier](./access-modifiers.md) for types and type members.</span></span>
  
 > <span data-ttu-id="e22ad-104">Questa pagina illustra l'accesso `internal`.</span><span class="sxs-lookup"><span data-stu-id="e22ad-104">This page covers `internal` access.</span></span> <span data-ttu-id="e22ad-105">La `internal` parola chiave fa [`protected internal`](./protected-internal.md) anche parte del modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="e22ad-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="e22ad-106">I tipi o membri interni sono accessibili solo all'interno di file nello stesso assembly, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e22ad-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 <span data-ttu-id="e22ad-107">Per un confronto di `internal` con altri modificatori di accesso, vedere [Livelli di accessibilità](./accessibility-levels.md) e [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="e22ad-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](./accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="e22ad-108">Per altre informazioni sugli assembly, vedere [Assembly in .NET](../../../standard/assembly/index.md).</span><span class="sxs-lookup"><span data-stu-id="e22ad-108">For more information about assemblies, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
 <span data-ttu-id="e22ad-109">Un uso comune dell'accesso interno è in fase di sviluppo basato su componenti poiché consente a un gruppo di componenti di collaborare in modo privato senza essere esposti al resto del codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e22ad-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="e22ad-110">Ad esempio, un framework per la creazione di interfacce utente grafiche potrebbe indicare le classi `Control` e `Form` che interagiscono usando membri con accesso interno.</span><span class="sxs-lookup"><span data-stu-id="e22ad-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="e22ad-111">Poiché questi membri sono interni, non sono esposti al codice che usa il framework.</span><span class="sxs-lookup"><span data-stu-id="e22ad-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="e22ad-112">Non è corretto fare riferimento a un tipo o a un membro con accesso interno all'esterno dell'assembly in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="e22ad-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e22ad-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e22ad-113">Example</span></span>  
 <span data-ttu-id="e22ad-114">Questo esempio contiene due file, `Assembly1.cs` e `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="e22ad-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="e22ad-115">Il primo file contiene una classe di base interna, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="e22ad-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="e22ad-116">Nel secondo file, un tentativo di creare un'istanza di `BaseClass` genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="e22ad-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="e22ad-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="e22ad-117">Example</span></span>  
 <span data-ttu-id="e22ad-118">In questo esempio, usare gli stessi file dell'esempio 1 e modificare il livello di accessibilità di `BaseClass` in `public`.</span><span class="sxs-lookup"><span data-stu-id="e22ad-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="e22ad-119">Modificare anche il livello di accessibilità del membro `intM` in `internal`.</span><span class="sxs-lookup"><span data-stu-id="e22ad-119">Also change the accessibility level of the member `intM` to `internal`.</span></span> <span data-ttu-id="e22ad-120">In questo caso, è possibile creare un'istanza della classe, ma non è possibile accedere al membro interno.</span><span class="sxs-lookup"><span data-stu-id="e22ad-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="e22ad-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e22ad-121">C# Language Specification</span></span>  

<span data-ttu-id="e22ad-122">Per altre informazioni, vedere [Accessibilità dichiarata](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="e22ad-122">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="e22ad-123">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="e22ad-123">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e22ad-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e22ad-124">See also</span></span>

- [<span data-ttu-id="e22ad-125">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e22ad-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e22ad-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e22ad-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e22ad-127">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e22ad-127">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="e22ad-128">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="e22ad-128">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="e22ad-129">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="e22ad-129">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="e22ad-130">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e22ad-130">Modifiers</span></span>](index.md)
- [<span data-ttu-id="e22ad-131">pubblico</span><span class="sxs-lookup"><span data-stu-id="e22ad-131">public</span></span>](./public.md)
- [<span data-ttu-id="e22ad-132">Privato</span><span class="sxs-lookup"><span data-stu-id="e22ad-132">private</span></span>](./private.md)
- [<span data-ttu-id="e22ad-133">Protetto</span><span class="sxs-lookup"><span data-stu-id="e22ad-133">protected</span></span>](./protected.md)
