---
title: Linee guida per la progettazione di Framework
description: Vedere linee guida di progettazione di Framework per la progettazione di librerie che estendono e interagiscono con .NET, per garantire la coerenza e la semplicità d'uso dell'API.
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 17998adb1d18579f6763a80a82944e742e284e4e
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769067"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="50c2c-103">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="50c2c-103">Framework Design Guidelines</span></span>
<span data-ttu-id="50c2c-104">In questa sezione vengono fornite le linee guida per la progettazione di librerie che estendono e interagiscono con il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50c2c-104">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="50c2c-105">L'obiettivo è aiutare i progettisti di librerie a garantire la coerenza e la semplicità di utilizzo dell'API offrendo un modello di programmazione unificato indipendente dal linguaggio di programmazione utilizzato per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="50c2c-105">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="50c2c-106">Si consiglia di seguire queste linee guida di progettazione per lo sviluppo di classi e componenti che estendono le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50c2c-106">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="50c2c-107">Un progetto di libreria incoerente influisce negativamente sulla produttività degli sviluppatori e sconsiglia l'adozione.</span><span class="sxs-lookup"><span data-stu-id="50c2c-107">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="50c2c-108">Le linee guida sono organizzate come semplici raccomandazioni precedute dai termini `Do` ,, `Consider` `Avoid` e `Do not` .</span><span class="sxs-lookup"><span data-stu-id="50c2c-108">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="50c2c-109">Queste linee guida sono progettate per aiutare i progettisti di librerie di classi a comprendere i compromessi tra diverse soluzioni.</span><span class="sxs-lookup"><span data-stu-id="50c2c-109">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="50c2c-110">Potrebbero essere presenti situazioni in cui la progettazione di una libreria corretta richiede la violazione di queste linee guida di progettazione.</span><span class="sxs-lookup"><span data-stu-id="50c2c-110">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="50c2c-111">Questi casi dovrebbero essere rari ed è importante avere un motivo chiaro e interessante per la decisione.</span><span class="sxs-lookup"><span data-stu-id="50c2c-111">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="50c2c-112">Queste linee guida sono tratte dalle *linee guida per la progettazione di Book Framework: convenzioni, idiomi e modelli per le librerie .NET riutilizzabili, 2a edizione*, di Krzysztof Cwalina e Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="50c2c-112">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50c2c-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="50c2c-113">In This Section</span></span>  
 [<span data-ttu-id="50c2c-114">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="50c2c-114">Naming Guidelines</span></span>](naming-guidelines.md)  
 <span data-ttu-id="50c2c-115">Vengono fornite linee guida per la denominazione di assembly, spazi dei nomi, tipi e membri nelle librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="50c2c-115">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="50c2c-116">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="50c2c-116">Type Design Guidelines</span></span>](type.md)  
 <span data-ttu-id="50c2c-117">Vengono fornite linee guida per l'utilizzo di classi, interfacce, enumerazioni, strutture e altri tipi statici e astratti.</span><span class="sxs-lookup"><span data-stu-id="50c2c-117">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="50c2c-118">Linee guida per la progettazione di membri</span><span class="sxs-lookup"><span data-stu-id="50c2c-118">Member Design Guidelines</span></span>](member.md)  
 <span data-ttu-id="50c2c-119">Vengono fornite linee guida per la progettazione e l'utilizzo di proprietà, metodi, costruttori, campi, eventi, operatori e parametri.</span><span class="sxs-lookup"><span data-stu-id="50c2c-119">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="50c2c-120">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="50c2c-120">Designing for Extensibility</span></span>](designing-for-extensibility.md)  
 <span data-ttu-id="50c2c-121">Vengono illustrati i meccanismi di estendibilità, ad esempio la sottoclasse, l'utilizzo di eventi, membri virtuali e callback e viene illustrato come scegliere i meccanismi che meglio soddisfano i requisiti del Framework.</span><span class="sxs-lookup"><span data-stu-id="50c2c-121">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="50c2c-122">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="50c2c-122">Design Guidelines for Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="50c2c-123">Descrive le linee guida di progettazione per la progettazione, la generazione e il rilevamento di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="50c2c-123">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="50c2c-124">Linee guida sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="50c2c-124">Usage Guidelines</span></span>](usage-guidelines.md)  
 <span data-ttu-id="50c2c-125">Vengono descritte le linee guida per l'utilizzo di tipi comuni come matrici, attributi e raccolte, il supporto della serializzazione e l'overload degli operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="50c2c-125">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="50c2c-126">Modelli di progettazione comuni</span><span class="sxs-lookup"><span data-stu-id="50c2c-126">Common Design Patterns</span></span>](common-design-patterns.md)  
 <span data-ttu-id="50c2c-127">Vengono fornite linee guida per la scelta e l'implementazione delle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="50c2c-127">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="50c2c-128">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="50c2c-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="50c2c-129">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="50c2c-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c2c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50c2c-130">See also</span></span>

- [<span data-ttu-id="50c2c-131">Overview</span><span class="sxs-lookup"><span data-stu-id="50c2c-131">Overview</span></span>](../../framework/get-started/overview.md)
- [<span data-ttu-id="50c2c-132">Guida allo sviluppo</span><span class="sxs-lookup"><span data-stu-id="50c2c-132">Development Guide</span></span>](../../framework/development-guide.md)
