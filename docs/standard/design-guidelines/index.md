---
title: Linee guida per la progettazione di Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2674acf14aae5e892dfb9707a19cca12b4797c90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572983"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="c1ce5-102">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="c1ce5-102">Framework Design Guidelines</span></span>
<span data-ttu-id="c1ce5-103">In questa sezione vengono fornite linee guida per la progettazione di librerie che estendono e interagiscono con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="c1ce5-104">L'obiettivo è garantire agli sviluppatori di librerie coerenza API e la facilità di utilizzo fornendo un modello di programmazione unificato che sia indipendente dal linguaggio di programmazione utilizzato per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="c1ce5-105">È consigliabile seguire queste linee guida di progettazione durante lo sviluppo di classi e componenti che estendono .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="c1ce5-106">Progettazione di librerie incoerente può influire negativamente sulla produttività degli sviluppatori e sconsiglia adozione.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="c1ce5-107">Le linee guida sono organizzate come indicazioni semplice con le condizioni di prefisso `Do`, `Consider`, `Avoid`, e `Do not`.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="c1ce5-108">Queste linee guida servono per consentire agli sviluppatori di librerie di classe di comprendere i compromessi tra diverse soluzioni.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="c1ce5-109">Potrebbero esistere situazioni in cui è necessario che violi queste linee guida di progettazione corretta progettazione delle librerie.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="c1ce5-110">Casi devono essere rari ed è importante disporre di un motivo esistano valide per la decisione.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="c1ce5-111">Queste linee guida sono state estratte dal libro *linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition*, Krzysztof Cwalina e Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1ce5-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c1ce5-112">In This Section</span></span>  
 [<span data-ttu-id="c1ce5-113">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c1ce5-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="c1ce5-114">Vengono fornite linee guida per la denominazione di assembly, spazi dei nomi, tipi e membri nelle librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="c1ce5-115">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="c1ce5-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="c1ce5-116">Vengono fornite linee guida per l'utilizzo di classi statiche e astratte, interfacce, enumerazioni, strutture e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="c1ce5-117">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="c1ce5-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="c1ce5-118">Vengono fornite linee guida per la progettazione e utilizzando le proprietà, metodi, costruttori, campi, eventi, operatori e i parametri.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="c1ce5-119">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="c1ce5-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="c1ce5-120">Vengono illustrati i meccanismi di estendibilità, ad esempio la creazione di sottoclassi, utilizzando gli eventi, i membri virtuali e i callback e viene spiegato come scegliere i meccanismi che meglio soddisfano i requisiti del framework.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="c1ce5-121">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c1ce5-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="c1ce5-122">Descrive linee guida di progettazione per la progettazione, generazione e l'intercettazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="c1ce5-123">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="c1ce5-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="c1ce5-124">Vengono fornite istruzioni per l'utilizzo di tipi comuni, ad esempio matrici, attributi e raccolte che supportano la serializzazione e l'overload degli operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="c1ce5-125">Modelli di progettazione comuni</span><span class="sxs-lookup"><span data-stu-id="c1ce5-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="c1ce5-126">Vengono fornite linee guida per la scelta e l'implementazione delle proprietà di dipendenza e il modello dispose.</span><span class="sxs-lookup"><span data-stu-id="c1ce5-126">Provides guidelines for choosing and implementing dependency properties and the dispose pattern.</span></span>  
  
 <span data-ttu-id="c1ce5-127">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="c1ce5-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c1ce5-128">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c1ce5-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ce5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1ce5-129">See Also</span></span>  
 [<span data-ttu-id="c1ce5-130">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c1ce5-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="c1ce5-131">Guida di orientamento per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c1ce5-131">Roadmap for the .NET Framework</span></span>](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [<span data-ttu-id="c1ce5-132">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="c1ce5-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
