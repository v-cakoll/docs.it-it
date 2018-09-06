---
title: Progettazione di interfacce
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c687d7622e82ee206b2201760818827398f8543b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863722"
---
# <a name="interface-design"></a><span data-ttu-id="6b13f-102">Progettazione di interfacce</span><span class="sxs-lookup"><span data-stu-id="6b13f-102">Interface Design</span></span>
<span data-ttu-id="6b13f-103">Sebbene la maggior parte delle API sono meglio modellate utilizzando le classi e struct, vi sono casi in cui le interfacce sono più appropriate oppure sono l'unica opzione.</span><span class="sxs-lookup"><span data-stu-id="6b13f-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="6b13f-104">CLR non supporta l'ereditarietà multipla (ad esempio, le classi CLR non possono ereditare da più di una classe di base), ma consente i tipi implementare una o più interfacce, oltre che eredita da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="6b13f-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="6b13f-105">Pertanto, interfacce vengono spesso usate per ottenere l'effetto dell'ereditarietà multipla.</span><span class="sxs-lookup"><span data-stu-id="6b13f-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="6b13f-106">Ad esempio, <xref:System.IDisposable> è un'interfaccia che consente ai tipi di supporto disposability indipendente da qualsiasi altra gerarchia di ereditarietà in cui si desidera partecipare.</span><span class="sxs-lookup"><span data-stu-id="6b13f-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="6b13f-107">L'altra situazione in cui la definizione di un'interfaccia è appropriata è durante la creazione di un'interfaccia comune che può essere supportata dai diversi tipi, inclusi alcuni tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="6b13f-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="6b13f-108">I tipi di valore non possono ereditare da tipi diversi da <xref:System.ValueType>, ma possono implementare interfacce, quindi, usando un'interfaccia è l'unica opzione per fornire un tipo base comune.</span><span class="sxs-lookup"><span data-stu-id="6b13f-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="6b13f-109">**✓ DO** definire un'interfaccia se è necessario alcune API comuni devono essere supportati da un set di tipi che include i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="6b13f-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="6b13f-110">**✓ CONSIDER** che definisce un'interfaccia se è necessario supportare le funzionalità nei tipi che ereditano già da un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="6b13f-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="6b13f-111">**X AVOID** utilizzano interfacce marcatore (interfacce senza membri).</span><span class="sxs-lookup"><span data-stu-id="6b13f-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="6b13f-112">Se è necessario contrassegnare una classe come se avessero una caratteristica specifica (indicatore), in generale, usare un attributo personalizzato anziché a un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="6b13f-113">**✓ DO** fornire almeno un tipo che è un'implementazione di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="6b13f-114">Operazioni di questo monitoraggio consente di convalidare la progettazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="6b13f-115">Ad esempio, <xref:System.Collections.Generic.List%601> è un'implementazione del <xref:System.Collections.Generic.IList%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="6b13f-116">**✓ DO** forniscono almeno una API che utilizza ciascuna interfaccia definita (un metodo che utilizza l'interfaccia come un parametro o una proprietà tipizzato come l'interfaccia).</span><span class="sxs-lookup"><span data-stu-id="6b13f-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="6b13f-117">Operazioni di questo monitoraggio consente di convalidare la progettazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="6b13f-118">Ad esempio, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> utilizza il <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="6b13f-119">**X DO NOT** aggiungere membri a un'interfaccia che è già stata distribuita.</span><span class="sxs-lookup"><span data-stu-id="6b13f-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="6b13f-120">Questa operazione causa l'interruzione implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6b13f-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="6b13f-121">È necessario creare una nuova interfaccia per evitare problemi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="6b13f-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="6b13f-122">Fatta eccezione per le situazioni descritte in queste linee guida, è consigliabile, in generale, scegliere classi anziché le interfacce nella progettazione di librerie riutilizzabili di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6b13f-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="6b13f-123">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="6b13f-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6b13f-124">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="6b13f-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b13f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b13f-125">See also</span></span>

- [<span data-ttu-id="6b13f-126">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="6b13f-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="6b13f-127">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="6b13f-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
