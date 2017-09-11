---
title: "Livelli di accessibilità (Riferimenti per C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
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
ms.openlocfilehash: 796802a407c486c1df5332d5b4920467f3a1171b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="0a4a2-102">Livelli di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0a4a2-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="0a4a2-103">Usano i modificatori di accesso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) per specificare uno dei livelli seguenti di accessibilità dichiarata per i membri.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="0a4a2-104">Accessibilità dichiarata</span><span class="sxs-lookup"><span data-stu-id="0a4a2-104">Declared accessibility</span></span>|<span data-ttu-id="0a4a2-105">Significato</span><span class="sxs-lookup"><span data-stu-id="0a4a2-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="0a4a2-106">L'accesso non è limitato.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="0a4a2-107">L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="0a4a2-108">L'accesso è limitato all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="0a4a2-109">L'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="0a4a2-110">L'accesso è limitato al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-110">Access is limited to the containing type.</span></span>|  
  
 <span data-ttu-id="0a4a2-111">Per un membro o un tipo è consentito solo un modificatore di accesso, tranne quando si usa la combinazione `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-111">Only one access modifier is allowed for a member or type, except when you use the `protected internal` combination.</span></span>  
  
 <span data-ttu-id="0a4a2-112">I modificatori di accesso non sono consentiti negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-112">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="0a4a2-113">Gli spazi dei nomi non hanno restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-113">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="0a4a2-114">A seconda del contesto in cui si verifica una dichiarazione di membro, sono consentite solo determinate accessibilità dichiarate.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-114">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="0a4a2-115">Se non è specificato nessun modificatore di accesso in una dichiarazione di membro, viene usata un'accessibilità predefinita.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-115">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="0a4a2-116">I tipi di primo livello, che non sono annidati in altri tipi, possono avere solo l'accessibilità `internal` o `public`.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-116">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="0a4a2-117">L'accessibilità predefinita per questi tipi è `internal`.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-117">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="0a4a2-118">I tipi annidati, che sono membri di altri tipi, possono avere accessibilità dichiarate come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-118">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="0a4a2-119">Membri di</span><span class="sxs-lookup"><span data-stu-id="0a4a2-119">Members of</span></span>|<span data-ttu-id="0a4a2-120">Accessibilità predefinita del membro</span><span class="sxs-lookup"><span data-stu-id="0a4a2-120">Default member accessibility</span></span>|<span data-ttu-id="0a4a2-121">Accessibilità dichiarate e consentite del membro</span><span class="sxs-lookup"><span data-stu-id="0a4a2-121">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="0a4a2-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0a4a2-122">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal`|  
|`interface`|`public`|<span data-ttu-id="0a4a2-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0a4a2-123">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="0a4a2-124">L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-124">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="0a4a2-125">Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="0a4a2-125">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0a4a2-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0a4a2-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a4a2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a4a2-127">See Also</span></span>  
 <span data-ttu-id="0a4a2-128">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0a4a2-129">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0a4a2-130">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0a4a2-131">[Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-131">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="0a4a2-132">[Dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-132">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md) </span></span>  
 <span data-ttu-id="0a4a2-133">[Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-133">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="0a4a2-134">[Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-134">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="0a4a2-135">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-135">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="0a4a2-136">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-136">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="0a4a2-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="0a4a2-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="0a4a2-138">internal</span><span class="sxs-lookup"><span data-stu-id="0a4a2-138">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

