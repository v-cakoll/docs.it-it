---
title: "Progettazione finalizzata all'estensibilità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f21e9239199ecd36432ed8f14adb896f1799506b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="70908-102">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="70908-102">Designing for Extensibility</span></span>
<span data-ttu-id="70908-103">Un aspetto importante della progettazione di un framework consiste nel garantire che l'estendibilità del framework è stato considerato con attenzione.</span><span class="sxs-lookup"><span data-stu-id="70908-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="70908-104">È necessario comprendere i costi e i vantaggi associati a vari meccanismi di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="70908-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="70908-105">Questo capitolo consente di decidere quale dei meccanismi di estendibilità: creazione di una sottoclasse, eventi, i membri virtuali, i callback e così via, possano soddisfare i requisiti del framework di.</span><span class="sxs-lookup"><span data-stu-id="70908-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="70908-106">Esistono diversi modi per consentire l'estensibilità in Framework.</span><span class="sxs-lookup"><span data-stu-id="70908-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="70908-107">Vanno da meno potenti ma meno costose da molto potenti ma costosa.</span><span class="sxs-lookup"><span data-stu-id="70908-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="70908-108">Per qualsiasi requisito di estendibilità specifico, è necessario scegliere il meccanismo di estendibilità meno costoso che soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="70908-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="70908-109">Tenere presente che è in genere, è possibile aggiungere ulteriori estendibilità in un secondo momento, ma è mai possibile trasferirli immediatamente senza introdurre modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="70908-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70908-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="70908-110">In This Section</span></span>  
 [<span data-ttu-id="70908-111">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="70908-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="70908-112">Membri protetti</span><span class="sxs-lookup"><span data-stu-id="70908-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="70908-113">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="70908-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="70908-114">Membri virtuali</span><span class="sxs-lookup"><span data-stu-id="70908-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="70908-115">Astrazioni (interfacce e tipi astratti)</span><span class="sxs-lookup"><span data-stu-id="70908-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="70908-116">Classi base per l'implementazione di astrazioni</span><span class="sxs-lookup"><span data-stu-id="70908-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="70908-117">Sealing</span><span class="sxs-lookup"><span data-stu-id="70908-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="70908-118">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="70908-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="70908-119">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="70908-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70908-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70908-120">See Also</span></span>  
 [<span data-ttu-id="70908-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="70908-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
