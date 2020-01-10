---
title: Livelli di accessibilità - Riferimenti per C#
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713821"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="66c8b-102">Livelli di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="66c8b-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="66c8b-103">Usare i modificatori di accesso `public`, `protected`, `internal` o `private` per specificare uno dei livelli seguenti di accessibilità dichiarata per i membri.</span><span class="sxs-lookup"><span data-stu-id="66c8b-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="66c8b-104">Accessibilità dichiarata</span><span class="sxs-lookup"><span data-stu-id="66c8b-104">Declared accessibility</span></span>|<span data-ttu-id="66c8b-105">Significato</span><span class="sxs-lookup"><span data-stu-id="66c8b-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="66c8b-106">L'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="66c8b-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="66c8b-107">L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="66c8b-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="66c8b-108">L'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="66c8b-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="66c8b-109">L'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="66c8b-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="66c8b-110">L'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="66c8b-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="66c8b-111">L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene all'interno dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="66c8b-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="66c8b-112">Disponibile da C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="66c8b-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="66c8b-113">Per un membro o un tipo è consentito solo un modificatore di accesso, tranne quando si usano le combinazioni `protected internal` o `private protected`.</span><span class="sxs-lookup"><span data-stu-id="66c8b-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="66c8b-114">I modificatori di accesso non sono consentiti negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="66c8b-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="66c8b-115">Gli spazi dei nomi non hanno restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="66c8b-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="66c8b-116">A seconda del contesto in cui si verifica una dichiarazione di membro, sono consentite solo determinate accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="66c8b-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="66c8b-117">Se non è specificato nessun modificatore di accesso in una dichiarazione di membro, viene usata un'accessibilità predefinita.</span><span class="sxs-lookup"><span data-stu-id="66c8b-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="66c8b-118">I tipi di primo livello, che non sono annidati in altri tipi, possono avere solo l'accessibilità `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="66c8b-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="66c8b-119">L'accessibilità predefinita per questi tipi è `internal`.</span><span class="sxs-lookup"><span data-stu-id="66c8b-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="66c8b-120">I tipi annidati, che sono membri di altri tipi, possono avere accessibilità dichiarate come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="66c8b-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="66c8b-121">Membri di</span><span class="sxs-lookup"><span data-stu-id="66c8b-121">Members of</span></span>|<span data-ttu-id="66c8b-122">Accessibilità predefinita del membro</span><span class="sxs-lookup"><span data-stu-id="66c8b-122">Default member accessibility</span></span>|<span data-ttu-id="66c8b-123">Accessibilità dichiarate e consentite del membro</span><span class="sxs-lookup"><span data-stu-id="66c8b-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="66c8b-124">nessuna</span><span class="sxs-lookup"><span data-stu-id="66c8b-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="66c8b-125">nessuna</span><span class="sxs-lookup"><span data-stu-id="66c8b-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="66c8b-126">L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](./accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="66c8b-126">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="66c8b-127">Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="66c8b-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="66c8b-128">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="66c8b-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66c8b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66c8b-129">See also</span></span>

- [<span data-ttu-id="66c8b-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="66c8b-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="66c8b-131">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="66c8b-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="66c8b-132">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="66c8b-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="66c8b-133">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="66c8b-133">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="66c8b-134">Dominio di accessibilità</span><span class="sxs-lookup"><span data-stu-id="66c8b-134">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="66c8b-135">Restrizioni relative all'uso dei livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="66c8b-135">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="66c8b-136">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="66c8b-136">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="66c8b-137">public</span><span class="sxs-lookup"><span data-stu-id="66c8b-137">public</span></span>](./public.md)
- [<span data-ttu-id="66c8b-138">private</span><span class="sxs-lookup"><span data-stu-id="66c8b-138">private</span></span>](./private.md)
- [<span data-ttu-id="66c8b-139">protected</span><span class="sxs-lookup"><span data-stu-id="66c8b-139">protected</span></span>](./protected.md)
- [<span data-ttu-id="66c8b-140">internal</span><span class="sxs-lookup"><span data-stu-id="66c8b-140">internal</span></span>](./internal.md)
