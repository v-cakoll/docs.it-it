---
title: Notifiche di Garbage Collection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: 389e851782edb82578c216951be440070b92723c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286002"
---
# <a name="garbage-collection-notifications"></a>Notifiche di Garbage Collection
In alcune situazioni un'operazione completa di Garbage Collection (cioè di generazione 2) eseguita da Common Language Runtime può influire negativamente sulle prestazioni. Questo può costituire un problema in particolare con i server che elaborano volumi elevati di richieste. in questo caso, un Garbage Collection lungo può causare un timeout della richiesta. Per evitare che si verifichi una raccolta completa durante un periodo critico, è possibile ricevere una notifica del raggiungimento di un Garbage Collection completo e quindi eseguire un'azione per reindirizzare il carico di lavoro a un'altra istanza del server. È anche possibile indurre manualmente una raccolta, a condizione che l'istanza del server corrente non sia necessaria per elaborare le richieste.  
  
 Il metodo <xref:System.GC.RegisterForFullGCNotification%2A> registra la generazione di una notifica quando il runtime rileva che sta per essere eseguita una Garbage Collection completa. Esistono due parti per questa notifica: quando sta per essere eseguita la Garbage Collection completa e quando la Garbage Collection completa è terminata.  
  
> [!WARNING]
> Le notifiche vengono generate solo in caso di blocco delle operazioni di Garbage Collection. Quando l' [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento di configurazione è abilitato, le operazioni di Garbage Collection in background non generano notifiche.  
  
 Per determinare quando è stata generata una notifica, usare i metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A>. Questi metodi vengono in genere usati in un ciclo `while` per ottenere continuamente un'enumerazione <xref:System.GCNotificationStatus> che indica lo stato della notifica. Se tale valore è <xref:System.GCNotificationStatus.Succeeded>, è possibile procedere nel modo seguente:  
  
- In risposta a una notifica ottenuta con il metodo <xref:System.GC.WaitForFullGCApproach%2A>, è possibile reindirizzare il carico di lavoro e probabilmente indurre manualmente una raccolta.  
  
- In risposta a una notifica ottenuta con il metodo <xref:System.GC.WaitForFullGCComplete%2A>, è possibile rendere l'istanza corrente del server disponibile per elaborare di nuovo le richieste. È anche possibile raccogliere informazioni. È ad esempio è possibile usare il metodo <xref:System.GC.CollectionCount%2A> per registrare il numero di raccolte.  
  
 I metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> sono progettati per interagire. L'uso di uno senza l'altro può produrre risultati imprevisti.  
  
## <a name="full-garbage-collection"></a>Garbage Collection completa  
 Il runtime genera una Garbage Collection completa quando si verifica uno degli scenari seguenti:  
  
- È stata promossa memoria sufficiente alla generazione 2 per generare la raccolta di generazione 2 successiva.  
  
- È stata promossa memoria sufficiente all'heap degli oggetti grandi per generare la raccolta di generazione 2 successiva.  
  
- Viene eseguita l'escalation di una raccolta di generazione 1 a una raccolta di generazione 2 a causa di altri fattori.  
  
 Le soglie specificate nel metodo <xref:System.GC.RegisterForFullGCNotification%2A> si applicano ai primi due scenari. Nel primo scenario, tuttavia, non si riceverà sempre la notifica nel periodo di tempo proporzionale ai valori della soglia specificati, per due motivi:  
  
- Il runtime non controlla ogni allocazione di oggetti piccoli (per motivi di prestazioni).  
  
- Sole le raccolte di generazione 1 promuovono la memoria alla generazione 2.  
  
 Nel terzo scenario è incerto anche quando si riceverà la notifica. Anche se non è una garanzia, è un modo utile per ridurre gli effetti di una Garbage Collection completa non opportuna reindirizzando le richieste durante questo intervallo di tempo o inducendo manualmente la raccolta quando può essere gestita meglio.  
  
## <a name="notification-threshold-parameters"></a>Parametri delle soglie di notifica  
 Il metodo <xref:System.GC.RegisterForFullGCNotification%2A> presenta due parametri per specificare i valori di soglia degli oggetti di generazione 2 e dell'heap degli oggetti grandi. Quando tali valori sono soddisfatti, verrà generata una notifica di Garbage Collection. Nella tabella seguente vengono descritti i parametri.  
  
|Parametro|Description|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Numero compreso tra 1 e 99 che specifica se la notifica deve essere generata in base agli oggetti promossi alla generazione 2.|  
|`largeObjectHeapThreshold`|Numero compreso tra 1 e 99 che specifica quando generare la notifica in base agli oggetti allocati nell'heap degli oggetti grandi.|  
  
 Se si specifica un valore troppo elevato, è molto probabile che si riceverà una notifica, ma il tempo di attesa prima che il runtime causi una raccolta potrebbe essere troppo lungo. Se si induce manualmente una raccolta, potrebbero essere recuperati più oggetti di quanti ne verrebbero recuperati se fosse il runtime a causare la raccolta.  
  
 Se si specifica un valore troppo basso, il runtime potrebbe causare la raccolta prima di aver avuto tempo sufficiente per ricevere la notifica.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente un gruppo di server gestisce le richieste Web in ingresso. Per simulare il carico di lavoro dell'elaborazione delle richieste, vengono aggiunte matrici di byte a una raccolta <xref:System.Collections.Generic.List%601>. Ogni server registra una notifica di Garbage Collection e quindi avvia un thread nel metodo utente `WaitForFullGCProc` per monitorare costantemente l'enumerazione <xref:System.GCNotificationStatus> restituita dai metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A>.  
  
 I metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> chiamano i rispettivi metodi utente di gestione eventi quando viene generata una notifica:  
  
- `OnFullGCApproachNotify`  
  
     Questo metodo chiama il metodo utente `RedirectRequests`, che indica al server di accodamento delle richieste di sospendere l'invio di richieste al server. Questa azione viene simulata impostando la variabile a livello di classe `bAllocate` su `false` in modo che non vengano allocati altri oggetti.  
  
     Viene quindi chiamato il metodo utente `FinishExistingRequests` per completare l'elaborazione delle richieste al server in sospeso. Questa azione viene simulata cancellando la raccolta <xref:System.Collections.Generic.List%601>.  
  
     Viene infine indotta una Garbage Collection perché il carico di lavoro è leggero.  
  
- `OnFullGCCompleteNotify`  
  
     Questo metodo chiama il metodo utente `AcceptRequests` per riprendere l'accettazione delle richieste perché il server non è più soggetto a una Garbage Collection completa. Questa azione viene simulata impostando la variabile `bAllocate` su `true` in modo che sia possibile riprendere l'aggiunta degli oggetti alla raccolta <xref:System.Collections.Generic.List%601>.  
  
 Il codice seguente contiene il metodo `Main` dell'esempio.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Il codice seguente contiene il metodo utente `WaitForFullGCProc`, che include un ciclo while continuo per cercare le notifiche di Garbage Collection.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Il codice seguente contiene il metodo `OnFullGCApproachNotify` chiamato dal  
  
 Metodo`WaitForFullGCProc` .  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Il codice seguente contiene il metodo `OnFullGCApproachComplete` chiamato dal  
  
 Metodo`WaitForFullGCProc` .  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Il codice seguente contiene i metodi utente chiamati dai metodi `OnFullGCApproachNotify` e `OnFullGCCompleteNotify`. I metodi utente reindirizzano le richieste, completano le richieste esistenti e quindi riprendono le richieste dopo che è stata eseguita una Garbage Collection completa.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 L'esempio di codice completo è il seguente:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Garbage Collection](index.md)
