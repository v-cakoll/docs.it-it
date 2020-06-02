---
title: Progettazione finalizzata all'estensibilità
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 406c15b6ce42b637ed1bbb61761d05e040995579
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280244"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="a8436-102">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="a8436-102">Designing for Extensibility</span></span>
<span data-ttu-id="a8436-103">Un aspetto importante della progettazione di un Framework è garantire che l'estendibilità del Framework sia stata considerata attentamente.</span><span class="sxs-lookup"><span data-stu-id="a8436-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="a8436-104">A questo scopo è necessario comprendere i costi e i vantaggi associati a vari meccanismi di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="a8436-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="a8436-105">Questo capitolo aiuta a decidere quale meccanismo di estendibilità, ovvero sottoclassi, eventi, membri virtuali, callback e così via, è in grado di soddisfare al meglio i requisiti del Framework.</span><span class="sxs-lookup"><span data-stu-id="a8436-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="a8436-106">Esistono diversi modi per consentire l'estendibilità nei Framework.</span><span class="sxs-lookup"><span data-stu-id="a8436-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="a8436-107">Variano da meno potente ma meno costoso a molto potente ma costoso.</span><span class="sxs-lookup"><span data-stu-id="a8436-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="a8436-108">Per qualsiasi requisito di estendibilità, è necessario scegliere il meccanismo di estendibilità meno costosa che soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="a8436-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="a8436-109">Tenere presente che in genere è possibile aggiungere ulteriore estendibilità in un secondo momento, ma non è mai possibile eliminarla senza introdurre modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="a8436-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8436-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a8436-110">In This Section</span></span>  
 [<span data-ttu-id="a8436-111">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="a8436-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="a8436-112">Membri protetti</span><span class="sxs-lookup"><span data-stu-id="a8436-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="a8436-113">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="a8436-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="a8436-114">Membri virtuali</span><span class="sxs-lookup"><span data-stu-id="a8436-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="a8436-115">Astrazioni (tipi e interfacce astratte)</span><span class="sxs-lookup"><span data-stu-id="a8436-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="a8436-116">Classi base per l'implementazione di astrazioni</span><span class="sxs-lookup"><span data-stu-id="a8436-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="a8436-117">sealed</span><span class="sxs-lookup"><span data-stu-id="a8436-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="a8436-118">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="a8436-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a8436-119">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a8436-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8436-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8436-120">See also</span></span>

- [<span data-ttu-id="a8436-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="a8436-121">Framework Design Guidelines</span></span>](index.md)
