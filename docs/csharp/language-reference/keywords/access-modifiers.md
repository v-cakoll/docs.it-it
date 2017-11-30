---
title: Modificatori di accesso (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="bc194-102">Modificatori di accesso (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bc194-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="bc194-103">I modificatori di accesso sono parole chiave usate per specificare l'accessibilità dichiarata di un membro o di un tipo.</span><span class="sxs-lookup"><span data-stu-id="bc194-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="bc194-104">In questa sezione vengono presentati i quattro modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="bc194-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="bc194-105">public</span><span class="sxs-lookup"><span data-stu-id="bc194-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="bc194-106">protected</span><span class="sxs-lookup"><span data-stu-id="bc194-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="bc194-107">internal</span><span class="sxs-lookup"><span data-stu-id="bc194-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="bc194-108">private</span><span class="sxs-lookup"><span data-stu-id="bc194-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="bc194-109">È possibile specificare i seguenti sei livelli di accessibilità utilizzando i modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="bc194-109">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="bc194-110">`public`: l'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="bc194-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="bc194-111">`protected`: l'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="bc194-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="bc194-112">`internal`: l'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="bc194-112">`internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="bc194-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): L'accesso è limitato all'assembly corrente o i tipi derivati dalla classe di appartenenza.</span><span class="sxs-lookup"><span data-stu-id="bc194-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="bc194-114">`private`: l'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="bc194-114">`private`: Access is limited to the containing type.</span></span>  

 <span data-ttu-id="bc194-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): L'accesso è limitato a una classe o i tipi derivati dalla classe di appartenenza all'interno dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="bc194-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="bc194-116">In questa sezione vengono presentati anche gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc194-116">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="bc194-117">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md): utilizzo di quattro modificatori di accesso per dichiarare sei livelli di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="bc194-117">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="bc194-118">[Dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md): specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="bc194-118">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="bc194-119">[Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): riepilogo delle restrizioni per l'uso dei livelli di accessibilità dichiarati.</span><span class="sxs-lookup"><span data-stu-id="bc194-119">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc194-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc194-120">See Also</span></span>  
 [<span data-ttu-id="bc194-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bc194-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bc194-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bc194-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bc194-123">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="bc194-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="bc194-124">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="bc194-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="bc194-125">Parole chiave per l'accesso</span><span class="sxs-lookup"><span data-stu-id="bc194-125">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="bc194-126">Modificatori</span><span class="sxs-lookup"><span data-stu-id="bc194-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
