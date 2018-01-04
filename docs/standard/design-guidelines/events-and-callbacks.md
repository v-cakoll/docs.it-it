---
title: Eventi e callback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 39dd4e31e84e455b72ce53bd8abffd650ce77dfc
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="events-and-callbacks"></a><span data-ttu-id="98f23-102">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="98f23-102">Events and Callbacks</span></span>
<span data-ttu-id="98f23-103">I callback sono i punti di estendibilità che consentono un framework di richiamare il codice utente tramite un delegato.</span><span class="sxs-lookup"><span data-stu-id="98f23-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="98f23-104">Questi delegati sono in genere passati al framework tramite un parametro di un metodo.</span><span class="sxs-lookup"><span data-stu-id="98f23-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="98f23-105">Gli eventi sono un tipo speciale di callback che supporta la sintassi semplice e uniforme per fornire il delegato (gestore eventi).</span><span class="sxs-lookup"><span data-stu-id="98f23-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="98f23-106">Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono informazioni sull'utilizzo di API basata su eventi.</span><span class="sxs-lookup"><span data-stu-id="98f23-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="98f23-107">(Vedere [evento progettazione](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="98f23-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="98f23-108">**Provare a ✓** mediante i callback per consentire agli utenti di fornire codice personalizzato deve essere eseguito dal framework.</span><span class="sxs-lookup"><span data-stu-id="98f23-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="98f23-109">**Provare a ✓** mediante gli eventi per consentire agli utenti di personalizzare il comportamento di un framework senza la necessità di informazioni sulla progettazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="98f23-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="98f23-110">**✓ SI** preferire eventi semplici callback, perché sono più familiari a una gamma più ampia di sviluppatori e sono integrati con il completamento delle istruzioni di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98f23-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="98f23-111">**X evitare** usare callback nelle API sensibili alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="98f23-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="98f23-112">**✓ SI** usare il nuovo `Func<...>`, `Action<...>`, o `Expression<...>` tipi anziché delegati personalizzati, quando si definiscono le API con callback.</span><span class="sxs-lookup"><span data-stu-id="98f23-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="98f23-113">`Func<...>`e `Action<...>` rappresentano i delegati generici.</span><span class="sxs-lookup"><span data-stu-id="98f23-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="98f23-114">`Expression<...>`rappresenta le definizioni di funzione che possono essere compilate e successivamente viene richiamate in fase di esecuzione ma può anche essere serializzate e passate a processi remoti.</span><span class="sxs-lookup"><span data-stu-id="98f23-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="98f23-115">**✓ SI** misurare e comprendere le implicazioni sulle prestazioni dell'utilizzo di `Expression<...>`, anziché utilizzare `Func<...>` e `Action<...>` delegati.</span><span class="sxs-lookup"><span data-stu-id="98f23-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="98f23-116">`Expression<...>`i tipi sono in genere equivalente logico di `Func<...>` e `Action<...>` delegati.</span><span class="sxs-lookup"><span data-stu-id="98f23-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="98f23-117">La differenza principale è che i delegati sono destinati a essere utilizzato in scenari di processo locale. le espressioni sono destinate a casi in cui sia utile e consente di valutare l'espressione in un computer o un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="98f23-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="98f23-118">**✓ SI** comprendere che la chiamata a un delegato, si eseguono codice arbitrario e che potrebbe avere ripercussioni di sicurezza, la correttezza e compatibilità.</span><span class="sxs-lookup"><span data-stu-id="98f23-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="98f23-119">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="98f23-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="98f23-120">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="98f23-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f23-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98f23-121">See Also</span></span>  
 [<span data-ttu-id="98f23-122">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="98f23-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="98f23-123">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="98f23-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
