---
title: Criteri di cache basati sulla posizione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Cache If Available policy
- reload policy
- location-based cache policies
- Cache Only policy
- local cache
- intermediate cache
- No Cache No Store policy
- cache [.NET Framework], location-based policies
- Revalidate policy
- freshness of cached resources
- Cache Or Next Cache Only policy
- Refresh policy
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
caps.latest.revision: 12
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a5b4bf67db3fcbb70d2a93f35976d8d9b4b3a028
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="location-based-cache-policies"></a>Criteri di cache basati sulla posizione
I criteri di cache basati sulla posizione definiscono l'aggiornamento delle voci memorizzate nella cache valide in base alla posizione da cui è possibile ricavare la risorsa richiesta. Una risorsa memorizzata nella cache è valida se l'uso non viola i requisiti di riconvalida specificati dal server. I criteri di cache basati sulla posizione vengono creati a livello di codice usando un costruttore di classe <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>. Il tipo dei criteri basati sulla posizione viene passato al costruttore usando un valore di enumerazione <xref:System.Net.Cache.RequestCacheLevel> o <xref:System.Net.Cache.HttpRequestCacheLevel>. Per esempi di codice che creano criteri di cache basati sulla posizione, vedere [Procedura: Impostare criteri di cache basati sulla posizione per un'applicazione](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md). Le sezioni seguenti illustrano i diversi tipi di criteri di cache basati sulla posizione per le risorse Hypertext Transfer Protocol (HTTP e HTTPS).  
  
## <a name="cache-if-available-policy"></a>CacheIfAvailable (criterio)  
 Se una risorsa richiesta valida è nella cache locale, viene usata la risorsa memorizzata nella cache. In caso contrario, la richiesta per la risorsa viene inviata al server. Se la risorsa richiesta è disponibile in qualsiasi cache tra il client e il server, la richiesta può essere soddisfatta da una cache intermedia.  
  
## <a name="cache-only-policy"></a>CacheOnly (criterio)  
 Se una risorsa richiesta valida è nella cache locale, viene usata la risorsa memorizzata nella cache. Quando viene specificato questo livello di criteri di cache, viene generata un'eccezione <xref:System.Net.WebException> se l'elemento non è presente nella cache locale.  
  
## <a name="cache-or-next-cache-only-policy"></a>CacheOrNextCacheOnly (criterio)  
 Se una risorsa richiesta valida è nella cache locale o in una cache intermedia nella rete locale, viene usata la risorsa memorizzata nella cache. In caso contrario, viene generata un'eccezione <xref:System.Net.WebException>. Nel protocollo di memorizzazione nella cache HTTP, ciò si ottiene usando la direttiva di controllo della cache only-if-cached.  
  
## <a name="no-cache-no-store-policy"></a>NoCacheNoStore (criterio)  
 Una risorsa richiesta non viene mai usata dalla cache né inserita nella cache. Se una risorsa richiesta è presente nella cache locale, viene rimossa. Questo livello di criteri indica alle cache intermedie di rimuovere la risorsa. Nel protocollo di memorizzazione nella cache HTTP, ciò si ottiene usando la direttiva di controllo della cache no-store.  
  
## <a name="refresh-policy"></a>Refresh (criterio)  
 Una risorsa richiesta può essere usata se viene ottenuta dal server o trovata in una cache diversa dalla cache locale. Prima che la richiesta possa essere soddisfatta da una cache intermedia, tale cache deve riconvalidare la voce memorizzata nella cache con il server. Nel protocollo di memorizzazione nella cache HTTP, ciò si ottiene usando la direttiva di controllo della cache max-age = 0 e l'intestazione Pragma no-cache.  
  
## <a name="reload-policy"></a>reload (criterio)  
 Le risorse richieste devono essere ottenute dal server. La risposta può essere salvata nella cache locale. Nel protocollo di memorizzazione nella cache HTTP, ciò si ottiene usando la direttiva di controllo della cache no-cache e l'intestazione Pragma no-cache.  
  
## <a name="revalidate-policy"></a>Revalidate (criterio)  
 Confronta la copia della risorsa nella cache con la copia nel server. Se la copia nel server è più recente, viene usata per soddisfare la richiesta e la copia nella cache viene sostituita. Se la copia nella cache corrisponde alla copia nel server, viene usata la copia memorizzata nella cache. Nel protocollo di memorizzazione nella cache HTTP, ciò si ottiene usando una richiesta condizionale.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)   
 [Criteri di cache basati sul tempo](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Configurazione della memorizzazione nella cache per applicazioni di rete](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [Elemento \<requestCaching> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

