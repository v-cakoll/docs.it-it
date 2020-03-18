---
title: EventWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
ms.openlocfilehash: 80c90254978495a58d228c4302eda84d6165c800
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138080"
---
# <a name="eventwaithandle"></a>EventWaitHandle
La classe <xref:System.Threading.EventWaitHandle> consente la comunicazione tra i thread inviando e attendendo i segnali. Gli handle di attesa degli eventi (detti anche semplicemente eventi) sono handle di attesa che possono essere segnalati per rilasciare uno o più thread in attesa. Un handle di attesa di un evento, dopo essere stato segnalato, viene reimpostato manualmente o automaticamente. La classe <xref:System.Threading.EventWaitHandle> può rappresentare un handle di attesa di un evento locale (evento locale) o un handle di attesa di un evento di sistema denominato (evento denominato o evento di sistema, visibile a tutti i processi).  
  
> [!NOTE]
> Gli handle di attesa evento non sono [eventi](../events/index.md) .NET. Non sono coinvolti delegati o gestori eventi. Si usa la parola "evento" per descriverli perché sono sempre stati indicati come eventi del sistema operativo e perché l'azione di segnalare l'handle di attesa indica ai thread in attesa che si è verificato un evento.  
  
 Sia gli handle di attesa degli eventi locali che quelli denominati usano oggetti di sincronizzazione del sistema, protetti da wrapper <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> per assicurare che le risorse vengano rilasciate. È possibile usare il metodo <xref:System.Threading.WaitHandle.Dispose%2A> per liberare le risorse immediatamente dopo aver finito di usare l'oggetto.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>Handle di attesa degli eventi reimpostati automaticamente  
 Per creare un evento di reimpostazione automatica, specificare <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> quando si crea l'oggetto <xref:System.Threading.EventWaitHandle>. Come indica il nome, questo evento di sincronizzazione viene reimpostato automaticamente quando viene segnalato, dopo avere rilasciato un singolo thread in attesa. Per segnalare l'evento, chiamare il metodo <xref:System.Threading.EventWaitHandle.Set%2A>.  
  
 Gli eventi di reimpostazione automatica vengono in genere usati per fornire l'accesso esclusivo a una risorsa per un singolo thread per volta. Un thread richiede la risorsa chiamando il metodo <xref:System.Threading.WaitHandle.WaitOne%2A>. Se nessun altro thread contiene l'handle di attesa, il metodo restituisce `true` e il thread chiamante ha il controllo della risorsa.  
  
> [!IMPORTANT]
> Come per tutti i meccanismi di sincronizzazione, è necessario assicurarsi che tutti i percorsi del codice attendano l'handle di attesa appropriato prima di accedere a una risorsa protetta. La sincronizzazione dei thread è cooperativa.  
  
 Se un evento di reimpostazione automatica viene segnalato quando nessun thread è in attesa, rimane segnalato finché un thread non prova ad attenderlo. L'evento rilascia il thread e viene immediatamente reimpostato, bloccando i thread successivi.  
  
