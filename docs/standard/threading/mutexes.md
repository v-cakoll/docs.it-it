---
title: Mutex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a>Mutex
È possibile utilizzare un <xref:System.Threading.Mutex> oggetto per fornire l'accesso esclusivo a una risorsa. Il <xref:System.Threading.Mutex> classe utilizza più risorse di sistema rispetto alla <xref:System.Threading.Monitor> classe, ma può essere sottoposto a marshalling attraverso i limiti del dominio applicazione, può essere utilizzato con più attese e può essere utilizzato per sincronizzare i thread in processi diversi. Per un confronto dei meccanismi di sincronizzazione gestiti, vedere [Panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Per esempi di codice, vedere la documentazione di riferimento per il <xref:System.Threading.Mutex.%23ctor%2A> costruttori.  
  
## <a name="using-mutexes"></a>Uso dei mutex  
 Un thread chiama il <xref:System.Threading.WaitHandle.WaitOne%2A> metodo di un mutex per richiedere la proprietà. La chiamata viene bloccata finché il mutex non è disponibile o fino a quando l'intervallo di timeout facoltativo scade. Lo stato di un mutex viene segnalato se nessun thread lo possiede.  
  
 Un thread rilascia un mutex chiamando il relativo <xref:System.Threading.Mutex.ReleaseMutex%2A> metodo. I mutex presentano affinità di thread; vale a dire il mutex può essere rilasciato solo dal thread che ne è proprietario. Se un thread rilascia un mutex non è proprietario, un <xref:System.ApplicationException> viene generata nel thread.  
  
 Poiché il <xref:System.Threading.Mutex> deriva dalla classe <xref:System.Threading.WaitHandle>, è inoltre possibile chiamare il metodo statico <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> metodi di <xref:System.Threading.WaitHandle> che richiede la proprietà di un <xref:System.Threading.Mutex> in combinazione con altri handle di attesa.  
  
 Se il proprietario di un thread un <xref:System.Threading.Mutex>, che può specificare lo stesso thread <xref:System.Threading.Mutex> nelle chiamate ripetute di attesa richiesta senza interrompere l'esecuzione; tuttavia, è necessario rilasciare il <xref:System.Threading.Mutex> tante volte per rilasciare la proprietà.  
  
## <a name="abandoned-mutexes"></a>Mutex abbandonati  
 Se un thread termina senza rilasciare un <xref:System.Threading.Mutex>, viene definito il mutex abbandonato. Ciò indica spesso un grave errore di programmazione perché la risorsa protetta dal mutex può essere lasciata in uno stato incoerente. In .NET Framework versione 2.0, un <xref:System.Threading.AbandonedMutexException> viene generata nel thread successivo che acquisisce il mutex.  
  
> [!NOTE]
>  In .NET Framework versioni 1.0 e 1.1, un abbandonato <xref:System.Threading.Mutex> è impostato sullo stato segnalato e la successiva in attesa del thread ottiene la proprietà. Se nessun thread è in attesa, il <xref:System.Threading.Mutex> rimane in stato segnalato. Non viene generata alcuna eccezione.  
  
 Nel caso di un mutex di sistema, un mutex abbandonato potrebbe indicare che un'applicazione è stata terminata in modo anomalo (ad esempio, usando Gestione attività Windows).  
  
## <a name="local-and-system-mutexes"></a>Mutex locali e di sistema  
 Sono disponibili due tipi di mutex: i mutex locali e quelli denominati mutex di sistema. Se si crea un <xref:System.Threading.Mutex> utilizzando un costruttore che accetta un nome, dell'oggetto è associato a un oggetto di sistema operativo di tale nome. I mutex denominati di sistema sono visibili in tutto il sistema operativo e possono essere usati per sincronizzare le attività dei processi. È possibile creare più <xref:System.Threading.Mutex> gli oggetti che rappresentano lo stesso mutex di sistema denominato ed è possibile utilizzare il <xref:System.Threading.Mutex.OpenExisting%2A> mutex di sistema denominato metodo per aprire un oggetto esistente.  
  
 Un mutex locale esiste solo all'interno del processo. E può essere utilizzato da qualsiasi thread del processo che ha un riferimento locale <xref:System.Threading.Mutex> oggetto. Ogni <xref:System.Threading.Mutex> oggetto è un mutex locale distinto.  
  
### <a name="access-control-security-for-system-mutexes"></a>Sicurezza del controllo di accesso per i Mutex di sistema  
 La versione .NET Framework 2.0 offre la possibilità di eseguire query e impostare la sicurezza del controllo di accesso di Windows per gli oggetti denominati di sistema. Si consiglia la protezione dei mutex di sistema dal momento della creazione perché gli oggetti di sistema sono globali e pertanto possono essere bloccati da un codice diverso dal proprio.  
  
 Per informazioni sulla sicurezza di controllo di accesso per i mutex, vedere il <xref:System.Security.AccessControl.MutexSecurity> e <xref:System.Security.AccessControl.MutexAccessRule> classi, il <xref:System.Security.AccessControl.MutexRights> enumerazione, il <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A>, e <xref:System.Threading.Mutex.OpenExisting%2A> metodi del <xref:System.Threading.Mutex> classe e il <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> costruttore.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Monitoraggi](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 [Thread e Threading](../../../docs/standard/threading/threads-and-threading.md)
