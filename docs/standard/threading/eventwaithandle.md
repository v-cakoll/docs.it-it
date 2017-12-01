---
title: EventWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bd248133bd95ff05246eb36a8e250247fd7ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle"></a>EventWaitHandle
La <xref:System.Threading.EventWaitHandle> classe consente ai thread di comunicare tra loro tramite segnalazioni e attendendo segnali. Handle di attesa di eventi (nota anche semplicemente come eventi) sono handle di attesa che possono essere segnalati per rilasciare una o più thread in attesa. Dopo essere stato segnalato, un handle di attesa dell'evento viene reimpostato automaticamente o manualmente. La <xref:System.Threading.EventWaitHandle> classe può rappresentare un handle a attesa evento locale (evento locale) o handle (denominato evento o sistema, visibili a tutti i processi) di attesa di un evento di sistema denominato.  
  
> [!NOTE]
>  Handle di attesa eventi non sono gli eventi in quanto in genere indicata con tale parola in .NET Framework. Non è coinvolto Nessun delegati o gestori di eventi. L'evento"word" viene utilizzato per descrivere le poiché essi passato sono stati definiti per come eventi di sistema operativo e l'azione di segnalazione dell'handle di attesa indica al thread in attesa che si è verificato un evento.  
  
 Entrambi gli handle di attesa dell'evento locale che denominato utilizzano oggetti di sincronizzazione del sistema, che sono protetti da <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> wrapper per garantire che le risorse vengono rilasciate. È possibile utilizzare il <xref:System.Threading.WaitHandle.Dispose%2A> metodo per liberare le risorse quando è terminato di utilizzare l'oggetto.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>Handle di attesa di eventi di reimpostazione automatica  
 Per creare un evento di reimpostazione automatica specificando <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> quando si crea il <xref:System.Threading.EventWaitHandle> oggetto. Come suggerisce il nome, questo evento di sincronizzazione viene reimpostato automaticamente quando viene segnalato, dopo il rilascio di un singolo thread in attesa. Segnalare l'evento chiamando il relativo <xref:System.Threading.EventWaitHandle.Set%2A> metodo.  
  
 Eventi di reimpostazione automatica vengono in genere utilizzati per fornire l'accesso esclusivo a una risorsa per un solo thread alla volta. Un thread richiede la risorsa chiamando il <xref:System.Threading.WaitHandle.WaitOne%2A> metodo. Se nessun altro thread contiene l'handle di attesa, il metodo restituisce `true` e il thread chiamante ha il controllo della risorsa.  
  
> [!IMPORTANT]
>  Come con tutti i meccanismi di sincronizzazione, è necessario assicurarsi che tutti i percorsi del codice in attesa dell'handle di attesa appropriato prima di accedere a una risorsa protetta. La sincronizzazione dei thread è cooperativa.  
  
 Se un evento di reimpostazione automatica viene segnalato quando nessun thread è in attesa, rimane segnalato fino un thread in attesa. L'evento rilascia il thread e viene reimpostato immediatamente bloccando i thread successivi.  
  
