---
title: Eventi e callback
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: KrzysztofCwalina
ms.openlocfilehash: 3609d6ac4847cb081740fd698869df4976f83f8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960397"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="88d34-102">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="88d34-102">Events and Callbacks</span></span>
<span data-ttu-id="88d34-103">I callback sono punti di estendibilità che consentono un framework di eseguire il callback nel codice utente attraverso un delegato.</span><span class="sxs-lookup"><span data-stu-id="88d34-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="88d34-104">Questi delegati vengono in genere passati al framework tramite un parametro di un metodo.</span><span class="sxs-lookup"><span data-stu-id="88d34-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="88d34-105">Gli eventi sono un caso speciale di callback che supporta la sintassi semplice e uniforme per fornire il delegato (un gestore eventi).</span><span class="sxs-lookup"><span data-stu-id="88d34-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="88d34-106">Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono informazioni sull'uso di API basate su eventi.</span><span class="sxs-lookup"><span data-stu-id="88d34-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="88d34-107">(Vedere [progettazione di eventi](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="88d34-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="88d34-108">**✓ CONSIDER** utilizzando i callback per permettere agli utenti di fornire codice personalizzato deve essere eseguita dal framework.</span><span class="sxs-lookup"><span data-stu-id="88d34-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="88d34-109">**✓ CONSIDER** mediante gli eventi per consentire agli utenti di personalizzare il comportamento di un framework senza la necessità di informazioni sulla progettazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="88d34-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="88d34-110">**✓ DO** preferire eventi semplici callback, perché sono più familiari a una gamma più ampia di sviluppatori e integrati con il completamento delle istruzioni di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="88d34-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="88d34-111">**X AVOID** usare callback nelle API sensibili alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="88d34-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="88d34-112">**✓ DO** usare il nuovo `Func<...>`, `Action<...>`, o `Expression<...>` tipi anziché delegati personalizzati, quando si definiscono le API con callback.</span><span class="sxs-lookup"><span data-stu-id="88d34-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="88d34-113">`Func<...>` e `Action<...>` rappresentano i delegati generici.</span><span class="sxs-lookup"><span data-stu-id="88d34-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="88d34-114">`Expression<...>` rappresenta le definizioni di funzione che possono essere compilate e successivamente richiamate in fase di esecuzione ma può anche essere serializzate e passate a processi remoti.</span><span class="sxs-lookup"><span data-stu-id="88d34-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="88d34-115">**✓ DO** misurare e comprendere le implicazioni sulle prestazioni dell'uso `Expression<...>`, anziché utilizzare `Func<...>` e `Action<...>` delegati.</span><span class="sxs-lookup"><span data-stu-id="88d34-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="88d34-116">`Expression<...>` i tipi sono logicamente equivalente alla maggior parte dei casi `Func<...>` e `Action<...>` delegati.</span><span class="sxs-lookup"><span data-stu-id="88d34-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="88d34-117">La differenza principale tra di esse è che i delegati sono destinati a essere usato in scenari del processo locale. le espressioni sono concepite per casi in cui risulta vantaggioso e consente di valutare l'espressione in una macchina o il processo remoto.</span><span class="sxs-lookup"><span data-stu-id="88d34-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="88d34-118">**✓ DO** comprendere che la chiamata a un delegato, si eseguono codice arbitrario e che potrebbe avere ripercussioni sicurezza, la correttezza e compatibilità.</span><span class="sxs-lookup"><span data-stu-id="88d34-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="88d34-119">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="88d34-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="88d34-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="88d34-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d34-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88d34-121">See also</span></span>

- [<span data-ttu-id="88d34-122">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="88d34-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="88d34-123">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="88d34-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
