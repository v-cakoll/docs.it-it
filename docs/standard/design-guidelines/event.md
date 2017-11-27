---
title: Progettazione di eventi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8dcd1003b3f93db733ece4f90340d1d98867d2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="event-design"></a><span data-ttu-id="d71de-102">Progettazione di eventi</span><span class="sxs-lookup"><span data-stu-id="d71de-102">Event Design</span></span>
<span data-ttu-id="d71de-103">Gli eventi sono la forma più diffuse di callback (costrutti che consentono il framework per effettuare chiamate nel codice utente).</span><span class="sxs-lookup"><span data-stu-id="d71de-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="d71de-104">Altri meccanismi di callback che includono membri accettando delegati, i membri virtuali e basata sull'interfaccia plug-in. Dati da studi di usabilità indicano che la maggior parte degli sviluppatori hanno maggiore familiarità con gli eventi che utilizzano altri meccanismi di callback.</span><span class="sxs-lookup"><span data-stu-id="d71de-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="d71de-105">Gli eventi sono perfettamente integrati con Visual Studio e molti linguaggi.</span><span class="sxs-lookup"><span data-stu-id="d71de-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="d71de-106">È importante notare che sono presenti due gruppi di eventi: eventi generati prima di uno stato delle modifiche del sistema, denominati eventi precedenti e gli eventi generati dopo uno stato di modifica, chiamati eventi successivi.</span><span class="sxs-lookup"><span data-stu-id="d71de-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="d71de-107">Un esempio di un pre-evento di `Form.Closing`, che viene generato prima della chiusura di un form.</span><span class="sxs-lookup"><span data-stu-id="d71de-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="d71de-108">Un esempio di un post-evento di `Form.Closed`, che viene generato dopo la chiusura di un form.</span><span class="sxs-lookup"><span data-stu-id="d71de-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="d71de-109">**✓ SI** viene usato il termine "generazione" per gli eventi anziché "generazione" o "trigger".</span><span class="sxs-lookup"><span data-stu-id="d71de-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="d71de-110">**✓ SI** utilizzare <xref:System.EventHandler%601?displayProperty=nameWithType> anziché creare manualmente nuovi delegati da utilizzare come gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="d71de-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="d71de-111">**✓ Provare a** utilizza una sottoclasse di <xref:System.EventArgs> come argomento dell'evento, a meno che non si è assolutamente certi l'evento non sarà mai necessario eseguire tutti i dati per il metodo gestione eventi, nel qual caso è possibile utilizzare il `EventArgs` digitare direttamente.</span><span class="sxs-lookup"><span data-stu-id="d71de-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="d71de-112">Se si fornisce un'API tramite `EventArgs` direttamente, non sarà in grado di aggiungere tutti i dati da eseguire con l'evento senza interrompere la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="d71de-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="d71de-113">Se si utilizza una sottoclasse, anche se inizialmente completamente vuote, sarà possibile aggiungere proprietà alla sottoclasse quando necessario.</span><span class="sxs-lookup"><span data-stu-id="d71de-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="d71de-114">**✓ SI** utilizzare un metodo virtuale protetto per generare ciascun evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="d71de-115">Questa opzione è disponibile solo per eventi non statici su classi non sealed, non per le strutture, le classi sealed o eventi statici.</span><span class="sxs-lookup"><span data-stu-id="d71de-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="d71de-116">Lo scopo del metodo è fornire un modo per una classe derivata per gestire l'evento utilizzando una sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d71de-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="d71de-117">Si esegue l'override è un modo più flessibile, più veloce e più semplice gestire gli eventi di classe di base nelle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="d71de-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="d71de-118">Per convenzione, il nome del metodo deve iniziare con "On" e con il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="d71de-119">La classe derivata è possibile scegliere di non chiamare l'implementazione di base del metodo nel relativo override.</span><span class="sxs-lookup"><span data-stu-id="d71de-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="d71de-120">Preparare per questo oggetto, non includendo qualsiasi elaborazione nel metodo che è necessario per la classe base funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="d71de-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="d71de-121">**✓ SI** accettare un parametro al metodo protetto che genera un evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="d71de-122">Il parametro deve essere denominato `e` e deve essere digitato come la classe di argomenti dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="d71de-123">**X non** passare null come mittente quando viene generato un evento non statico.</span><span class="sxs-lookup"><span data-stu-id="d71de-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="d71de-124">**✓ SI** passare null come mittente quando viene generato un evento statico.</span><span class="sxs-lookup"><span data-stu-id="d71de-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="d71de-125">**X non** passare null come parametro di dati dell'evento quando viene generato un evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="d71de-126">È necessario passare `EventArgs.Empty` se non si desidera passare tutti i dati per il metodo di gestione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="d71de-127">È previsto che questo parametro non deve essere null.</span><span class="sxs-lookup"><span data-stu-id="d71de-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="d71de-128">**Provare a ✓** la generazione di eventi che è possibile annullare l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d71de-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="d71de-129">Questo vale solo per gli eventi precedenti.</span><span class="sxs-lookup"><span data-stu-id="d71de-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="d71de-130">Utilizzare <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o la relativa sottoclasse come argomento dell'evento per consentire all'utente di annullare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="d71de-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="d71de-131">Progettazione di gestori di eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="d71de-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="d71de-132">Vi sono casi in cui `EventHandler<T>` non può essere usata, ad esempio quando il framework richiede l'utilizzo con le versioni precedenti di CLR, che non supporta Generics.</span><span class="sxs-lookup"><span data-stu-id="d71de-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="d71de-133">In questi casi, potrebbe essere necessario progettare e sviluppare un delegato del gestore eventi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d71de-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="d71de-134">**✓ SI** utilizzare un tipo restituito void per gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="d71de-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="d71de-135">Un gestore eventi è possibile richiamare metodi, anche su più oggetti di gestione di più eventi.</span><span class="sxs-lookup"><span data-stu-id="d71de-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="d71de-136">Se i metodi di gestione degli eventi sono stati consentiti per restituire un valore, non vi sarà più valori restituiti per ogni chiamata a un evento.</span><span class="sxs-lookup"><span data-stu-id="d71de-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="d71de-137">**✓ SI** utilizzare `object` come il tipo del primo parametro del gestore eventi e lo chiama `sender`.</span><span class="sxs-lookup"><span data-stu-id="d71de-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="d71de-138">**✓ SI** utilizzare <xref:System.EventArgs?displayProperty=nameWithType> o la relativa sottoclasse come il tipo del secondo parametro del gestore eventi e lo chiama `e`.</span><span class="sxs-lookup"><span data-stu-id="d71de-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="d71de-139">**X non** avere più di due parametri sui gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="d71de-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="d71de-140">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d71de-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d71de-141">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d71de-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71de-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d71de-142">See Also</span></span>  
 [<span data-ttu-id="d71de-143">Linee guida di progettazione di membro</span><span class="sxs-lookup"><span data-stu-id="d71de-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="d71de-144">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d71de-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
