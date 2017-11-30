---
title: Notifiche di Garbage Collection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a>Notifiche di Garbage Collection
In alcune situazioni un'operazione completa di Garbage Collection (cioè di generazione 2) eseguita da Common Language Runtime può influire negativamente sulle prestazioni. Può trattarsi di un problema particolarmente con server che elaborano grandi volumi di richieste. In questo caso, una lunga procedura di garbage collection può provocare un timeout della richiesta. Per evitare un insieme completo che si verifichino durante un periodo critico, si può ricevere notifiche di garbage collection completa sta per raggiungere e intraprendere azioni per reindirizzare il carico di lavoro a un'altra istanza del server. È possibile anche forzare una raccolta, condizione che l'istanza del server corrente non è necessario elaborare le richieste.  
  
 Il <xref:System.GC.RegisterForFullGCNotification%2A> metodo registra la notifica quando il runtime rileva che sta per una garbage collection completa. Esistono due parti per questa notifica: quando sta per raggiungere la garbage collection completa e quando è stata completata la garbage collection completa.  
  
> [!WARNING]
>  Le notifiche vengono generate solo in caso di blocco delle operazioni di Garbage Collection. Quando il [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento di configurazione è abilitata, le Garbage Collection in background non saranno generate notifiche.  
  
 Per determinare quando è stata generata una notifica, utilizzare il <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi. In genere, usare questi metodi in un `while` ciclo per ottenere continuamente una <xref:System.GCNotificationStatus> enumerazione che indica lo stato della notifica. Se il valore è <xref:System.GCNotificationStatus.Succeeded>, è possibile eseguire le operazioni seguenti:  
  
-   In risposta a una notifica ottenuta con la <xref:System.GC.WaitForFullGCApproach%2A> (metodo), è possibile reindirizzare il carico di lavoro e possibilmente forzare una raccolta.  
  
-   In risposta a una notifica ottenuta con la <xref:System.GC.WaitForFullGCComplete%2A> (metodo), è possibile rendere l'istanza corrente di server disponibile per elaborare le richieste nuovamente. È anche possibile raccogliere informazioni. Ad esempio, è possibile utilizzare il <xref:System.GC.CollectionCount%2A> metodo per registrare il numero di raccolte.  
  
 Il <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi sono progettati per funzionare insieme. Utilizzo di uno senza l'altro può produrre risultati imprevisti.  
  
## <a name="full-garbage-collection"></a>Garbage Collection completa  
 Il runtime genera un'operazione completa di garbage collection quando uno degli scenari seguenti sono vere:  
  
-   Memoria insufficiente sia stato promosso alla generazione 2 per generare la raccolta di generazione 2 successiva.  
  
-   Memoria insufficiente è stato promosso nell'heap oggetti grandi per generare la raccolta di generazione 2 successiva.  
  
-   Una raccolta di generazione 1 viene riassegnata a una raccolta di generazione 2 a causa di altri fattori.  
  
 Le soglie specificate nel <xref:System.GC.RegisterForFullGCNotification%2A> metodo riguardano i primi due scenari. Tuttavia, nel primo scenario è non sempre riceveranno la notifica al momento proporzionale per i valori di soglia specificati per due motivi:  
  
-   Il runtime non controlla ogni allocazione di oggetti piccoli (per motivi di prestazioni).  
  
-   Generazione 1 raccolte innalzare di livello solo memoria alla generazione 2.  
  
 Il terzo scenario contribuisce inoltre all'incertezza di quando si riceveranno la notifica. Anche se non si tratta di una garanzia, esso si riveli utile per ridurre gli effetti di un inopportuna completa di garbage collection da reindirizzare le richieste durante questo periodo o forzando la raccolta quando possono essere gestita meglio.  
  
## <a name="notification-threshold-parameters"></a>Parametri della soglia di notifica  
 Il <xref:System.GC.RegisterForFullGCNotification%2A> metodo presenta due parametri per specificare i valori soglia degli oggetti di generazione 2 e l'heap oggetti grandi. Quando vengono soddisfatti questi valori, dovrebbe essere generata una notifica di garbage collection. Nella tabella seguente vengono descritti questi parametri.  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Un numero compreso tra 1 e 99 che specifica se la notifica deve essere generata basato sugli oggetti alzate di livello nella generazione 2.|  
|`largeObjectHeapThreshold`|Un numero compreso tra 1 e 99 che specifica se la notifica deve essere generata basato sugli oggetti allocati nell'heap degli oggetti di grandi dimensioni.|  
  
 Se si specifica un valore troppo elevato, è presente un elevato livello di probabilità che si riceverà una notifica, ma potrebbe essere troppo lungo un periodo di attesa prima che il runtime determina un insieme. Se si forzare una raccolta, si potrebbero richiedere più oggetti verrebbero recuperati se il runtime determina la raccolta.  
  
 Se si specifica un valore troppo basso, il runtime può provocare la raccolta prima che sia trascorso sufficiente tempo per ricevere una notifica.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente, un gruppo di server richieste Web in ingresso. Per simulare il carico di lavoro dell'elaborazione delle richieste, le matrici di byte vengono aggiunti a un <xref:System.Collections.Generic.List%601> insieme. Ogni server registrato per notifica di un'operazione di garbage collection e quindi avvia un thread nel `WaitForFullGCProc` metodo utente per monitorare costantemente il <xref:System.GCNotificationStatus> enumerazione restituito dal <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi.  
  
 Il <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi chiamano i rispettivi metodi utente di gestione degli eventi quando viene generata una notifica:  
  
-   `OnFullGCApproachNotify`  
  
     Questo metodo chiama il `RedirectRequests` metodo utente, che indica al server di Accodamento messaggi di richiesta di sospendere l'invio di richieste al server. Questa situazione viene simulata impostando la variabile a livello di classe `bAllocate` a `false` in modo che non vengano più allocati oggetti.  
  
     Successivamente, il `FinishExistingRequests` utente viene chiamato per completare l'elaborazione delle richieste in sospeso al server. Questa situazione viene simulata cancellando la <xref:System.Collections.Generic.List%601> insieme.  
  
     Infine, una garbage collection è causata perché il carico di lavoro è chiaro.  
  
-   `OnFullGCCompleteNotify`  
  
     Questo metodo chiama il metodo dell'utente `AcceptRequests` per riprendere l'accettazione di richieste perché il server non è più soggetto a garbage collection completa. Questa azione viene simulata impostando il `bAllocate` variabile `true` in modo che gli oggetti possono riprendere l'aggiunta di <xref:System.Collections.Generic.List%601> insieme.  
  
 Il codice seguente contiene il `Main` metodo dell'esempio.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Il codice seguente contiene il `WaitForFullGCProc` metodo utente, che contiene un ciclo while continuo per le notifiche di garbage collection.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Il codice seguente contiene il `OnFullGCApproachNotify` metodo chiamato dal  
  
 Metodo `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Il codice seguente contiene il `OnFullGCApproachComplete` metodo chiamato dal  
  
 Metodo `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Il codice seguente contiene i metodi di utente che vengono chiamati dal `OnFullGCApproachNotify` e `OnFullGCCompleteNotify` metodi. I metodi utente reindirizzano le richieste, completano le richieste esistenti e quindi riprendono le richieste dopo un'operazione completa di garbage collection si è verificato.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 L'esempio di codice completo è il seguente:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
