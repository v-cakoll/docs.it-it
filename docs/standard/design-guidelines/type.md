---
title: Linee guida di progettazione dei tipi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: 17bd300277a039818a3d563c8f2d5f99eb2fc68d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289564"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="cb0ec-102">Linee guida di progettazione dei tipi</span><span class="sxs-lookup"><span data-stu-id="cb0ec-102">Type Design Guidelines</span></span>
<span data-ttu-id="cb0ec-103">Dal punto di vista di CLR, sono disponibili solo due categorie di tipi, ovvero tipi di riferimento e tipi di valore, ma ai fini di una discussione sulla progettazione del Framework, i tipi vengono suddivisi in più gruppi logici, ognuno con regole di progettazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>

 <span data-ttu-id="cb0ec-104">Le classi sono il caso generale dei tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="cb0ec-105">Costituiscono la maggior parte dei tipi nella maggior parte dei Framework.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="cb0ec-106">Le classi devono avere la popolarità per il set completo di funzionalità orientate a oggetti che supportano e per la loro applicabilità generale.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="cb0ec-107">Le classi base e le classi astratte sono gruppi logici speciali correlati all'estendibilità.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>

 <span data-ttu-id="cb0ec-108">Le interfacce sono tipi che possono essere implementati sia da tipi di riferimento che da tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="cb0ec-109">Possono quindi fungere da radici di gerarchie polimorfiche di tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="cb0ec-110">Inoltre, è possibile utilizzare le interfacce per simulare l'ereditarietà multipla, che non è supportata in modo nativo da CLR.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>

 <span data-ttu-id="cb0ec-111">Gli struct sono il caso generale dei tipi di valore e devono essere riservati per tipi semplici e piccoli, simili alle primitive di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>

 <span data-ttu-id="cb0ec-112">Le enumerazioni sono un caso speciale di tipi valore usati per definire brevi set di valori, ad esempio giorni della settimana, colori della console e così via.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>

 <span data-ttu-id="cb0ec-113">Le classi statiche sono tipi destinati a essere contenitori per i membri statici.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="cb0ec-114">Sono comunemente usati per fornire collegamenti ad altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-114">They are commonly used to provide shortcuts to other operations.</span></span>

 <span data-ttu-id="cb0ec-115">I delegati, le eccezioni, gli attributi, le matrici e le raccolte sono casi speciali di tipi di riferimento destinati a utilizzi specifici, mentre le linee guida per la progettazione e l'utilizzo sono illustrate altrove in questo libro.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>

 <span data-ttu-id="cb0ec-116">✔️ Assicurarsi che ogni tipo sia un set ben definito di membri correlati, non solo una raccolta casuale di funzionalità non correlate.</span><span class="sxs-lookup"><span data-stu-id="cb0ec-116">✔️ DO ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cb0ec-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cb0ec-117">In This Section</span></span>
 <span data-ttu-id="cb0ec-118">[Scelta tra classi e struct](choosing-between-class-and-struct.md) [classe astratta progettazione](abstract-class.md) di classi [statiche](static-class.md) progettazione dell' [interfaccia](interface.md) [struttura struttura](struct.md) progettazione dell'enumerazione progettazione dell' [enumerazione](enum.md) [tipi annidati](nested-types.md) *parti © 2005, 2009 Microsoft Corporation. Tutti i diritti sono riservati.*</span><span class="sxs-lookup"><span data-stu-id="cb0ec-118">[Choosing Between Class and Struct](choosing-between-class-and-struct.md) [Abstract Class Design](abstract-class.md) [Static Class Design](static-class.md) [Interface Design](interface.md) [Struct Design](struct.md) [Enum Design](enum.md) [Nested Types](nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="cb0ec-119">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="cb0ec-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="cb0ec-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb0ec-120">See also</span></span>

- [<span data-ttu-id="cb0ec-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="cb0ec-121">Framework Design Guidelines</span></span>](index.md)
