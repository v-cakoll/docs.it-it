---
title: protected internal (riferimenti per c#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="a0c7e-102">protected internal (riferimenti per c#)</span><span class="sxs-lookup"><span data-stu-id="a0c7e-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="a0c7e-103">Il `protected internal` combinazione di parole chiave è un modificatore di accesso di membro.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a0c7e-104">Un membro interno protetto è accessibile dall'assembly corrente o dai tipi che derivano dalla classe di appartenenza.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="a0c7e-105">Per un confronto di `protected internal` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a0c7e-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="a0c7e-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0c7e-106">Example</span></span>  
 <span data-ttu-id="a0c7e-107">Un membro protetto interno di una classe base è accessibile da qualsiasi tipo all'interno del relativo assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="a0c7e-108">È inoltre possibile accedere in una classe derivata che si trova in un altro assembly solo se viene eseguito l'accesso tramite una variabile del tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="a0c7e-109">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a0c7e-109">For example, consider the following code segment:</span></span>  

```
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
  
```  
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
 <span data-ttu-id="a0c7e-110">Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="a0c7e-111">Il primo file contiene una classe base pubblica, `BaseClass`e un'altra classe, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="a0c7e-112">`BaseClass`proprietario di un membro interno protetto `myValue`, che avviene mediante il `TestAccess` tipo.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="a0c7e-113">Nel secondo file, un tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` produrrà un errore, durante l'accesso a questo membro tramite un'istanza di una classe derivata, `DerivedClass` avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="a0c7e-114">I membri struct non possono essere `protected internal` perché lo struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a0c7e-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a0c7e-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a0c7e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0c7e-116">See Also</span></span>  
 <span data-ttu-id="a0c7e-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a0c7e-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a0c7e-119">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a0c7e-120">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="a0c7e-121">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="a0c7e-122">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="a0c7e-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="a0c7e-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="a0c7e-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="a0c7e-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="a0c7e-126">[Problemi di sicurezza per parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="a0c7e-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
