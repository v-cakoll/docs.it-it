---
title: protected (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: a3115fe82b452f52ee75cf222302ece0fc67b330
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269570"
---
# <a name="protected-c-reference"></a><span data-ttu-id="17827-102">protected (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="17827-102">protected (C# Reference)</span></span>
<span data-ttu-id="17827-103">La parola chiave `protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="17827-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="17827-104">Questa pagina illustra l'accesso `protected`.</span><span class="sxs-lookup"><span data-stu-id="17827-104">This page covers `protected` access.</span></span> <span data-ttu-id="17827-105">La parola chiave `protected` fa anche parte dei modificatori di accesso [`protected internal`](./protected-internal.md) e [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="17827-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="17827-106">Un membro protetto è accessibile all'interno della classe di appartenenza e dalle istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="17827-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="17827-107">Per un confronto di `protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="17827-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="17827-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="17827-108">Example</span></span>  
 <span data-ttu-id="17827-109">Un membro protetto di una classe di base è accessibile in una classe derivata solo se viene eseguito l'accesso tramite il tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="17827-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="17827-110">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="17827-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="17827-111">L'istruzione `a.x = 10` genera un errore perché usata all'interno del metodo statico Main e non in un'istanza della classe B.</span><span class="sxs-lookup"><span data-stu-id="17827-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="17827-112">I membri struct non possono essere protetti perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="17827-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17827-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="17827-113">Example</span></span>  
 <span data-ttu-id="17827-114">In questo esempio la classe `DerivedPoint` è derivata da `Point`.</span><span class="sxs-lookup"><span data-stu-id="17827-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="17827-115">Pertanto, è possibile accedere i membri protetti della classe di base direttamente dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="17827-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="17827-116">Se si impostano i livelli di accesso di `x` e `y` su [privato](../../../csharp/language-reference/keywords/private.md), il compilatore genererà i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="17827-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="17827-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="17827-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="17827-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17827-118">See Also</span></span>  
 [<span data-ttu-id="17827-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="17827-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="17827-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="17827-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="17827-121">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="17827-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="17827-122">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="17827-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="17827-123">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="17827-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="17827-124">Modificatori</span><span class="sxs-lookup"><span data-stu-id="17827-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="17827-125">public</span><span class="sxs-lookup"><span data-stu-id="17827-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="17827-126">private</span><span class="sxs-lookup"><span data-stu-id="17827-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="17827-127">internal</span><span class="sxs-lookup"><span data-stu-id="17827-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="17827-128">[Problemi di sicurezza per le parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="17827-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>