---
title: Modificatori di accesso (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: ff313df9683dbc76bab684ff484b746ad05e065a
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45988192"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="df387-102">Modificatori di accesso (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="df387-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="df387-103">I modificatori di accesso sono parole chiave usate per specificare l'accessibilità dichiarata di un membro o di un tipo.</span><span class="sxs-lookup"><span data-stu-id="df387-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="df387-104">In questa sezione vengono presentati i quattro modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="df387-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="df387-105">È possibile specificare i sei livelli di accessibilità seguenti usando i modificatori di accesso:</span><span class="sxs-lookup"><span data-stu-id="df387-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="df387-106">[`public`](public.md): l'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="df387-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="df387-107">[`protected`](protected.md): l'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="df387-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="df387-108">[`internal`](internal.md): l'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="df387-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="df387-109">[`protected internal`](protected-internal.md): l'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="df387-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="df387-110">[`private`](private.md): l'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="df387-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="df387-111">[`private protected`](private-protected.md): l'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene all'interno dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="df387-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="df387-112">In questa sezione vengono presentati anche gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="df387-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="df387-113">[Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md): uso dei quattro modificatori di accesso per dichiarare sei livelli di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="df387-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="df387-114">[Dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md): specifica in quali sezioni del programma è possibile fare riferimento a un membro.</span><span class="sxs-lookup"><span data-stu-id="df387-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="df387-115">[Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): riepilogo delle restrizioni per l'uso dei livelli di accessibilità dichiarati.</span><span class="sxs-lookup"><span data-stu-id="df387-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df387-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df387-116">See Also</span></span>  
- [<span data-ttu-id="df387-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="df387-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="df387-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="df387-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="df387-119">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="df387-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="df387-120">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="df387-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="df387-121">Parole chiave per l'accesso</span><span class="sxs-lookup"><span data-stu-id="df387-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
- [<span data-ttu-id="df387-122">Modificatori</span><span class="sxs-lookup"><span data-stu-id="df387-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
