---
title: Criteri di cache
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
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: 11
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7323c93ef89e340595f6b62947ea45867e651425
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="cache-policy"></a>Criteri di cache
I criteri di cache definiscono le regole usate per determinare se è possibile soddisfare una richiesta usando una copia della risorsa richiesta memorizzata nella cache. Anche se nelle applicazioni vengono specificati i requisiti di cache del client relativi alla validità, l'efficacia dei criteri di cache è determinata non solo dai requisiti di cache del client, ma anche dai requisiti di scadenza del contenuto del server e di riconvalida del server. Per garantire che all'applicazione client venga restituito il contenuto più aggiornato, l'interazione tra i criteri di cache del client e i requisiti del server determina sempre la creazione dei criteri di cache più conservativi.  
  
 I criteri di cache possono essere basati sulla posizione o sul tempo. I criteri di cache basati sulla posizione definiscono il livello di aggiornamento delle voci memorizzate nella cache in base alla posizione da cui è possibile ricavare la risorsa richiesta. I criteri di cache basati sul tempo definiscono il livello di aggiornamento delle voci memorizzate nella cache usando l'ora di recupero della risorsa, le intestazioni restituite con la risorsa e l'ora corrente. Nella maggior parte delle applicazioni è possibile usare i criteri di cache predefiniti basati sul tempo, che implementano i criteri di memorizzazione nella cache specificati in RFC 2616, disponibile all'indirizzo [http://www.ietf.org](http://www.ietf.org/).  
  
 Nella tabella seguente sono descritte le classi usate per specificare i criteri di cache.  
  
|Nome di classe|Descrizione|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Rappresenta criteri di cache basati sulla posizione e sul tempo per risorse richieste tramite oggetti <xref:System.Net.HttpWebRequest>.|  
|<xref:System.Net.Cache.RequestCachePolicy>|Rappresenta criteri di cache basati sulla posizione o i criteri di cache <xref:System.Net.Cache.RequestCacheLevel.Default> basati sul tempo per risorse richieste tramite oggetti <xref:System.Net.WebRequest>.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Specifica i valori usati per creare oggetti <xref:System.Net.Cache.HttpRequestCachePolicy> basati sul tempo.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Specifica i valori usati per creare oggetti <xref:System.Net.Cache.HttpRequestCachePolicy> basati sulla posizione e sul tempo.|  
|<xref:System.Net.Cache.RequestCacheLevel>|Specifica i valori usati per creare oggetti <xref:System.Net.Cache.RequestCachePolicy> basati sulla posizione o <xref:System.Net.Cache.RequestCacheLevel.Default> basati sul tempo.|  
  
 È possibile definire criteri di cache per tutte le richieste eseguite dall'applicazione o per singole richieste. Quando si specificano criteri di cache a livello sia di applicazione sia di richiesta, vengono usati quelli a livello di richiesta. È possibile specificare criteri di cache a livello di applicazione usando i file di configurazione dell'applicazione o del computer oppure a livello di codice. Per altre informazioni, vedere [Elemento \<requestCaching> (Impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Per creare criteri di cache, è necessario definire un oggetto criteri tramite un'istanza della classe <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>. Per specificare i criteri in una richiesta, impostare la proprietà <xref:System.Net.WebRequest.CachePolicy%2A> della richiesta sull'oggetto criteri. Quando si impostano a livello di codice criteri a livello di applicazione, impostare la proprietà <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> sull'oggetto criteri.  
  
 Per esempi di codice che illustrano la creazione e l'uso dei criteri di cache, vedere [Configurazione della memorizzazione nella cache per applicazioni di rete](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Criteri di cache basati sul tempo](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Configurazione della memorizzazione nella cache per applicazioni di rete](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)

