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
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44336914"
---
# <a name="sealing"></a><span data-ttu-id="f3f85-102">sealed</span><span class="sxs-lookup"><span data-stu-id="f3f85-102">Sealing</span></span>
<span data-ttu-id="f3f85-103">Una delle funzionalità orientate a oggetti Framework è che gli sviluppatori possono estendere e personalizzarli in modi non previsti per i progettisti del framework.</span><span class="sxs-lookup"><span data-stu-id="f3f85-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="f3f85-104">Questa è la potenza e pericolo di progettazione estendibile.</span><span class="sxs-lookup"><span data-stu-id="f3f85-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="f3f85-105">Quando si progetta il tuo framework, è quindi molto importante per progettare con attenzione per l'estensibilità quando lo si desidera e per limitare l'estendibilità è pericoloso.</span><span class="sxs-lookup"><span data-stu-id="f3f85-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="f3f85-106">Una soluzione efficace che impedisce l'estendibilità è sealed.</span><span class="sxs-lookup"><span data-stu-id="f3f85-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="f3f85-107">È possibile applicare il seal classe o singoli membri.</span><span class="sxs-lookup"><span data-stu-id="f3f85-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="f3f85-108">Una classe impedisce agli utenti di ereditare dalla classe.</span><span class="sxs-lookup"><span data-stu-id="f3f85-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="f3f85-109">Come rendere sealed un membro impedisce agli utenti di eseguire l'override di un membro specifico.</span><span class="sxs-lookup"><span data-stu-id="f3f85-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="f3f85-110">**X DO NOT** bloccare classi senza un buon motivo per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f3f85-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="f3f85-111">Come rendere sealed una classe poiché è possibile pensare a uno scenario di estensibilità non è una buona ragione.</span><span class="sxs-lookup"><span data-stu-id="f3f85-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="f3f85-112">Gli utenti di Framework, ad esempio ereditare dalle classi per vari motivi non prevedibile, quali l'aggiunta di membri di praticità.</span><span class="sxs-lookup"><span data-stu-id="f3f85-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="f3f85-113">Visualizzare [classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md) per alcuni dei motivi non prevedibile degli utenti desiderano ereditare da un tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f85-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="f3f85-114">Buone ragioni per una classe includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f3f85-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="f3f85-115">La classe è una classe statica.</span><span class="sxs-lookup"><span data-stu-id="f3f85-115">The class is a static class.</span></span> <span data-ttu-id="f3f85-116">Visualizzare [progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="f3f85-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="f3f85-117">La classe archivia i segreti sensibili alla sicurezza in membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="f3f85-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="f3f85-118">La classe eredita molte membri virtuali e il costo del sealing li singolarmente sarebbe superano i vantaggi di lasciare la classe non sealed.</span><span class="sxs-lookup"><span data-stu-id="f3f85-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="f3f85-119">La classe è un attributo che richiede la ricerca di runtime molto veloce.</span><span class="sxs-lookup"><span data-stu-id="f3f85-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="f3f85-120">Gli attributi sealed hanno livelli di prestazioni leggermente superiori rispetto a quelli non sealed.</span><span class="sxs-lookup"><span data-stu-id="f3f85-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="f3f85-121">visualizzare [attributi](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="f3f85-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="f3f85-122">**X DO NOT** dichiarare membri protetti o virtuali su tipi sealed.</span><span class="sxs-lookup"><span data-stu-id="f3f85-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="f3f85-123">Per definizione, tipi sealed non possono essere ereditati da.</span><span class="sxs-lookup"><span data-stu-id="f3f85-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="f3f85-124">Ciò significa che i membri protetti nei tipi sealed non possono essere chiamati e metodi virtuali nei tipi sealed non possono essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="f3f85-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="f3f85-125">**✓ CONSIDER** sealing membri che si esegue l'override.</span><span class="sxs-lookup"><span data-stu-id="f3f85-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="f3f85-126">I problemi derivanti dall'introduzione a membri virtuali (descritto in [membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)) si applicano agli override, anche se a un livello leggermente inferiore.</span><span class="sxs-lookup"><span data-stu-id="f3f85-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="f3f85-127">Come rendere sealed un override ci consente di nascondere questi problemi a partire da quel punto nella gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="f3f85-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="f3f85-128">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="f3f85-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f3f85-129">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="f3f85-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f85-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3f85-130">See also</span></span>

- [<span data-ttu-id="f3f85-131">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="f3f85-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="f3f85-132">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="f3f85-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="f3f85-133">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="f3f85-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
