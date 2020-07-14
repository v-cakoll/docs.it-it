---
title: Considerazioni sulla sicurezza e sui servizi remoti
description: Informazioni sulle considerazioni sulla sicurezza in relazione alla comunicazione remota, che consente di configurare chiamate trasparenti tra domini applicazione, processi o computer.
ms.date: 03/30/2017
helpviewer_keywords:
- code security, remoting
- remoting, security
- security [.NET Framework], remoting
- secure coding, remoting
ms.assetid: 125d2ab8-55a4-4e5f-af36-a7d401a37ab0
ms.openlocfilehash: 029f9863ebed94805675b629be7eb10963a7b689
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281394"
---
# <a name="security-and-remoting-considerations"></a>Considerazioni sulla sicurezza e sui servizi remoti
I servizi remoti consentono di impostare chiamate trasparenti tra domini applicazione, processi o computer. Lo stack di sicurezza per l'accesso di codice, tuttavia, non può superare i limiti del processo o del computer (viene applicato tra domini applicazione dello stesso processo).  
  
 Tutte le classi utilizzabili in remoto (derivate da una classe <xref:System.MarshalByRefObject>) devono assumersi la responsabilità della sicurezza. Il codice deve essere usato solo in ambienti chiusi in cui il codice chiamante può essere considerato attendibile in modo implicito oppure le chiamate remote devono essere progettate in modo da non esporre il codice protetto a immissioni esterne che potrebbero essere usate da utenti malintenzionati.  
  
 In genere, è consigliabile non esporre mai metodi, proprietà o eventi protetti da [LinkDemand](link-demands.md) dichiarativo e <xref:System.Security.Permissions.SecurityAction.InheritanceDemand> controlli di sicurezza. Con i servizi remoti, questi controlli non vengono applicati. Altri controlli di sicurezza, ad esempio <xref:System.Security.Permissions.SecurityAction.Demand> , [Assert](using-the-assert-method.md)e così via, funzionano tra i domini dell'applicazione all'interno di un processo, ma non funzionano negli scenari tra processi o tra computer.  
  
## <a name="protected-objects"></a>Oggetti protetti  
 Alcuni oggetti includono internamente lo stato di sicurezza. Questi oggetti non devono essere passati a codice non attendibile, che potrebbe acquisire autorizzazioni di sicurezza più elevate delle proprie.  
  
 Un esempio riguarda la creazione di un oggetto <xref:System.IO.FileStream>. <xref:System.Security.Permissions.FileIOPermission> viene richiesto al momento della creazione e, se riesce, viene restituito l'oggetto file. Tuttavia, se il riferimento all'oggetto viene passato al codice senza le autorizzazioni del file, l'oggetto sarà in grado di leggere e scrivere nel file specificato.  
  
 La difesa più semplice per questo tipo di oggetto è richiedere lo stesso **FileIOPermission** di qualsiasi codice che cerca di ottenere il riferimento all'oggetto tramite un elemento API pubblico.  
  
## <a name="application-domain-crossing-issues"></a>Problemi relativi a diversi domini applicazioni  
 Per isolare il codice in ambienti host gestiti, di solito si generano più domini applicazione figlio con criteri espliciti che consentono di ridurre i livelli di autorizzazione per i vari assembly. Tuttavia, i criteri per questi assembly rimangono invariati nel dominio applicazione predefinito. Se uno dei domini applicazione figlio riesce a forzare il dominio applicazione predefinito per caricare un assembly, l'effetto dell'isolamento del codice si perde e i tipi nell'assembly caricato forzatamente potranno eseguire il codice con un livello di attendibilità superiore.  
  
 Un dominio applicazione può forzare un altro dominio applicazione per caricare un assembly ed eseguire il codice contenuto chiamando un proxy in un oggetto ospitato nell’altro dominio applicazione. Per ottenere un proxy tra domini applicazione, il dominio applicazione che ospita l'oggetto deve distribuirne uno tramite un parametro di chiamata al metodo o un valore restituito. Oppure, se il dominio applicazione è stato appena creato, l'autore dispone di un proxy per l’oggetto <xref:System.AppDomain> per impostazione predefinita. Pertanto, per evitare di interrompere l'isolamento del codice, un dominio applicazione con un livello di attendibilità superiore non deve distribuire i riferimenti agli oggetti con marshalling per riferimento (istanze di classi derivate da <xref:System.MarshalByRefObject>) del proprio dominio ai domini applicazione con livelli di attendibilità inferiori.  
  
 In genere, il dominio applicazione predefinito crea domini applicazione figlio con un oggetto controllo in ognuno di essi. L'oggetto controllo gestisce il nuovo dominio applicazione e occasionalmente accetta gli ordini dal dominio applicazione predefinito, ma non è in grado di contattare direttamente il dominio. A volte il dominio applicazione predefinito chiama il proxy per l'oggetto controllo. Tuttavia, in alcuni casi l'oggetto controllo deve richiamare il dominio applicazione predefinito. In questi casi, il dominio applicazione predefinito passa un oggetto callback di marshalling per riferimento al costruttore dell'oggetto controllo. È responsabilità dell'oggetto controllo proteggere il proxy. Se l'oggetto controllo posiziona il proxy in un campo statico pubblico di una classe pubblica o espone pubblicamente il proxy, può attivarsi un pericoloso meccanismo che consente a un codice di richiamare il dominio applicazione predefinito. Per questo motivo, gli oggetti controllo vengono sempre considerati implicitamente attendibili per mantenere privato il proxy.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
