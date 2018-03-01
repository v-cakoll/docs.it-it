---
title: "Livelli di accessibilità (Riferimenti per C#)"
ms.date: 12/06/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fed7d6d0eb3eda4d8d2e1847259dd8d23700d3e7
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="939a9-102">Livelli di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="939a9-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="939a9-103">Usare i modificatori di accesso `public`, `protected`, `internal` o `private` per specificare uno dei livelli seguenti di accessibilità dichiarata per i membri.</span><span class="sxs-lookup"><span data-stu-id="939a9-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="939a9-104">Accessibilità dichiarata</span><span class="sxs-lookup"><span data-stu-id="939a9-104">Declared accessibility</span></span>|<span data-ttu-id="939a9-105">Significato</span><span class="sxs-lookup"><span data-stu-id="939a9-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="939a9-106">L'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="939a9-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="939a9-107">L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="939a9-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="939a9-108">L'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="939a9-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="939a9-109">L'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="939a9-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="939a9-110">L'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="939a9-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="939a9-111">L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene all'interno dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="939a9-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="939a9-112">Disponibile da C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="939a9-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="939a9-113">Per un membro o un tipo è consentito solo un modificatore di accesso, tranne quando si usano le combinazioni `protected internal` o `private protected`.</span><span class="sxs-lookup"><span data-stu-id="939a9-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="939a9-114">I modificatori di accesso non sono consentiti negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="939a9-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="939a9-115">Gli spazi dei nomi non hanno restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="939a9-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="939a9-116">A seconda del contesto in cui si verifica una dichiarazione di membro, sono consentite solo determinate accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="939a9-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="939a9-117">Se non è specificato nessun modificatore di accesso in una dichiarazione di membro, viene usata un'accessibilità predefinita.</span><span class="sxs-lookup"><span data-stu-id="939a9-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="939a9-118">I tipi di primo livello, che non sono annidati in altri tipi, possono avere solo l'accessibilità `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="939a9-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="939a9-119">L'accessibilità predefinita per questi tipi è `internal`.</span><span class="sxs-lookup"><span data-stu-id="939a9-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="939a9-120">I tipi annidati, che sono membri di altri tipi, possono avere accessibilità dichiarate come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="939a9-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="939a9-121">Membri di</span><span class="sxs-lookup"><span data-stu-id="939a9-121">Members of</span></span>|<span data-ttu-id="939a9-122">Accessibilità predefinita del membro</span><span class="sxs-lookup"><span data-stu-id="939a9-122">Default member accessibility</span></span>|<span data-ttu-id="939a9-123">Accessibilità dichiarate e consentite del membro</span><span class="sxs-lookup"><span data-stu-id="939a9-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="939a9-124">nessuno</span><span class="sxs-lookup"><span data-stu-id="939a9-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="939a9-125">nessuno</span><span class="sxs-lookup"><span data-stu-id="939a9-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="939a9-126">L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="939a9-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="939a9-127">Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="939a9-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="939a9-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="939a9-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="939a9-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="939a9-129">See Also</span></span>  
 [<span data-ttu-id="939a9-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="939a9-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="939a9-131">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="939a9-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="939a9-132">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="939a9-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="939a9-133">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="939a9-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="939a9-134">Dominio di accessibilità</span><span class="sxs-lookup"><span data-stu-id="939a9-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="939a9-135">Restrizioni relative all'uso dei livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="939a9-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="939a9-136">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="939a9-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="939a9-137">public</span><span class="sxs-lookup"><span data-stu-id="939a9-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="939a9-138">private</span><span class="sxs-lookup"><span data-stu-id="939a9-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="939a9-139">protected</span><span class="sxs-lookup"><span data-stu-id="939a9-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="939a9-140">internal</span><span class="sxs-lookup"><span data-stu-id="939a9-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
