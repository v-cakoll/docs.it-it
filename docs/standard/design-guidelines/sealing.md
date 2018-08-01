---
title: sealed
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7202e10e41b9f114f42a4502ee2e6694bf3821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573740"
---
# <a name="sealing"></a><span data-ttu-id="b0546-102">sealed</span><span class="sxs-lookup"><span data-stu-id="b0546-102">Sealing</span></span>
<span data-ttu-id="b0546-103">Una delle funzionalità del Framework orientata a oggetti è che gli sviluppatori possono estendere e personalizzarli in modi imprevisti per le finestre di progettazione di framework.</span><span class="sxs-lookup"><span data-stu-id="b0546-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="b0546-104">Questa è la potenza e pericolo di progettazione estensibile.</span><span class="sxs-lookup"><span data-stu-id="b0546-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="b0546-105">Quando si progetta il framework, è pertanto molto importante per progettare con attenzione per l'estensibilità quando si desidera e per limitare l'estendibilità quando è pericoloso.</span><span class="sxs-lookup"><span data-stu-id="b0546-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="b0546-106">L'utilizzo di un meccanismo potente che impedisce l'estendibilità è sealed.</span><span class="sxs-lookup"><span data-stu-id="b0546-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="b0546-107">È possibile bloccare i singoli membri o classe.</span><span class="sxs-lookup"><span data-stu-id="b0546-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="b0546-108">Una classe impedisce agli utenti di ereditare dalla classe.</span><span class="sxs-lookup"><span data-stu-id="b0546-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="b0546-109">Chiusura di un membro impedisce agli utenti di un particolare membro viene sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="b0546-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="b0546-110">**X DO NOT** bloccare classi senza un buon motivo per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b0546-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="b0546-111">Chiusura di una classe poiché è possibile considerare uno scenario di estensibilità non è un buon motivo.</span><span class="sxs-lookup"><span data-stu-id="b0546-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="b0546-112">Gli utenti di Framework come ereditare da classi per vari motivi non prevedibile, ad esempio l'aggiunta di membri di praticità.</span><span class="sxs-lookup"><span data-stu-id="b0546-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="b0546-113">Vedere [classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md) per esempi di motivi non prevedibile gli utenti desiderano ereditare da un tipo.</span><span class="sxs-lookup"><span data-stu-id="b0546-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="b0546-114">Di seguito sono indicati i motivi validi per una classe:</span><span class="sxs-lookup"><span data-stu-id="b0546-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="b0546-115">La classe è una classe statica.</span><span class="sxs-lookup"><span data-stu-id="b0546-115">The class is a static class.</span></span> <span data-ttu-id="b0546-116">Vedere [progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="b0546-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="b0546-117">La classe archivia i segreti sensibili alla sicurezza in membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="b0546-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="b0546-118">La classe eredita molti membri virtuali e il costo del rendere sealed li singolarmente annullerebbe i vantaggi di lasciare la classe non sealed.</span><span class="sxs-lookup"><span data-stu-id="b0546-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="b0546-119">La classe è un attributo che richiede una ricerca di un runtime molto veloce.</span><span class="sxs-lookup"><span data-stu-id="b0546-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="b0546-120">Gli attributi sealed hanno livelli di prestazioni leggermente superiori rispetto a quelli non sealed.</span><span class="sxs-lookup"><span data-stu-id="b0546-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="b0546-121">vedere [attributi](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b0546-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="b0546-122">**X DO NOT** dichiarare membri protetti o virtuali su tipi sealed.</span><span class="sxs-lookup"><span data-stu-id="b0546-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="b0546-123">Per definizione, non è possibile ereditare tipi sealed.</span><span class="sxs-lookup"><span data-stu-id="b0546-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="b0546-124">Ciò significa che i membri protetti su tipi sealed non possono essere chiamati e metodi virtuali su tipi sealed non possono essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="b0546-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="b0546-125">**✓ CONSIDER** sealing membri che si esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="b0546-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="b0546-126">I problemi che possono derivare da introduzione membri virtuali (descritto in [membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)) si applicano a sostituzioni, anche se a un livello leggermente inferiore.</span><span class="sxs-lookup"><span data-stu-id="b0546-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="b0546-127">Come rendere sealed un override protegge da questi problemi, a partire da quel punto nella gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="b0546-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="b0546-128">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="b0546-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b0546-129">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b0546-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0546-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0546-130">See Also</span></span>  
 [<span data-ttu-id="b0546-131">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="b0546-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="b0546-132">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="b0546-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="b0546-133">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="b0546-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
