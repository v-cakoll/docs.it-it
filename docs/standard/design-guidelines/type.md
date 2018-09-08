---
title: Linee guida di progettazione dei tipi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7fb9964d0e542c0937c55ae65bd88b3f7149fa8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187939"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="88900-102">Linee guida di progettazione dei tipi</span><span class="sxs-lookup"><span data-stu-id="88900-102">Type Design Guidelines</span></span>
<span data-ttu-id="88900-103">Dalla prospettiva del CLR, sono disponibili solo due categorie di tipi, tipi di riferimento e tipi di valore, ma ai fini di una discussione sulla progettazione di framework, si esegue la divisione tipi in gruppi logici, ciascuno con il proprio regole specifiche di progettazione.</span><span class="sxs-lookup"><span data-stu-id="88900-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="88900-104">Le classi sono nel caso generale dei tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="88900-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="88900-105">Rendono la maggior parte dei tipi nella maggior parte dei Framework.</span><span class="sxs-lookup"><span data-stu-id="88900-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="88900-106">Le classi goduto la grande diffusione per il ricco set di funzionalità orientate a oggetti che supportano e la loro applicabilità generale.</span><span class="sxs-lookup"><span data-stu-id="88900-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="88900-107">Classi di base e le classi astratte sono gruppi logici speciali correlati all'estendibilità.</span><span class="sxs-lookup"><span data-stu-id="88900-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="88900-108">Le interfacce sono tipi che possono essere implementati da entrambi i tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="88900-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="88900-109">Vengono pertanto può essere usato come radici di polimorfiche gerarchie di tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="88900-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="88900-110">Inoltre, le interfacce utilizzabile per simulare l'ereditarietà multipla, che non è supportato da CLR.</span><span class="sxs-lookup"><span data-stu-id="88900-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="88900-111">Gli struct sono nel caso generale dei tipi di valore e devono essere riservati per tipi semplici e di piccoli, simili alle primitive di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="88900-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="88900-112">Enumerazioni rappresentano un caso speciale di tipi di valore utilizzato per definire set short di valori, ad esempio giorni della settimana, colori della console e così via.</span><span class="sxs-lookup"><span data-stu-id="88900-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="88900-113">Le classi statiche sono tipi devono essere contenitori per i membri statici.</span><span class="sxs-lookup"><span data-stu-id="88900-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="88900-114">Vengono comunemente utilizzati per fornire collegamenti ad altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="88900-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="88900-115">I delegati, eccezioni, gli attributi, le matrici e raccolte sono tutti i casi speciali di tipi di riferimento destinati a utilizzi specifici e le linee guida per la progettazione e utilizzo vengono trattate altrove in questo manuale.</span><span class="sxs-lookup"><span data-stu-id="88900-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="88900-116">**✓ DO** assicurarsi che ogni tipo è un set ben definito di membri correlati, non solo un insieme di funzionalità non correlati casuale.</span><span class="sxs-lookup"><span data-stu-id="88900-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88900-117">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="88900-117">In This Section</span></span>  
 [<span data-ttu-id="88900-118">Scelta tra classi e struct</span><span class="sxs-lookup"><span data-stu-id="88900-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="88900-119">Progettazione di classi astratte</span><span class="sxs-lookup"><span data-stu-id="88900-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="88900-120">Progettazione di classi statiche</span><span class="sxs-lookup"><span data-stu-id="88900-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="88900-121">Progettazione di interfacce</span><span class="sxs-lookup"><span data-stu-id="88900-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="88900-122">Progettazione di struct</span><span class="sxs-lookup"><span data-stu-id="88900-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="88900-123">Progettazione di enum</span><span class="sxs-lookup"><span data-stu-id="88900-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="88900-124">Tipi annidati</span><span class="sxs-lookup"><span data-stu-id="88900-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="88900-125">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="88900-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="88900-126">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="88900-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88900-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88900-127">See also</span></span>

- [<span data-ttu-id="88900-128">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="88900-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