## <a name="event-wait-handles-that-reset-manually"></a>Handle di attesa degli eventi reimpostati manualmente  
 Per creare un evento di reimpostazione manuale, specificare <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> quando si crea l'oggetto <xref:System.Threading.EventWaitHandle>. Come indica il nome, questo evento di sincronizzazione deve essere reimpostato manualmente dopo essere stato segnalato. Finché non viene reimpostato, chiamando il metodo <xref:System.Threading.EventWaitHandle.Reset%2A>, i thread in attesa dell'handle dell'evento procedono immediatamente senza bloccarsi.  
  
 Un evento di reimpostazione manuale è paragonabile al cancello di un recinto. Quando l'evento non viene segnalato, i thread che lo attendono vengono bloccati, come cavalli in un recinto. Quando l'evento viene segnalato, chiamando il metodo <xref:System.Threading.EventWaitHandle.Set%2A>, tutti i thread in attesa possono procedere. L'evento rimane segnalato finché non viene chiamato il metodo <xref:System.Threading.EventWaitHandle.Reset%2A>. L'evento di reimpostazione manuale risulta quindi un modo ideale per bloccare i thread che devono attendere finché un thread non termina un'attività.  
  
 Come quando i cavalli escono da un recinto, la pianificazione, tramite il sistema operativo, dei thread rilasciati e la ripresa dell'esecuzione richiedono tempo. Se il metodo <xref:System.Threading.EventWaitHandle.Reset%2A> viene chiamato prima che tutti i thread abbiano ripreso l'esecuzione, i thread rimanenti vengono bloccati ancora una volta. Quali thread riprendono e quali si bloccano dipende da fattori casuali, ad esempio il carico sul sistema, il numero di thread in attesa dell'utilità di pianificazione e così via. Ciò non rappresenta un problema se il thread che segnala l'evento termina dopo la segnalazione, che è il modello di utilizzo più comune. Se si vuole che il thread che ha segnalato l'evento inizi una nuova attività dopo che tutti i thread in attesa sono stati ripresi, è necessario bloccarlo finché tutti i thread in attesa non sono stati ripresi. In caso contrario, si verifica una race condition e il comportamento del codice non è prevedibile.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>Funzionalità comuni a eventi automatici e manuali  
 Uno o più thread vengono in genere bloccati su una classe <xref:System.Threading.EventWaitHandle> finché un thread non bloccato non chiama il metodo <xref:System.Threading.EventWaitHandle.Set%2A>, che rilascia uno dei thread in attesa (in caso di eventi di reimpostazione automatica) oppure tutti (in caso di eventi di reimpostazione manuale). Un thread può segnalare una classe <xref:System.Threading.EventWaitHandle> e quindi venire bloccato, come un'operazione atomica, chiamando il metodo statico <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType>.  
  
 Gli oggetti <xref:System.Threading.EventWaitHandle> possono essere usati con i metodi statici <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> e <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>. Poiché le classi <xref:System.Threading.EventWaitHandle> e <xref:System.Threading.Mutex> derivano entrambe da <xref:System.Threading.WaitHandle>, è possibile usare entrambe le classi con questi metodi.  
  
### <a name="named-events"></a>Eventi denominati  
 Il sistema operativo Windows consente di assegnare nomi agli handle di attesa degli eventi. Un evento denominato è a livello di sistema, vale a dire che, dopo essere stato creato, l'evento denominato è visibile a tutti i thread in tutti i processi. In questo modo, gli eventi denominati possono essere usati per sincronizzare le attività di processi e thread.  
  
 È possibile creare un oggetto <xref:System.Threading.EventWaitHandle> che rappresenta un evento di sistema denominato usando uno dei costruttori che specifica un nome di evento.  
  
> [!NOTE]
> Poiché gli eventi denominati sono a livello di sistema, è possibile avere più oggetti <xref:System.Threading.EventWaitHandle> che rappresentano lo stesso evento denominato. A ogni chiamata a un costruttore o al metodo <xref:System.Threading.EventWaitHandle.OpenExisting%2A> viene creato un nuovo oggetto <xref:System.Threading.EventWaitHandle>. Specificando lo stesso nome ripetutamente verranno creati più oggetti che rappresentano lo stesso evento denominato.  
  
 È consigliabile prestare attenzione nell'uso degli eventi denominati. Poiché sono a livello di sistema, un altro processo che usa lo stesso nome può bloccare i thread in modo imprevisto. Il malware in esecuzione sullo stesso computer potrebbe sfruttare questa opportunità per un attacco Denial of Service.  
  
 Usare il controllo di accesso per proteggere un oggetto <xref:System.Threading.EventWaitHandle> che rappresenta un evento denominato, preferibilmente usando un costruttore che specifichi un oggetto <xref:System.Security.AccessControl.EventWaitHandleSecurity>. È anche possibile applicare la sicurezza del controllo di accesso usando il metodo <xref:System.Threading.EventWaitHandle.SetAccessControl%2A>, ma in tal modo verrà creata una finestra di vulnerabilità tra l'ora di creazione dell'handle di attesa degli eventi e l'ora in cui viene protetto. La protezione degli eventi con la sicurezza del controllo di accesso aiuta a impedire gli attacchi dannosi, ma non risolve il problema dei conflitti di nomi non intenzionali.  
  
> [!NOTE]
> Diversamente dalla classe <xref:System.Threading.EventWaitHandle>, le classi derivate <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.ManualResetEvent> possono rappresentare solo handle di attesa locali. Non possono rappresentare gli eventi di sistema denominati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.EventWaitHandle>
- <xref:System.Threading.WaitHandle>
- <xref:System.Threading.AutoResetEvent>
- <xref:System.Threading.ManualResetEvent>