## <a name="event-wait-handles-that-reset-manually"></a>Handle di attesa evento reimpostato manualmente  
 Per creare un evento di reimpostazione manuale specificando <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> quando si crea il <xref:System.Threading.EventWaitHandle> oggetto. Come suggerisce il nome, questo evento di sincronizzazione deve essere reimpostato manualmente dopo che è stato segnalato. Finché viene reimpostata, chiamando il relativo <xref:System.Threading.EventWaitHandle.Reset%2A> (metodo), i thread in attesa dell'handle di evento procedono immediatamente senza bloccare.  
  
 Un reimpostazione manuale evento funziona come il controllo di un recinto. Quando l'evento non viene segnalato, bloccano i thread in attesa su di esso, come cavalli in un recinto. Quando l'evento viene segnalato, chiamando il relativo <xref:System.Threading.EventWaitHandle.Set%2A> (metodo), tutti i thread in attesa sono disponibili per continuare. L'evento rimane segnalato fino a quando il relativo <xref:System.Threading.EventWaitHandle.Reset%2A> metodo viene chiamato. In questo modo l'evento di reimpostazione manuale di una soluzione ideale per contenere i thread che è necessario attendere fino a quando un thread termina un'attività.  
  
 Ad esempio horse lasciando un recinto, il tempo è per i thread rilasciati per la pianificazione dal sistema operativo e per riprendere l'esecuzione. Se il <xref:System.Threading.EventWaitHandle.Reset%2A> metodo viene chiamato prima di ripresa dell'esecuzione di tutti i thread, thread rimanenti si bloccano di nuovo. Quali ripresa di thread e il blocco del thread dipende casuale fattori quali il carico sul sistema, il numero di thread in attesa per l'utilità di pianificazione e così via. Questo non costituisce un problema se il thread che segnala l'evento termina dopo la segnalazione, ovvero il modello di utilizzo più comune. Se si desidera il thread che ha segnalato l'evento per avviare una nuova attività dopo che tutti in attesa di ripresa thread, è necessario bloccare fino a quando tutti i thread in attesa ripresa. In caso contrario, si dispone di una race condition e il comportamento del codice è imprevedibile.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>Funzionalità comuni a eventi automatici e manuali  
 In genere, uno o più thread bloccati in un <xref:System.Threading.EventWaitHandle> fino a quando un thread sbloccato chiama il <xref:System.Threading.EventWaitHandle.Set%2A> metodo, che rilascia uno dei thread in attesa (in caso di eventi di reimpostazione automatica) o tutti i parametri (reimpostazione manuale eventi). Un thread può segnalare un <xref:System.Threading.EventWaitHandle> e quindi bloccare su di esso, come operazione atomica, chiamando il metodo statico <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType> metodo.  
  
 <xref:System.Threading.EventWaitHandle>oggetti possono essere utilizzati con il metodo statico <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> e <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> metodi. Poiché il <xref:System.Threading.EventWaitHandle> e <xref:System.Threading.Mutex> derivano entrambe da <xref:System.Threading.WaitHandle>, è possibile utilizzare entrambe le classi con questi metodi.  
  
### <a name="named-events"></a>Eventi denominati  
 Il sistema operativo Windows consente gli handle di attesa evento dispongano di nomi. Un evento denominato è a livello di sistema. Vale a dire, una volta creato l'evento, è visibile a tutti i thread in tutti i processi. Di conseguenza, gli eventi denominati consente di sincronizzare le attività di processi e thread.  
  
 È possibile creare un <xref:System.Threading.EventWaitHandle> oggetto che rappresenta un evento di sistema denominato usando uno dei costruttori che specifica un nome di evento.  
  
> [!NOTE]
>  Poiché gli eventi denominati sono a livello di sistema, è possibile avere più <xref:System.Threading.EventWaitHandle> gli oggetti che rappresentano lo stesso evento denominato. Ogni volta che si chiama un costruttore, o <xref:System.Threading.EventWaitHandle.OpenExisting%2A> (metodo), un nuovo <xref:System.Threading.EventWaitHandle> viene creato l'oggetto. Specificando lo stesso nome ripetutamente crea più oggetti che rappresentano lo stesso evento denominato.  
  
 È consigliabile prestare attenzione nell'utilizzo degli eventi denominati. Poiché sono a livello di sistema, un altro processo che utilizza lo stesso nome può bloccare i thread in modo imprevisto. Il malware in esecuzione sullo stesso computer potrebbe sfruttare questa opportunità per un attacco Denial of Service.  
  
 Utilizzare la sicurezza del controllo di accesso per proteggere un <xref:System.Threading.EventWaitHandle> oggetto che rappresenta un evento denominato, preferibilmente usando un costruttore che specifica un <xref:System.Security.AccessControl.EventWaitHandleSecurity> oggetto. È inoltre possibile applicare una sicurezza utilizzando il <xref:System.Threading.EventWaitHandle.SetAccessControl%2A> (metodo), ma in tal modo una finestra di vulnerabilità tra l'ora in cui viene creato l'handle di attesa evento e l'ora è protetto. Eventi con il controllo di accesso sicurezza impedisce gli attacchi dannosi, ma non risolve il problema dei conflitti di nomi non intenzionali.  
  
> [!NOTE]
>  A differenza di <xref:System.Threading.EventWaitHandle> (classe), le classi derivate <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.ManualResetEvent> possa rappresentare solo handle di attesa. Non possono rappresentare gli eventi di sistema denominato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
