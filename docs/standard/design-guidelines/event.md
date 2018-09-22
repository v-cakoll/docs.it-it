---
title: Progettazione di eventi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577665"
---
# <a name="event-design"></a><span data-ttu-id="8d973-102">Progettazione di eventi</span><span class="sxs-lookup"><span data-stu-id="8d973-102">Event Design</span></span>
<span data-ttu-id="8d973-103">Gli eventi sono la forma più diffuso di callback (costrutti che consentono al framework di effettuare chiamate nel codice utente).</span><span class="sxs-lookup"><span data-stu-id="8d973-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="8d973-104">Altri meccanismi di callback che includono membri accettando i delegati, i membri virtuali e basata sull'interfaccia plug-in. I dati di studi di utilizzabilità indicano che la maggior parte degli sviluppatori sono più a proprio agio usando gli eventi che usano altri meccanismi di callback.</span><span class="sxs-lookup"><span data-stu-id="8d973-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="8d973-105">Gli eventi sono perfettamente integrati con Visual Studio e linguaggi.</span><span class="sxs-lookup"><span data-stu-id="8d973-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="8d973-106">È importante tenere presente che esistono due gruppi di eventi: gli eventi generati prima uno stato delle modifiche del sistema, denominato pre- eventi e gli eventi generati dopo uno stato modificato, denominato eventi successivi.</span><span class="sxs-lookup"><span data-stu-id="8d973-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="8d973-107">Un esempio di un pre-evento di sarebbe `Form.Closing`, che viene generato prima della chiusura di un form.</span><span class="sxs-lookup"><span data-stu-id="8d973-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="8d973-108">Un esempio di un post-evento di sarebbe `Form.Closed`, che viene generato dopo la chiusura di un form.</span><span class="sxs-lookup"><span data-stu-id="8d973-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="8d973-109">**✓ DO** viene usato il termine "generazione" per gli eventi anziché "generazione" o "trigger".</span><span class="sxs-lookup"><span data-stu-id="8d973-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="8d973-110">**✓ DO** utilizzare <xref:System.EventHandler%601?displayProperty=nameWithType> anziché creare manualmente nuovi delegati da utilizzare come gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="8d973-111">**✓ CONSIDER** utilizzando una sottoclasse di <xref:System.EventArgs> come argomento dell'evento, a meno che non si è assolutamente certi l'evento non sarà mai necessario eseguire tutti i dati per il metodo gestione eventi, nel qual caso è possibile utilizzare il `EventArgs` digitare direttamente.</span><span class="sxs-lookup"><span data-stu-id="8d973-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="8d973-112">Se si invia un'API usando `EventArgs` direttamente, non sarà in grado di aggiungere tutti i dati devono essere trasportati senza compromettere la compatibilità con l'evento.</span><span class="sxs-lookup"><span data-stu-id="8d973-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="8d973-113">Se si usa una sottoclasse, anche se inizialmente completamente vuote, sarà possibile aggiungere proprietà alla sottoclasse quando necessario.</span><span class="sxs-lookup"><span data-stu-id="8d973-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="8d973-114">**✓ DO** utilizzare un metodo virtuale protetto per la generazione di ogni evento.</span><span class="sxs-lookup"><span data-stu-id="8d973-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="8d973-115">Questa opzione è disponibile solo per gli eventi non statici su classi non sealed, non per gli struct, le classi sealed o eventi statici.</span><span class="sxs-lookup"><span data-stu-id="8d973-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="8d973-116">Lo scopo del metodo è fornire un modo per una classe derivata gestire l'evento utilizzando una sostituzione.</span><span class="sxs-lookup"><span data-stu-id="8d973-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="8d973-117">Si esegue l'override è un modo più flessibile, veloce e più naturale per gestire gli eventi di classe di base nelle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="8d973-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="8d973-118">Per convenzione, il nome del metodo deve iniziare con "On" e precedere con il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8d973-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="8d973-119">La classe derivata può scegliere di non chiamare l'implementazione di base del metodo nel relativo override.</span><span class="sxs-lookup"><span data-stu-id="8d973-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="8d973-120">Prevedere questa possibilità non includendo qualsiasi elaborazione del metodo che è necessario per la classe di base funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="8d973-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="8d973-121">**✓ DO** deve accettare un parametro al metodo protetto che genera un evento.</span><span class="sxs-lookup"><span data-stu-id="8d973-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="8d973-122">Il parametro deve essere denominato `e` e deve essere digitato come la classe di argomenti di evento.</span><span class="sxs-lookup"><span data-stu-id="8d973-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="8d973-123">**X DO NOT** passare null come mittente quando viene generato un evento non statico.</span><span class="sxs-lookup"><span data-stu-id="8d973-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="8d973-124">**✓ DO** passare null come mittente quando viene generato un evento statico.</span><span class="sxs-lookup"><span data-stu-id="8d973-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="8d973-125">**X DO NOT** passare null come parametro di dati dell'evento quando viene generato un evento.</span><span class="sxs-lookup"><span data-stu-id="8d973-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="8d973-126">È necessario passare `EventArgs.Empty` se non si desidera passare tutti i dati per il metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="8d973-127">Gli sviluppatori si aspettano questo parametro non deve essere null.</span><span class="sxs-lookup"><span data-stu-id="8d973-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="8d973-128">**✓ CONSIDER** generazione di eventi a cui l'utente finale può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="8d973-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="8d973-129">Si applica solo agli eventi precedenti.</span><span class="sxs-lookup"><span data-stu-id="8d973-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="8d973-130">Usare <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o la relativa sottoclasse come argomento dell'evento per consentire all'utente finale Annulla gli eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="8d973-131">Progettazione di gestore dell'evento personalizzato</span><span class="sxs-lookup"><span data-stu-id="8d973-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="8d973-132">Vi sono casi in cui `EventHandler<T>` non può essere utilizzato, ad esempio quando è necessario che il framework lavorare con le versioni precedenti di CLR, che non supporta Generics.</span><span class="sxs-lookup"><span data-stu-id="8d973-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="8d973-133">In questi casi, potrebbe essere necessario progettare e sviluppare un delegato del gestore eventi personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8d973-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="8d973-134">**✓ DO** utilizzare un tipo restituito void per gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="8d973-135">Un gestore eventi può richiamare più metodi, possibilmente su più oggetti di gestione di eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="8d973-136">Se i metodi di gestione degli eventi sono stati consentiti per restituire un valore, non vi sarà più valori restituiti per ogni chiamata di eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="8d973-137">**✓ DO** usare `object` come tipo del primo parametro del gestore dell'evento e chiamarlo `sender`.</span><span class="sxs-lookup"><span data-stu-id="8d973-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="8d973-138">**✓ DO** usare <xref:System.EventArgs?displayProperty=nameWithType> o la relativa sottoclasse come il tipo del secondo parametro del gestore dell'evento e chiamarlo `e`.</span><span class="sxs-lookup"><span data-stu-id="8d973-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="8d973-139">**X DO NOT** avere più di due parametri sui gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="8d973-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="8d973-140">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="8d973-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8d973-141">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8d973-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d973-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d973-142">See also</span></span>

- [<span data-ttu-id="8d973-143">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="8d973-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="8d973-144">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="8d973-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
