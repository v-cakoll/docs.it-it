---
title: Progettazione finalizzata all'estensibilità
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46697529"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="ed8f6-102">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="ed8f6-102">Designing for Extensibility</span></span>
<span data-ttu-id="ed8f6-103">Un aspetto importante della progettazione di un framework è assicurare che l'estendibilità del framework è stato considerato con attenzione.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="ed8f6-104">È necessario comprendere i costi e vantaggi associati vari meccanismi di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="ed8f6-105">In questo capitolo contribuisce di stabilire quale dei meccanismi di estendibilità: creazione di una sottoclasse, eventi, i membri virtuali, callback e così via, possano soddisfare i requisiti del framework.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="ed8f6-106">Esistono diversi modi per consentire di estendibilità nel Framework.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="ed8f6-107">Sono compresi tra meno potenti, ma meno onerosi e molto potenti ma dispendioso.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="ed8f6-108">Per qualsiasi requisito di estendibilità specifico, è consigliabile scegliere il meccanismo di estendibilità meno costoso che soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="ed8f6-109">Tenere presente che in genere è possibile aggiungere maggiore estendibilità in un secondo momento, ma è bene non creare immediatamente senza introdurre modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed8f6-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ed8f6-110">In This Section</span></span>  
 [<span data-ttu-id="ed8f6-111">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="ed8f6-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="ed8f6-112">Membri protetti</span><span class="sxs-lookup"><span data-stu-id="ed8f6-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="ed8f6-113">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="ed8f6-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="ed8f6-114">Membri virtuali</span><span class="sxs-lookup"><span data-stu-id="ed8f6-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="ed8f6-115">Astrazioni (interfacce e tipi astratti)</span><span class="sxs-lookup"><span data-stu-id="ed8f6-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="ed8f6-116">Classi base per l'implementazione di astrazioni</span><span class="sxs-lookup"><span data-stu-id="ed8f6-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="ed8f6-117">Sealing</span><span class="sxs-lookup"><span data-stu-id="ed8f6-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="ed8f6-118">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="ed8f6-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ed8f6-119">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ed8f6-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8f6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed8f6-120">See also</span></span>

- [<span data-ttu-id="ed8f6-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="ed8f6-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
