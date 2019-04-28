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
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785554"
---
# <a name="abstract-class-design"></a><span data-ttu-id="f338b-102">Progettazione di classi astratte</span><span class="sxs-lookup"><span data-stu-id="f338b-102">Abstract Class Design</span></span>
<span data-ttu-id="f338b-103">**X DO NOT** definire costruttori interni pubblici o protetti in tipi astratti.</span><span class="sxs-lookup"><span data-stu-id="f338b-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="f338b-104">I costruttori devono essere pubblici solo se gli utenti dovranno creare istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="f338b-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="f338b-105">Poiché non è possibile creare istanze di un tipo astratto, un tipo astratto con un costruttore pubblico è correttamente progettato e fuorviante per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f338b-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="f338b-106">**✓ DO** definiscono un protetto o un costruttore interno per le classi astratte.</span><span class="sxs-lookup"><span data-stu-id="f338b-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="f338b-107">Un costruttore protetto è più comune e consente semplicemente la classe di base eseguire la propria inizializzazione quando vengono creati i sottotipi.</span><span class="sxs-lookup"><span data-stu-id="f338b-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="f338b-108">Un costruttore interno è utilizzabile per limitare le implementazioni concrete della classe astratta per l'assembly che definisce la classe.</span><span class="sxs-lookup"><span data-stu-id="f338b-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="f338b-109">**✓ DO** fornire almeno un tipo concreto che eredita da ogni classe astratta che si effettua la spedizione.</span><span class="sxs-lookup"><span data-stu-id="f338b-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="f338b-110">Operazioni di questo monitoraggio consente di convalidare la struttura della classe astratta.</span><span class="sxs-lookup"><span data-stu-id="f338b-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="f338b-111">Ad esempio, <xref:System.IO.FileStream?displayProperty=nameWithType> è un'implementazione del <xref:System.IO.Stream?displayProperty=nameWithType> classe astratta.</span><span class="sxs-lookup"><span data-stu-id="f338b-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="f338b-112">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="f338b-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f338b-113">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f338b-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f338b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f338b-114">See also</span></span>

- [<span data-ttu-id="f338b-115">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="f338b-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="f338b-116">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="f338b-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
