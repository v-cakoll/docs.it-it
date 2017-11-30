---
title: "Livelli di accessibilità (Riferimenti per C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="30be0-102">Livelli di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="30be0-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="30be0-103">Usano i modificatori di accesso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) per specificare uno dei livelli seguenti di accessibilità dichiarata per i membri.</span><span class="sxs-lookup"><span data-stu-id="30be0-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="30be0-104">Accessibilità dichiarata</span><span class="sxs-lookup"><span data-stu-id="30be0-104">Declared accessibility</span></span>|<span data-ttu-id="30be0-105">Significato</span><span class="sxs-lookup"><span data-stu-id="30be0-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="30be0-106">L'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="30be0-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="30be0-107">L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="30be0-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="30be0-108">L'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="30be0-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="30be0-109">L'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="30be0-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="30be0-110">L'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="30be0-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="30be0-111">Accesso è limitato a una classe o i tipi derivati dalla classe di appartenenza all'interno dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="30be0-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>|  
  
 <span data-ttu-id="30be0-112">Solo un modificatore di accesso è consentito per un membro o un tipo, tranne quando si utilizza il `protected internal` o `private protected` combinazioni.</span><span class="sxs-lookup"><span data-stu-id="30be0-112">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="30be0-113">I modificatori di accesso non sono consentiti negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="30be0-113">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="30be0-114">Gli spazi dei nomi non hanno restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="30be0-114">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="30be0-115">A seconda del contesto in cui si verifica una dichiarazione di membro, sono consentite solo determinate accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="30be0-115">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="30be0-116">Se non è specificato nessun modificatore di accesso in una dichiarazione di membro, viene usata un'accessibilità predefinita.</span><span class="sxs-lookup"><span data-stu-id="30be0-116">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="30be0-117">I tipi di primo livello, che non sono annidati in altri tipi, possono avere solo l'accessibilità `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="30be0-117">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="30be0-118">L'accessibilità predefinita per questi tipi è `internal`.</span><span class="sxs-lookup"><span data-stu-id="30be0-118">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="30be0-119">I tipi annidati, che sono membri di altri tipi, possono avere accessibilità dichiarate come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="30be0-119">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="30be0-120">Membri di</span><span class="sxs-lookup"><span data-stu-id="30be0-120">Members of</span></span>|<span data-ttu-id="30be0-121">Accessibilità predefinita del membro</span><span class="sxs-lookup"><span data-stu-id="30be0-121">Default member accessibility</span></span>|<span data-ttu-id="30be0-122">Accessibilità dichiarate e consentite del membro</span><span class="sxs-lookup"><span data-stu-id="30be0-122">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="30be0-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="30be0-123">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="30be0-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="30be0-124">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="30be0-125">L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="30be0-125">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="30be0-126">Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="30be0-126">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="30be0-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="30be0-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30be0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30be0-128">See Also</span></span>  
 [<span data-ttu-id="30be0-129">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="30be0-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="30be0-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="30be0-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="30be0-131">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="30be0-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="30be0-132">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="30be0-132">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="30be0-133">Dominio di accessibilità</span><span class="sxs-lookup"><span data-stu-id="30be0-133">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="30be0-134">Restrizioni relative all'uso dei livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="30be0-134">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="30be0-135">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="30be0-135">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="30be0-136">public</span><span class="sxs-lookup"><span data-stu-id="30be0-136">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="30be0-137">private</span><span class="sxs-lookup"><span data-stu-id="30be0-137">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="30be0-138">protected</span><span class="sxs-lookup"><span data-stu-id="30be0-138">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="30be0-139">internal</span><span class="sxs-lookup"><span data-stu-id="30be0-139">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
