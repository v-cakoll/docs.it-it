---
title: privato protetto (riferimenti per c#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="d5b51-102">privato protetto (riferimenti per c#)</span><span class="sxs-lookup"><span data-stu-id="d5b51-102">private protected (C# Reference)</span></span>
<span data-ttu-id="d5b51-103">Il `private protected` combinazione di parole chiave è un modificatore di accesso di membro.</span><span class="sxs-lookup"><span data-stu-id="d5b51-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="d5b51-104">Un membro protetto privato è accessibile da tipi derivati dalla classe di appartenenza, ma solo all'interno del relativo assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="d5b51-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="d5b51-105">Per un confronto di `private protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d5b51-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="d5b51-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5b51-106">Example</span></span>  
 <span data-ttu-id="d5b51-107">Un membro privato protetto di una classe base è accessibile da tipi derivati nel relativo assembly contenitore solo se il tipo statico della variabile è il tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d5b51-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="d5b51-108">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d5b51-108">For example, consider the following code segment:</span></span>  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 <span data-ttu-id="d5b51-109">Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="d5b51-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="d5b51-110">Il primo file contiene una classe base pubblica, `BaseClass`e un tipo derivato da esso, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="d5b51-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="d5b51-111">`BaseClass`proprietario di un membro privato protetto, `myValue`, che `DerivedClass1` tenta di accedere in due modi.</span><span class="sxs-lookup"><span data-stu-id="d5b51-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="d5b51-112">Il primo tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="d5b51-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="d5b51-113">Tuttavia, il tentativo di utilizzo di un membro ereditato in `DerivedClass1` avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d5b51-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="d5b51-114">Nel secondo file, un tentativo di accedere a `myValue` di un membro ereditato di `DerivedClass2` genererà un errore, in quanto sono solo accessibili dai tipi derivati in Assembly1.</span><span class="sxs-lookup"><span data-stu-id="d5b51-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="d5b51-115">I membri struct non possono essere `private protected` perché lo struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="d5b51-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d5b51-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d5b51-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5b51-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5b51-117">See Also</span></span>  
 <span data-ttu-id="d5b51-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d5b51-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d5b51-120">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d5b51-121">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="d5b51-122">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="d5b51-123">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="d5b51-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="d5b51-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="d5b51-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="d5b51-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="d5b51-127">[Problemi di sicurezza per parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="d5b51-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
