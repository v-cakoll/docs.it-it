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
ms.openlocfilehash: ad7774fd197db80ce84b3b8a5baa4e9ee06b6cef
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289798"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="3fcf3-102">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="3fcf3-102">Events and Callbacks</span></span>
<span data-ttu-id="3fcf3-103">I callback sono punti di estensibilità che consentono a un Framework di richiamare il codice utente tramite un delegato.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="3fcf3-104">Questi delegati vengono in genere passati al Framework tramite un parametro di un metodo.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="3fcf3-105">Gli eventi sono un caso speciale di callback che supporta una sintassi semplice e coerente per fornire il delegato (un gestore eventi).</span><span class="sxs-lookup"><span data-stu-id="3fcf3-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="3fcf3-106">Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono supporto per l'uso di API basate su eventi.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="3fcf3-107">(Vedere [progettazione degli eventi](event.md)).</span><span class="sxs-lookup"><span data-stu-id="3fcf3-107">(See [Event Design](event.md).)</span></span>

 <span data-ttu-id="3fcf3-108">✔️ CONSIGLIABILE usare i callback per consentire agli utenti di fornire codice personalizzato che deve essere eseguito dal Framework.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-108">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="3fcf3-109">✔️ CONSIGLIABILE utilizzare gli eventi per consentire agli utenti di personalizzare il comportamento di un Framework senza la necessità di comprendere la progettazione orientata a oggetti.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-109">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="3fcf3-110">✔️ preferiscono gli eventi tramite callback semplici, perché sono più familiari a una gamma più ampia di sviluppatori e sono integrati con il completamento delle istruzioni di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-110">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="3fcf3-111">❌EVITARE di usare i callback nelle API sensibili alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-111">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="3fcf3-112">Quando si definiscono le API con callback, ✔️ usare i nuovi `Func<...>` `Action<...>` tipi, o `Expression<...>` anziché delegati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-112">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="3fcf3-113">`Func<...>`e `Action<...>` rappresentano delegati generici.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="3fcf3-114">`Expression<...>`rappresenta le definizioni di funzione che possono essere compilate e successivamente richiamate in fase di esecuzione, ma possono anche essere serializzate e passate ai processi remoti.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at run time but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="3fcf3-115">✔️ misurare e comprendere le implicazioni relative alle prestazioni dell'utilizzo di `Expression<...>` , anziché utilizzare i `Func<...>` `Action<...>` delegati e.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-115">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="3fcf3-116">`Expression<...>`i tipi sono nella maggior parte dei casi equivalenti logicamente ai `Func<...>` `Action<...>` delegati e.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="3fcf3-117">La differenza principale tra di esse è che i delegati devono essere utilizzati negli scenari di processo locale; le espressioni sono destinate ai casi in cui è vantaggioso e possibile valutare l'espressione in un processo o in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="3fcf3-118">✔️ tenere presente che chiamando un delegato si esegue codice arbitrario che potrebbe avere ripercussioni sulla sicurezza, la correttezza e la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="3fcf3-118">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="3fcf3-119">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3fcf3-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3fcf3-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3fcf3-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3fcf3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fcf3-121">See also</span></span>

- [<span data-ttu-id="3fcf3-122">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="3fcf3-122">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="3fcf3-123">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3fcf3-123">Framework Design Guidelines</span></span>](index.md)
