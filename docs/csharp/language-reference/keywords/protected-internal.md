---
title: protected internal (Riferimenti per C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="7eb92-102">protected internal (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7eb92-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="7eb92-103">La combinazione delle parole chiave `protected internal` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="7eb92-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="7eb92-104">Un membro protected internal è accessibile dall'assembly corrente o dai tipi che derivano dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="7eb92-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="7eb92-105">Per un confronto di `protected internal` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7eb92-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="7eb92-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7eb92-106">Example</span></span>  
 <span data-ttu-id="7eb92-107">Un membro protected internal di una classe base è accessibile da qualsiasi tipo all'interno dell'assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="7eb92-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="7eb92-108">È inoltre accessibile in una classe derivata che si trova in un altro assembly solo se l'accesso viene eseguito tramite una variabile del tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="7eb92-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="7eb92-109">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb92-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```csharp  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 <span data-ttu-id="7eb92-110">Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="7eb92-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="7eb92-111">Il primo file contiene una classe base pubblica, `BaseClass`, e un'altra classe, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="7eb92-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="7eb92-112">`BaseClass` è proprietario di un membro protected internal, `myValue`, a cui si accede dal tipo `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="7eb92-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="7eb92-113">Nel secondo file un tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` produrrà un errore, mentre l'accesso a questo membro tramite un'istanza di una classe derivata, `DerivedClass`, avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7eb92-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="7eb92-114">I membri struct non possono essere `protected internal` perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="7eb92-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7eb92-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7eb92-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7eb92-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eb92-116">See Also</span></span>  
 <span data-ttu-id="7eb92-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7eb92-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7eb92-119">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="7eb92-120">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="7eb92-121">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="7eb92-122">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="7eb92-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="7eb92-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="7eb92-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="7eb92-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="7eb92-126">[Problemi di sicurezza per le parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="7eb92-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
