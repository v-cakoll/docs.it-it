---
title: private protected (informazioni di riferimento su C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ee36cc713dd5fdb90ae20ef992f8e75eca09597d
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="2b1b8-102">private protected (informazioni di riferimento su C#)</span><span class="sxs-lookup"><span data-stu-id="2b1b8-102">private protected (C# Reference)</span></span>
<span data-ttu-id="2b1b8-103">La combinazione delle parole chiave `private protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="2b1b8-104">Un membro protetto privato è accessibile per i tipi derivati dalla classe che lo contiene, ma solo all'interno dell'assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="2b1b8-105">Per un confronto di `private protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2b1b8-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="2b1b8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b1b8-106">Example</span></span>  
 <span data-ttu-id="2b1b8-107">Un membro protetto privato di una classe base è accessibile dai tipi derivati nell'assembly che lo contiene solo se il tipo statico della variabile è il tipo della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="2b1b8-108">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2b1b8-108">For example, consider the following code segment:</span></span>  
  
 ```csharp
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
  
```csharp  
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
 <span data-ttu-id="2b1b8-109">Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="2b1b8-110">Il primo file contiene una classe base pubblica, `BaseClass`, e un tipo derivato, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="2b1b8-111">`BaseClass` è proprietaria di un membro protetto privato, `myValue`, a cui `DerivedClass1` prova ad accedere in due modi.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="2b1b8-112">Il primo tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="2b1b8-113">Il tentativo di usarlo come membro ereditato in `DerivedClass1` avrà, tuttavia, esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="2b1b8-114">Nel secondo file un tentativo di accedere a `myValue` come membro ereditato di `DerivedClass2` genererà un errore, perché è accessibile solo per i tipi derivati in Assembly1.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="2b1b8-115">I membri struct non possono essere `private protected` perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="2b1b8-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2b1b8-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2b1b8-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b1b8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b1b8-117">See Also</span></span>  
 <span data-ttu-id="2b1b8-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2b1b8-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2b1b8-120">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2b1b8-121">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="2b1b8-122">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="2b1b8-123">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="2b1b8-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="2b1b8-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="2b1b8-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="2b1b8-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="2b1b8-127">[Problemi di sicurezza per le parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="2b1b8-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
