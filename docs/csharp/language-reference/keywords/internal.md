---
title: internal (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: d2fcc19bb7bc6de373412e7728f3025647c0435d
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961482"
---
# <a name="internal-c-reference"></a><span data-ttu-id="d3f81-102">internal (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d3f81-102">internal (C# Reference)</span></span>
<span data-ttu-id="d3f81-103">La parola chiave `internal` è un [modificatore di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) per tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="d3f81-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="d3f81-104">Questa pagina illustra l'accesso `internal`.</span><span class="sxs-lookup"><span data-stu-id="d3f81-104">This page covers `internal` access.</span></span> <span data-ttu-id="d3f81-105">La parola chiave `internal` fa anche parte del modificatore di accesso [`protected internal`](./protected-internal.md).</span><span class="sxs-lookup"><span data-stu-id="d3f81-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="d3f81-106">I tipi o membri interni sono accessibili solo all'interno di file nello stesso assembly, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d3f81-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="d3f81-107">Per un confronto di `internal` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) e [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d3f81-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="d3f81-108">Per altre informazioni sugli assembly, vedere [Assembly e Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3f81-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="d3f81-109">Un uso comune dell'accesso interno è in fase di sviluppo basato su componenti poiché consente a un gruppo di componenti di collaborare in modo privato senza essere esposti al resto del codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3f81-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="d3f81-110">Ad esempio, un framework per la creazione di interfacce utente grafiche potrebbe indicare le classi `Control` e `Form` che interagiscono usando membri con accesso interno.</span><span class="sxs-lookup"><span data-stu-id="d3f81-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="d3f81-111">Poiché questi membri sono interni, non sono esposti al codice che usa il framework.</span><span class="sxs-lookup"><span data-stu-id="d3f81-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="d3f81-112">Non è corretto fare riferimento a un tipo o a un membro con accesso interno all'esterno dell'assembly in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="d3f81-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3f81-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3f81-113">Example</span></span>  
 <span data-ttu-id="d3f81-114">Questo esempio contiene due file, `Assembly1.cs` e `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="d3f81-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="d3f81-115">Il primo file contiene una classe di base interna, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="d3f81-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="d3f81-116">Nel secondo file, un tentativo di creare un'istanza di `BaseClass` genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="d3f81-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
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
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="d3f81-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3f81-117">Example</span></span>  
 <span data-ttu-id="d3f81-118">In questo esempio, usare gli stessi file dell'esempio 1 e modificare il livello di accessibilità di `BaseClass` in `public`.</span><span class="sxs-lookup"><span data-stu-id="d3f81-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="d3f81-119">Modificare anche il livello di accessibilità del membro `IntM` in `internal`.</span><span class="sxs-lookup"><span data-stu-id="d3f81-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="d3f81-120">In questo caso, è possibile creare un'istanza della classe, ma non è possibile accedere al membro interno.</span><span class="sxs-lookup"><span data-stu-id="d3f81-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
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
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="d3f81-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d3f81-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3f81-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3f81-122">See Also</span></span>  
 [<span data-ttu-id="d3f81-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d3f81-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d3f81-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d3f81-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d3f81-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="d3f81-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d3f81-126">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="d3f81-126">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="d3f81-127">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="d3f81-127">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="d3f81-128">Modificatori</span><span class="sxs-lookup"><span data-stu-id="d3f81-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="d3f81-129">public</span><span class="sxs-lookup"><span data-stu-id="d3f81-129">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="d3f81-130">private</span><span class="sxs-lookup"><span data-stu-id="d3f81-130">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="d3f81-131">protected</span><span class="sxs-lookup"><span data-stu-id="d3f81-131">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
