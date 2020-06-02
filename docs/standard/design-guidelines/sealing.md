---
title: sealed
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: a54c68efb4ac114fe0e5a5712eca877bef35c103
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290110"
---
# <a name="sealing"></a><span data-ttu-id="d3649-102">sealed</span><span class="sxs-lookup"><span data-stu-id="d3649-102">Sealing</span></span>
<span data-ttu-id="d3649-103">Una delle funzionalità dei Framework orientati a oggetti è che gli sviluppatori possono estenderli e personalizzarli in modi imprevisti dalle finestre di progettazione del Framework.</span><span class="sxs-lookup"><span data-stu-id="d3649-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="d3649-104">Questa è la potenza e il pericolo della progettazione estendibile.</span><span class="sxs-lookup"><span data-stu-id="d3649-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="d3649-105">Quando si progetta il Framework, è quindi molto importante progettare accuratamente per l'estendibilità quando si desidera e limitare l'estendibilità quando è pericoloso.</span><span class="sxs-lookup"><span data-stu-id="d3649-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="d3649-106">Un meccanismo potente che impedisce l'estendibilità è la chiusura.</span><span class="sxs-lookup"><span data-stu-id="d3649-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="d3649-107">È possibile sigillare la classe o i singoli membri.</span><span class="sxs-lookup"><span data-stu-id="d3649-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="d3649-108">La chiusura di una classe impedisce agli utenti di ereditare dalla classe.</span><span class="sxs-lookup"><span data-stu-id="d3649-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="d3649-109">La chiusura di un membro impedisce agli utenti di eseguire l'override di un membro specifico.</span><span class="sxs-lookup"><span data-stu-id="d3649-109">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="d3649-110">❌Non bloccare le classi senza avere un motivo valido.</span><span class="sxs-lookup"><span data-stu-id="d3649-110">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="d3649-111">La chiusura di una classe perché non è un buon motivo per considerare uno scenario di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="d3649-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="d3649-112">Gli utenti del Framework desiderano ereditare dalle classi per diversi motivi non ovvi, ad esempio l'aggiunta di pratici membri.</span><span class="sxs-lookup"><span data-stu-id="d3649-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="d3649-113">Per esempi di motivi non evidenti che gli utenti desiderano ereditare da un tipo, vedere [classi non sealed](unsealed-classes.md) .</span><span class="sxs-lookup"><span data-stu-id="d3649-113">See [Unsealed Classes](unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="d3649-114">Di seguito sono riportati i motivi validi per la chiusura di una classe:</span><span class="sxs-lookup"><span data-stu-id="d3649-114">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="d3649-115">La classe è una classe statica.</span><span class="sxs-lookup"><span data-stu-id="d3649-115">The class is a static class.</span></span> <span data-ttu-id="d3649-116">Vedere [progettazione di classi statiche](static-class.md).</span><span class="sxs-lookup"><span data-stu-id="d3649-116">See [Static Class Design](static-class.md).</span></span>

- <span data-ttu-id="d3649-117">La classe archivia i segreti sensibili per la sicurezza nei membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="d3649-117">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="d3649-118">La classe eredita molti membri virtuali e il costo di sealing singolarmente supererà i vantaggi derivanti dall'uscita dalla classe.</span><span class="sxs-lookup"><span data-stu-id="d3649-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="d3649-119">La classe è un attributo che richiede una ricerca molto rapida del runtime.</span><span class="sxs-lookup"><span data-stu-id="d3649-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="d3649-120">Gli attributi sealed hanno livelli di prestazioni leggermente più elevati rispetto a quelli non bloccati.</span><span class="sxs-lookup"><span data-stu-id="d3649-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="d3649-121">Vedere [attributi](attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d3649-121">See [Attributes](attributes.md).</span></span>

 <span data-ttu-id="d3649-122">❌NON dichiarare membri protetti o virtuali su tipi sealed.</span><span class="sxs-lookup"><span data-stu-id="d3649-122">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="d3649-123">Per definizione, i tipi sealed non possono essere ereditati da.</span><span class="sxs-lookup"><span data-stu-id="d3649-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="d3649-124">Ciò significa che i membri protetti nei tipi sealed non possono essere chiamati e che non è possibile eseguire l'override dei metodi virtuali sui tipi sealed.</span><span class="sxs-lookup"><span data-stu-id="d3649-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="d3649-125">✔️ tenere in considerazione i membri che si sostituiscono.</span><span class="sxs-lookup"><span data-stu-id="d3649-125">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="d3649-126">I problemi che possono derivare dall'introduzione di membri virtuali (descritti in [membri virtuali](virtual-members.md)) si applicano anche alle sostituzioni, anche se a un livello leggermente inferiore.</span><span class="sxs-lookup"><span data-stu-id="d3649-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="d3649-127">La chiusura di una sostituzione protegge da questi problemi a partire da quel punto nella gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="d3649-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="d3649-128">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d3649-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d3649-129">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d3649-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d3649-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3649-130">See also</span></span>

- [<span data-ttu-id="d3649-131">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d3649-131">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d3649-132">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="d3649-132">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="d3649-133">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="d3649-133">Unsealed Classes</span></span>](unsealed-classes.md)
