---
title: Astrazioni (interfacce e tipi astratti)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 276c5883487d8fba47d7fb80060d4c947e0f6cd6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="09ce2-102">Astrazioni (interfacce e tipi astratti)</span><span class="sxs-lookup"><span data-stu-id="09ce2-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="09ce2-103">Un'astrazione è un tipo che descrive un contratto, ma non fornisce un'implementazione completa del contratto.</span><span class="sxs-lookup"><span data-stu-id="09ce2-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="09ce2-104">Astrazioni sono in genere implementate come classi astratte o interfacce, e hanno un set ben definito della documentazione di riferimento che descrive la semantica dei tipi che implementa il contratto richiesta.</span><span class="sxs-lookup"><span data-stu-id="09ce2-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="09ce2-105">Le astrazioni più importanti in .NET Framework includono <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, e <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="09ce2-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="09ce2-106">È possibile estendere Framework implementando un tipo concreto che supporta il contratto di astrazione e utilizzo di questo tipo concreto con framework API consumer (eseguito) l'astrazione.</span><span class="sxs-lookup"><span data-stu-id="09ce2-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="09ce2-107">Un'astrazione utile e significativa che è in grado di resistere il test di tempo è molto difficile da progettare.</span><span class="sxs-lookup"><span data-stu-id="09ce2-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="09ce2-108">La difficoltà principale sta per diventare il set corretto di membri, non sono più presenti e non un numero inferiore.</span><span class="sxs-lookup"><span data-stu-id="09ce2-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="09ce2-109">Se un'astrazione ha troppi membri, diventa difficili o impossibili da implementare.</span><span class="sxs-lookup"><span data-stu-id="09ce2-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="09ce2-110">Se dispone di membri insufficienti per la funzionalità promesso, diventa inutilizzabile in molti scenari interessanti.</span><span class="sxs-lookup"><span data-stu-id="09ce2-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="09ce2-111">Troppi astrazioni in un framework anche influire negativamente sull'usabilità del framework.</span><span class="sxs-lookup"><span data-stu-id="09ce2-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="09ce2-112">È spesso molto difficile da comprendere un'astrazione senza conoscere come si inserisca nell'immagine più grande di API che viene applicato l'astrazione e le implementazioni concrete.</span><span class="sxs-lookup"><span data-stu-id="09ce2-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="09ce2-113">Inoltre, i nomi di astrazioni e i relativi membri sono necessariamente astratti che spesso rende difficile e inaccessibile senza prima conoscere il contesto più ampio del loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="09ce2-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="09ce2-114">Tuttavia, astrazioni forniscono estensibilità estremamente efficaci che spesso non possono corrispondere a altri meccanismi di estensibilità.</span><span class="sxs-lookup"><span data-stu-id="09ce2-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="09ce2-115">Sono alla base di molti modelli di architettura, ad esempio plug-in, inversione di controllo (IoC), le pipeline e così via.</span><span class="sxs-lookup"><span data-stu-id="09ce2-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="09ce2-116">Sono inoltre estremamente importante per la testabilità del Framework.</span><span class="sxs-lookup"><span data-stu-id="09ce2-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="09ce2-117">Buona astrazioni rendono possibile sottoporre a stub pesante dipendenze allo scopo di unit test.</span><span class="sxs-lookup"><span data-stu-id="09ce2-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="09ce2-118">In breve, le astrazioni sono responsabili per la ricchezza dei framework orientata agli oggetti moderno ricercata.</span><span class="sxs-lookup"><span data-stu-id="09ce2-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="09ce2-119">**X non** forniscono astrazioni a meno che non vengono verificati per lo sviluppo di diverse implementazioni concrete e utilizzano le astrazioni di API.</span><span class="sxs-lookup"><span data-stu-id="09ce2-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="09ce2-120">**✓ SI** quando si progetta un'astrazione scegliere con attenzione tra una classe astratta e un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="09ce2-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="09ce2-121">**Provare a ✓** fornire test di riferimento per le implementazioni concrete di astrazioni.</span><span class="sxs-lookup"><span data-stu-id="09ce2-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="09ce2-122">Tali test dovrebbero consentire agli utenti di verificare la corretta implementazione del contratto.</span><span class="sxs-lookup"><span data-stu-id="09ce2-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="09ce2-123">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="09ce2-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="09ce2-124">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="09ce2-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ce2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09ce2-125">See Also</span></span>  
 [<span data-ttu-id="09ce2-126">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="09ce2-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="09ce2-127">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="09ce2-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
