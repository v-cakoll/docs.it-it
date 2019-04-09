---
title: Eventi ETW di CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb7520518497b244be8be3751ca8a3063a02717a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135863"
---
# <a name="clr-etw-events"></a>Eventi ETW di CLR
Gli argomenti presenti in questa sezione descrivono gli eventi ETW (Event Tracing for Windows). A ogni evento sono associati una parola chiave e un livello, come descritto nell'argomento [Parole chiave e livelli ETW di CLR](../../../docs/framework/performance/clr-etw-keywords-and-levels.md). CLR dispone di due provider per gli eventi:  
  
-   Il provider di runtime, che genera eventi in base alle parole chiave (categorie di eventi) abilitate. Il GUID del provider di runtime di CLR è e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.  
  
-   Il provider di rundown, che viene usato per scopi specifici. Il GUID del provider di rundown di CLR è a669021c-c450-4609-a035-5af59af4df18.  
  
 Per altre informazioni, vedere [Provider ETW di CLR](../../../docs/framework/performance/clr-etw-providers.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Eventi di informazione di runtime](../../../docs/framework/performance/runtime-information-etw-events.md)  
 Acquisisce informazioni sul runtime, inclusi la SKU, il numero di versione, la modalità di attivazione del runtime, i parametri della riga di comando con i quali è stato avviato, il GUID (se applicabile) e altre informazioni pertinenti.  
  
 [Evento di eccezione generata_V1](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 Acquisisce informazioni sulle eccezioni generate.  
  
 [Eventi di conflitto](../../../docs/framework/performance/contention-etw-events.md)  
 Acquisisce informazioni sui conflitti per i blocchi di monitoraggio o nativi usati dal runtime.  
  
 [Eventi del pool di thread](../../../docs/framework/performance/thread-pool-etw-events.md)  
 Acquisisce informazioni sui pool dei thread di lavoro e di I/O.  
  
 [Eventi del caricatore](../../../docs/framework/performance/loader-etw-events.md)  
 Acquisisce informazioni sul caricamento e sullo scaricamento di moduli, assembly e domini applicazione.  
  
 [Eventi dei metodi](../../../docs/framework/performance/method-etw-events.md)  
 Acquisisce informazioni sui metodi di CLR per la risoluzione dei simboli.  
  
 [Eventi di Garbage Collection](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 Acquisisce informazioni che riguardano la procedura di Garbage Collection, utili nella diagnostica e nel debug.  
  
 [Eventi di traccia JIT](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 Acquisisce informazioni sull'incorporamento Just-In-Time (JIT) e sulle chiamate tail.  
  
 [Eventi di interoperabilità](../../../docs/framework/performance/interop-etw-events.md)  
 Acquisisce informazioni sulla memorizzazione nella cache e sulla generazione di stub Microsoft Intermediate Language (MSIL).  
  
 [Eventi ARM](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 Acquisisce informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.  
  
 [Eventi di sicurezza](../../../docs/framework/performance/security-etw-events.md)  
 Acquisisce informazioni sulla verifica tramite nome sicuro e Authenticode.  
  
 [Evento di stack](../../../docs/framework/performance/stack-etw-event.md)  
 Acquisisce informazioni che vengono usate con altri eventi per generare le analisi dello stack in seguito alla generazione di un evento.  
  
## <a name="see-also"></a>Vedere anche

- [Migliorare il debug e ottimizzazione delle prestazioni con ETW](https://go.microsoft.com/fwlink/?LinkId=179696)
- [Blog sulle prestazioni di Windows](https://go.microsoft.com/fwlink/?LinkId=179509)
- [Controllo della registrazione di .NET Framework](../../../docs/framework/performance/controlling-logging.md)
- [Provider ETW di CLR](../../../docs/framework/performance/clr-etw-providers.md)
- [Parole chiave e livelli ETW di CLR](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [Eventi ETW in Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
