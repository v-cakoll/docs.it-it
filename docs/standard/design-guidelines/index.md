---
title: Linee guida per la progettazione di Framework
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 623391de63891c1695a63482a424bb76a861deba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709309"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="8352e-102">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="8352e-102">Framework Design Guidelines</span></span>
<span data-ttu-id="8352e-103">In questa sezione vengono fornite le linee guida per la progettazione di librerie che estendono e interagiscono con il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8352e-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="8352e-104">L'obiettivo è aiutare i progettisti di librerie a garantire la coerenza e la semplicità di utilizzo dell'API offrendo un modello di programmazione unificato indipendente dal linguaggio di programmazione utilizzato per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8352e-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="8352e-105">Si consiglia di seguire queste linee guida di progettazione per lo sviluppo di classi e componenti che estendono le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8352e-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="8352e-106">Un progetto di libreria incoerente influisce negativamente sulla produttività degli sviluppatori e sconsiglia l'adozione.</span><span class="sxs-lookup"><span data-stu-id="8352e-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="8352e-107">Le linee guida sono organizzate come semplici raccomandazioni precedute dai termini `Do`, `Consider`, `Avoid`e `Do not`.</span><span class="sxs-lookup"><span data-stu-id="8352e-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="8352e-108">Queste linee guida sono progettate per aiutare i progettisti di librerie di classi a comprendere i compromessi tra diverse soluzioni.</span><span class="sxs-lookup"><span data-stu-id="8352e-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="8352e-109">Potrebbero essere presenti situazioni in cui la progettazione di una libreria corretta richiede la violazione di queste linee guida di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8352e-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="8352e-110">Questi casi dovrebbero essere rari ed è importante avere un motivo chiaro e interessante per la decisione.</span><span class="sxs-lookup"><span data-stu-id="8352e-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="8352e-111">Queste linee guida sono tratte dalle *linee guida per la progettazione di Book Framework: convenzioni, idiomi e modelli per le librerie .NET riutilizzabili, 2a edizione*, di Krzysztof Cwalina e Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="8352e-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8352e-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8352e-112">In This Section</span></span>  
 [<span data-ttu-id="8352e-113">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="8352e-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="8352e-114">Vengono fornite linee guida per la denominazione di assembly, spazi dei nomi, tipi e membri nelle librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="8352e-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="8352e-115">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="8352e-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="8352e-116">Vengono fornite linee guida per l'utilizzo di classi, interfacce, enumerazioni, strutture e altri tipi statici e astratti.</span><span class="sxs-lookup"><span data-stu-id="8352e-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="8352e-117">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="8352e-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="8352e-118">Vengono fornite linee guida per la progettazione e l'utilizzo di proprietà, metodi, costruttori, campi, eventi, operatori e parametri.</span><span class="sxs-lookup"><span data-stu-id="8352e-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="8352e-119">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="8352e-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="8352e-120">Vengono illustrati i meccanismi di estendibilità, ad esempio la sottoclasse, l'utilizzo di eventi, membri virtuali e callback e viene illustrato come scegliere i meccanismi che meglio soddisfano i requisiti del Framework.</span><span class="sxs-lookup"><span data-stu-id="8352e-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="8352e-121">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="8352e-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="8352e-122">Descrive le linee guida di progettazione per la progettazione, la generazione e il rilevamento di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="8352e-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="8352e-123">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="8352e-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="8352e-124">Vengono descritte le linee guida per l'utilizzo di tipi comuni come matrici, attributi e raccolte, il supporto della serializzazione e l'overload degli operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="8352e-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="8352e-125">Modelli di progettazione comuni</span><span class="sxs-lookup"><span data-stu-id="8352e-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="8352e-126">Vengono fornite linee guida per la scelta e l'implementazione delle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="8352e-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="8352e-127">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="8352e-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8352e-128">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8352e-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8352e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8352e-129">See also</span></span>

- [<span data-ttu-id="8352e-130">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8352e-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="8352e-131">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="8352e-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
