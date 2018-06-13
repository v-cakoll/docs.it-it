---
title: Progettazione di classi astratte
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28052cc6848d77acbdf8e9381146ca6fb06c15d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570564"
---
# <a name="abstract-class-design"></a><span data-ttu-id="6309c-102">Progettazione di classi astratte</span><span class="sxs-lookup"><span data-stu-id="6309c-102">Abstract Class Design</span></span>
<span data-ttu-id="6309c-103">**X non** definire costruttori interni pubblici o protetti in tipi astratti.</span><span class="sxs-lookup"><span data-stu-id="6309c-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="6309c-104">I costruttori devono essere pubblici solo se gli utenti dovranno creare istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="6309c-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="6309c-105">Poiché è possibile creare istanze di un tipo astratto, un tipo astratto con costruttore pubblico in modo non corretto è progettato e fuorviante per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6309c-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="6309c-106">**✓ SI** definiscono un protetto o un costruttore interno per le classi astratte.</span><span class="sxs-lookup"><span data-stu-id="6309c-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="6309c-107">Un costruttore protetto è più comune e consente semplicemente la classe di base eseguire il proprio inizializzazione quando vengono creati i sottotipi.</span><span class="sxs-lookup"><span data-stu-id="6309c-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="6309c-108">Un costruttore interno può essere utilizzato per limitare le implementazioni concrete della classe astratta per l'assembly che definisce la classe.</span><span class="sxs-lookup"><span data-stu-id="6309c-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="6309c-109">**✓ SI** fornire almeno un tipo concreto che eredita da ogni classe astratta che si effettua la spedizione.</span><span class="sxs-lookup"><span data-stu-id="6309c-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="6309c-110">Effettuando questa consente di convalidare la struttura della classe astratta.</span><span class="sxs-lookup"><span data-stu-id="6309c-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="6309c-111">Ad esempio, <xref:System.IO.FileStream?displayProperty=nameWithType> è un'implementazione del <xref:System.IO.Stream?displayProperty=nameWithType> classe astratta.</span><span class="sxs-lookup"><span data-stu-id="6309c-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="6309c-112">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="6309c-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6309c-113">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6309c-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6309c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6309c-114">See Also</span></span>  
 [<span data-ttu-id="6309c-115">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="6309c-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="6309c-116">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="6309c-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
