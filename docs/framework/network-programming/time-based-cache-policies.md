---
title: criteri di cache basati sull'ora
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- cache synchronization date policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- time, cached resources
- maximum age policy
- synchronization, cache
- staleness of cached resources
- default time-based cache policy
- maximum staleness policy
- content cache policies
- expired content
- minimum freshness policy
- age of cached resources
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
ms.openlocfilehash: 0edde8e716d5ce3b1444e994234def5835341475
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047117"
---
# <a name="time-based-cache-policies"></a>criteri di cache basati sull'ora
I criteri di cache basati sul tempo definiscono il livello di aggiornamento delle voci memorizzate nella cache usando l'ora di recupero della risorsa, le intestazioni restituite con la risorsa e l'ora corrente. Durante l'impostazione di criteri di cache basati sul tempo, è possibile usare il criterio basato sul tempo <xref:System.Net.Cache.HttpRequestCacheLevel.Default> oppure creare criteri personalizzati. Quando si usano i criteri basati sul tempo predefiniti per le risorse ottenute mediante HTTP (Hypertext Transfer Protocol), il comportamento esatto della cache è determinato dalle intestazioni incluse nella risposta memorizzata nella cache e dai comportamenti specificati nelle sezioni 13 e 14 del documento RFC 2616, disponibile nel sito Web [Internet Engineering Task Force (IETF)](https://www.ietf.org/). Per un esempio di codice che illustra l'impostazione di criteri basati sul tempo predefiniti per le risorse HTTP, vedere [Procedura: Impostare criteri di cache predefiniti basati sul tempo per un'applicazione](how-to-set-the-default-time-based-cache-policy-for-an-application.md). Per esempi di codice che illustrano la creazione e l'uso dei criteri di cache, vedere [Configurazione della memorizzazione nella cache per applicazioni di rete](configuring-caching-in-network-applications.md).  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a>Criteri per determinare il livello di aggiornamento delle voci memorizzate nella cache  
 Per personalizzare i criteri di cache basati sul tempo, è possibile specificare che occorre usare una o più delle impostazioni seguenti per determinare il livello di aggiornamento delle voci memorizzate nella cache:  
  
- Durata massima  
  
- Obsolescenza massima  
  
- Validità minima  
  
- Data di sincronizzazione della cache  
  
> [!NOTE]
> L'uso dei criteri di cache basati sul tempo predefiniti non è da confondersi con l'impostazione di criteri di cache predefiniti per l'applicazione. I criteri basati sul tempo predefiniti sono criteri specifici che possono essere usati a livello di richiesta o di applicazione. I criteri di cache predefiniti per l'applicazione sono criteri (basati sulla posizione o sul tempo) applicati quando non è impostato alcun criterio per una richiesta. Per informazioni dettagliate sull'impostazione di criteri di cache predefiniti per l'applicazione, vedere <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.  
  
### <a name="maximum-age"></a>Maximum Age  
 L'impostazione di durata massima per i criteri specifica per quanto tempo è possibile usare una copia memorizzata nella cache di una risorsa. Se la copia memorizzata nella cache della risorsa è precedente al periodo di tempo specificato, la risorsa deve essere riconvalidata controllandola in base al contenuto nel server. Se la durata massima consente di usare la risorsa dopo la scadenza, questo requisito non viene applicato a meno che non venga specificato anche un valore di obsolescenza massima.  
  
### <a name="maximum-staleness"></a>Obsolescenza massima  
 L'impostazione di durata massima per i criteri specifica il periodo di tempo dopo la scadenza del contenuto durante il quale è consentito l'uso della copia memorizzata nella cache della risorsa. Questo è l'unico requisito per i criteri di cache che consente di usare le risorse dopo la scadenza.  
  
### <a name="minimum-freshness"></a>Validità minima  
 L'impostazione di durata massima per i criteri specifica il periodo di tempo prima della scadenza del contenuto durante il quale è consentito l'uso della copia memorizzata nella cache della risorsa. Questo criterio causa la scadenza di una voce della cache prima della data di scadenza, pertanto le impostazioni di obsolescenza massima e validità minima si escludono a vicenda.  
  
## <a name="cache-synchronization-date"></a>Data di sincronizzazione della cache  
 L'impostazione della data di sincronizzazione della cache per i criteri determina quando una copia memorizzata nella cache di una risorsa deve essere riconvalidata controllandola in base al contenuto nel server. Se il contenuto è stato modificato dopo la memorizzazione nella cache dell'elemento, questo viene recuperato dal server, memorizzato nella cache e restituito all'applicazione. Se il contenuto risulta invariato, viene aggiornato il timestamp e l'applicazione ottiene il contenuto memorizzato nella cache.  
  
 La data di sincronizzazione della cache consente di specificare una data assoluta quando il contenuto memorizzato nella cache deve essere riconvalidato. Se una voce della cache aggiornata è stata riconvalidata per l'ultima volta prima della data di sincronizzazione della cache, la riconvalida con il server viene comunque eseguita. Se la voce della cache è stata riconvalidata dopo la data di sincronizzazione della cache e non esistono altri requisiti relativi all'aggiornamento o alla riconvalida nel server che invalidano la voce memorizzata nella cache, viene usata la voce dalla cache. Se la data di sincronizzazione della cache è impostata su una data futura, la voce viene riconvalidata a ogni richiesta fino al superamento della data di sincronizzazione della cache.  
  
 Gli argomenti seguenti forniscono informazioni sugli effetti della combinazione delle impostazioni per i criteri di cache basati sul tempo:  
  
- [Interazione tra criteri di cache: durata massima e obsolescenza massima](cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
- [Interazione tra criteri di cache: durata massima e validità minima](cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a>Vedere anche

- [Gestione della cache per le applicazioni di rete](cache-management-for-network-applications.md)
- [Criteri cache](cache-policy.md)
- [Criteri di cache basati sulla posizione](location-based-cache-policies.md)
- [Configurazione della memorizzazione nella cache per applicazioni di rete](configuring-caching-in-network-applications.md)
- [\<elemento> requestCaching (impostazioni di rete)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
