---
title: Mutex
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
ms.openlocfilehash: 874f879697db0b47c73626350eeb05a01b38e1bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127561"
---
# <a name="mutexes"></a>Mutex
È possibile usare un oggetto <xref:System.Threading.Mutex> per fornire l'accesso esclusivo a una risorsa. La classe <xref:System.Threading.Mutex> usa più risorse di sistema della classe <xref:System.Threading.Monitor>, ma è possibile eseguirne il marshalling fra i limiti del dominio dell'applicazione, può essere usata con più condizioni di attesa e può essere usata per sincronizzare i thread in processi diversi. Per un confronto dei meccanismi di sincronizzazione gestiti, vedere [Panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Per esempi di codice, vedere la documentazione di riferimento per i costruttori <xref:System.Threading.Mutex.%23ctor%2A>.  
  
## <a name="using-mutexes"></a>Uso dei mutex  
 Un thread chiama il metodo <xref:System.Threading.WaitHandle.WaitOne%2A> di un mutex per richiedere la proprietà. La chiamata viene bloccata finché il mutex non è disponibile o fino a quando l'intervallo di timeout facoltativo scade. Lo stato di un mutex viene segnalato se nessun thread lo possiede.  
  
 Un thread rilascia un mutex chiamando il relativo metodo <xref:System.Threading.Mutex.ReleaseMutex%2A>. I mutex presentano affinità di thread; vale a dire il mutex può essere rilasciato solo dal thread che ne è proprietario. Se un thread rilascia un mutex di cui non è proprietario, nel thread viene generata una <xref:System.ApplicationException>.  
  
 Poiché la classe <xref:System.Threading.Mutex> deriva da <xref:System.Threading.WaitHandle>, è anche possibile chiamare i metodi statici <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> di <xref:System.Threading.WaitHandle> per richiedere la proprietà di un <xref:System.Threading.Mutex> in combinazione con altri handle di attesa.  
  
 Se un thread è proprietario di un <xref:System.Threading.Mutex>, quel thread può specificare lo stesso <xref:System.Threading.Mutex> nelle chiamate di richiesta di attesa ripetute senza interromperne l'esecuzione. Tuttavia, deve rilasciare ogni volta il <xref:System.Threading.Mutex> per rilasciare la proprietà.  
  
## <a name="abandoned-mutexes"></a>Mutex abbandonati  
 Se un thread termina senza rilasciare un <xref:System.Threading.Mutex>, quest'ultimo si definisce abbandonato. Ciò indica spesso un grave errore di programmazione perché la risorsa protetta dal mutex può essere lasciata in uno stato incoerente. Nella versione .NET Framework 2.0 viene generata una <xref:System.Threading.AbandonedMutexException> nel thread successivo che acquisisce il mutex.  
  
> [!NOTE]
> Nelle versioni .NET Framework 1.0 e 1.1 un <xref:System.Threading.Mutex> abbandonato è impostato sullo stato segnalato e il thread in attesa successivo ottiene la proprietà. Se non c'è nessun thread in attesa, il <xref:System.Threading.Mutex> rimane in uno stato segnalato. Non viene generata alcuna eccezione.  
  
 Nel caso di un mutex di sistema, un mutex abbandonato potrebbe indicare che un'applicazione è stata terminata in modo anomalo (ad esempio, usando Gestione attività Windows).  
  
## <a name="local-and-system-mutexes"></a>Mutex locali e di sistema  
 Sono disponibili due tipi di mutex: i mutex locali e quelli denominati mutex di sistema. Se si crea un oggetto <xref:System.Threading.Mutex> usando un costruttore che accetta un nome, è associato a un oggetto del sistema operativo di tale nome. I mutex denominati di sistema sono visibili in tutto il sistema operativo e possono essere usati per sincronizzare le attività dei processi. È possibile creare più oggetti <xref:System.Threading.Mutex> che rappresentano lo stesso mutex di sistema denominato ed è possibile usare il metodo <xref:System.Threading.Mutex.OpenExisting%2A> per aprire un mutex di sistema denominato esistente.  
  
 Un mutex locale esiste solo all'interno del processo. Può essere usato da qualsiasi thread nel processo che abbia un riferimento all'oggetto <xref:System.Threading.Mutex> locale. Ogni oggetto <xref:System.Threading.Mutex> è un mutex locale distinto.  
  
### <a name="access-control-security-for-system-mutexes"></a>Sicurezza del controllo di accesso per i Mutex di sistema  
 La versione .NET Framework 2.0 offre la possibilità di eseguire query e impostare la sicurezza del controllo di accesso di Windows per gli oggetti denominati di sistema. Si consiglia la protezione dei mutex di sistema dal momento della creazione perché gli oggetti di sistema sono globali e pertanto possono essere bloccati da un codice diverso dal proprio.  
  
 Per informazioni sulla sicurezza del controllo di accesso per i mutex, vedere le classi <xref:System.Security.AccessControl.MutexSecurity> e <xref:System.Security.AccessControl.MutexAccessRule>, l'enumerazione <xref:System.Security.AccessControl.MutexRights>, i metodi <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A> e <xref:System.Threading.Mutex.OpenExisting%2A> della classe <xref:System.Threading.Mutex> e il costruttore <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Mutex?displayProperty=nameWithType>
- <xref:System.Threading.Mutex.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.MutexSecurity?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.MutexAccessRule?displayProperty=nameWithType>
- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- [Oggetti e funzionalità del threading](threading-objects-and-features.md)
- [Thread e threading](threads-and-threading.md)
- [Threading](index.md)
