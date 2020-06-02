---
title: Progettazione di classi astratte
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: e6a5923f293ed536fb272f6fe6c805067aede0ab
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280777"
---
# <a name="abstract-class-design"></a><span data-ttu-id="4147a-102">Progettazione di classi astratte</span><span class="sxs-lookup"><span data-stu-id="4147a-102">Abstract Class Design</span></span>

<span data-ttu-id="4147a-103">❌NON definire costruttori interni pubblici o protetti in tipi astratti.</span><span class="sxs-lookup"><span data-stu-id="4147a-103">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="4147a-104">I costruttori devono essere pubblici solo se gli utenti dovranno creare istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="4147a-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="4147a-105">Poiché non è possibile creare istanze di un tipo astratto, un tipo astratto con un costruttore pubblico non è progettato correttamente e fuorviante per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4147a-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="4147a-106">✔️ definire un costruttore protetto o interno in classi astratte.</span><span class="sxs-lookup"><span data-stu-id="4147a-106">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="4147a-107">Un costruttore protetto è più comune e consente semplicemente alla classe di base di eseguire una propria inizializzazione quando vengono creati sottotipi.</span><span class="sxs-lookup"><span data-stu-id="4147a-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="4147a-108">Un costruttore interno può essere usato per limitare le implementazioni concrete della classe astratta all'assembly che definisce la classe.</span><span class="sxs-lookup"><span data-stu-id="4147a-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="4147a-109">✔️ forniscono almeno un tipo concreto che eredita da ogni classe astratta distribuita.</span><span class="sxs-lookup"><span data-stu-id="4147a-109">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="4147a-110">Questa operazione consente di convalidare la progettazione della classe astratta.</span><span class="sxs-lookup"><span data-stu-id="4147a-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="4147a-111">Ad esempio, <xref:System.IO.FileStream?displayProperty=nameWithType> è un'implementazione della <xref:System.IO.Stream?displayProperty=nameWithType> classe astratta.</span><span class="sxs-lookup"><span data-stu-id="4147a-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="4147a-112">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="4147a-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4147a-113">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4147a-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4147a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4147a-114">See also</span></span>

- [<span data-ttu-id="4147a-115">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="4147a-115">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="4147a-116">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="4147a-116">Framework Design Guidelines</span></span>](index.md)
