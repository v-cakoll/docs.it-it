---
title: Modificatori di accesso (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
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
ms.openlocfilehash: a3ad46580561500d9f011da4997007023a3bc844
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="3eecb-102">Modificatori di accesso (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3eecb-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="3eecb-103">I modificatori di accesso sono parole chiave usate per specificare l'accessibilità dichiarata di un membro o di un tipo.</span><span class="sxs-lookup"><span data-stu-id="3eecb-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="3eecb-104">In questa sezione vengono presentati i quattro modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="3eecb-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="3eecb-105">public</span><span class="sxs-lookup"><span data-stu-id="3eecb-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="3eecb-106">protected</span><span class="sxs-lookup"><span data-stu-id="3eecb-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="3eecb-107">internal</span><span class="sxs-lookup"><span data-stu-id="3eecb-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="3eecb-108">private</span><span class="sxs-lookup"><span data-stu-id="3eecb-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="3eecb-109">È possibile specificare i seguenti cinque livelli di accessibilità usando i modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="3eecb-109">The following five accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="3eecb-110">`public`: l'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="3eecb-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="3eecb-111">`protected`: l'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="3eecb-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="3eecb-112">`Internal`: l'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="3eecb-112">`Internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="3eecb-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): l'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="3eecb-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="3eecb-114">`private`: l'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="3eecb-114">`private`: Access is limited to the containing type.</span></span>  
  
 <span data-ttu-id="3eecb-115">In questa sezione vengono presentati anche gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3eecb-115">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="3eecb-116">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md): uso dei quattro modificatori di accesso per dichiarare cinque livelli di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="3eecb-116">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare five levels of accessibility.</span></span>  
  
-   <span data-ttu-id="3eecb-117">[Dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md): specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="3eecb-117">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="3eecb-118">[Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): riepilogo delle restrizioni per l'uso dei livelli di accessibilità dichiarati.</span><span class="sxs-lookup"><span data-stu-id="3eecb-118">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eecb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eecb-119">See Also</span></span>  
 <span data-ttu-id="3eecb-120">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3eecb-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3eecb-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3eecb-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3eecb-122">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3eecb-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3eecb-123">[Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="3eecb-123">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="3eecb-124">[Parole chiave per l'accesso](../../../csharp/language-reference/keywords/access-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="3eecb-124">[Access Keywords](../../../csharp/language-reference/keywords/access-keywords.md) </span></span>  
 [<span data-ttu-id="3eecb-125">Modificatori</span><span class="sxs-lookup"><span data-stu-id="3eecb-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

