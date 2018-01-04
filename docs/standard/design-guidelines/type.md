---
title: Linee guida di progettazione dei tipi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6b02abef0180b6de82e26837863849cce35c994f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="type-design-guidelines"></a><span data-ttu-id="87d10-102">Linee guida di progettazione dei tipi</span><span class="sxs-lookup"><span data-stu-id="87d10-102">Type Design Guidelines</span></span>
<span data-ttu-id="87d10-103">Dal punto di vista di Common Language Runtime, sono disponibili solo due categorie di tipi, tipi di riferimento e tipi di valore, ma ai fini della discussione sulla progettazione di framework, i tipi di verrà diviso in gruppi logici, ognuno con il proprio regole specifiche di progettazione.</span><span class="sxs-lookup"><span data-stu-id="87d10-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="87d10-104">Le classi sono nel caso generale dei tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="87d10-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="87d10-105">Che costituiscono la maggior parte dei tipi nella maggior parte dei Framework.</span><span class="sxs-lookup"><span data-stu-id="87d10-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="87d10-106">Classi goduto la grande diffusione per il ricco set di funzionalità orientate a oggetti che supportano e applicabilità generale.</span><span class="sxs-lookup"><span data-stu-id="87d10-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="87d10-107">Classi di base e classi astratte sono gruppi logici speciali correlati all'estendibilità.</span><span class="sxs-lookup"><span data-stu-id="87d10-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="87d10-108">Le interfacce sono tipi che possono essere implementati da entrambi i tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="87d10-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="87d10-109">In questo modo possono risultare radici di polimorfiche gerarchie di tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="87d10-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="87d10-110">Inoltre, le interfacce consente di simulare l'ereditarietà multipla, in modo nativo non è supportato da CLR.</span><span class="sxs-lookup"><span data-stu-id="87d10-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="87d10-111">Gli struct sono nel caso generale dei tipi di valore e devono essere riservati per tipi semplici e di piccoli, simili a primitive di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87d10-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="87d10-112">Le enumerazioni sono un tipo speciale di tipi di valore utilizzato per definire una breve serie di valori, ad esempio giorni della settimana, colori della console e così via.</span><span class="sxs-lookup"><span data-stu-id="87d10-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="87d10-113">Le classi statiche sono tipi deve essere contenitori per i membri statici.</span><span class="sxs-lookup"><span data-stu-id="87d10-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="87d10-114">In genere utilizzati per fornire collegamenti ad altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="87d10-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="87d10-115">Delegati, eccezioni, gli attributi, matrici e raccolte sono tutti i casi speciali dei tipi di riferimento destinati a utilizzi specifici e linee guida per la progettazione e utilizzo vengono trattate altrove in questo manuale.</span><span class="sxs-lookup"><span data-stu-id="87d10-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="87d10-116">**✓ SI** assicurarsi che ogni tipo è un set ben definito di membri correlati, non solo un insieme casuale delle funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="87d10-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87d10-117">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="87d10-117">In This Section</span></span>  
 [<span data-ttu-id="87d10-118">Scelta tra classi e struct</span><span class="sxs-lookup"><span data-stu-id="87d10-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="87d10-119">Progettazione di classi astratte</span><span class="sxs-lookup"><span data-stu-id="87d10-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="87d10-120">Progettazione di classi statiche</span><span class="sxs-lookup"><span data-stu-id="87d10-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="87d10-121">Progettazione di interfacce</span><span class="sxs-lookup"><span data-stu-id="87d10-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="87d10-122">Progettazione di struct</span><span class="sxs-lookup"><span data-stu-id="87d10-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="87d10-123">Progettazione di enum</span><span class="sxs-lookup"><span data-stu-id="87d10-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="87d10-124">Tipi annidati</span><span class="sxs-lookup"><span data-stu-id="87d10-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="87d10-125">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="87d10-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="87d10-126">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="87d10-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d10-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87d10-127">See Also</span></span>  
 [<span data-ttu-id="87d10-128">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="87d10-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
