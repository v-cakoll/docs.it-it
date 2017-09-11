---
title: protected (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c3d24389f66edec313d4f5238b0aee02518e33b7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="protected-c-reference"></a><span data-ttu-id="db51b-102">protected (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="db51b-102">protected (C# Reference)</span></span>
<span data-ttu-id="db51b-103">La parola chiave `protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="db51b-103">The `protected` keyword is a member access modifier.</span></span> <span data-ttu-id="db51b-104">Un membro protetto è accessibile all'interno della classe di appartenenza e dalle istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db51b-104">A protected member is accessible within its class and by derived class instances.</span></span> <span data-ttu-id="db51b-105">Per un confronto di `protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="db51b-105">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db51b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="db51b-106">Example</span></span>  
 <span data-ttu-id="db51b-107">Un membro protetto di una classe di base è accessibile in una classe derivata solo se viene eseguito l'accesso tramite il tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db51b-107">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="db51b-108">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="db51b-108">For example, consider the following code segment:</span></span>  
  
 <span data-ttu-id="db51b-109">[!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="db51b-109">[!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]</span></span>  
  
 <span data-ttu-id="db51b-110">L'istruzione `a.x = 10` genera un errore perché usata all'interno del metodo statico Main e non in un'istanza della classe B.</span><span class="sxs-lookup"><span data-stu-id="db51b-110">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="db51b-111">I membri struct non possono essere protetti perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="db51b-111">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db51b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="db51b-112">Example</span></span>  
 <span data-ttu-id="db51b-113">In questo esempio la classe `DerivedPoint` è derivata da `Point`.</span><span class="sxs-lookup"><span data-stu-id="db51b-113">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="db51b-114">Pertanto, è possibile accedere i membri protetti della classe di base direttamente dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db51b-114">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 <span data-ttu-id="db51b-115">[!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="db51b-115">[!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]</span></span>  
  
 <span data-ttu-id="db51b-116">Se si impostano i livelli di accesso di `x` e `y` su [privato](../../../csharp/language-reference/keywords/private.md), il compilatore genererà i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="db51b-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="db51b-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="db51b-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db51b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db51b-118">See Also</span></span>  
 <span data-ttu-id="db51b-119">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="db51b-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="db51b-121">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-121">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="db51b-122">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-122">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="db51b-123">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-123">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="db51b-124">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-124">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="db51b-125">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-125">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="db51b-126">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="db51b-126">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="db51b-127">internal</span><span class="sxs-lookup"><span data-stu-id="db51b-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

