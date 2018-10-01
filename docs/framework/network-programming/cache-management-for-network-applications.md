---
title: Gestione della cache per le applicazioni di rete
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e0b3ed66977dd6587789e3d88f532b699653c6f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195576"
---
# <a name="cache-management-for-network-applications"></a>Gestione della cache per le applicazioni di rete
Questo argomento e i relativi sottoargomenti descrivono il funzionamento della cache per le risorse ottenute tramite le classi <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> e <xref:System.Net.FtpWebRequest>.  
  
 Una cache offre uno spazio di archiviazione temporanea per le risorse richieste da un'applicazione. Se un'applicazione richiede più volte la stessa risorsa, quest'ultima può essere restituita dalla cache, evitando il sovraccarico generato dalla necessità di richiederla nuovamente al server. La memorizzazione nella cache contribuisce a migliorare le prestazioni dell'applicazione riducendo il tempo necessario per ottenere una risorsa richiesta. Consente anche di ridurre il traffico di rete limitando il numero di percorsi di andata e ritorno al server. Se la memorizzazione nella cache da un lato migliora le prestazioni, dall'altro aumenta il rischio che la risorsa restituita all'applicazione sia obsoleta, ossia non identica a quella che verrebbe inviata dal server se non venisse usata la funzionalità di memorizzazione nella cache.  
  
 La memorizzazione nella cache può consentire a utenti o processi non autorizzati di leggere dati riservati. È infatti possibile recuperare una risposta autenticata memorizzata nella cache senza disporre di autorizzazioni aggiuntive. Se la memorizzazione nella cache è attivata, modificare il valore della proprietà <xref:System.Net.WebRequest.CachePolicy%2A> in <xref:System.Net.Cache.RequestCacheLevel.BypassCache> o <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> per disattivarla per questo tipo di richiesta.  
  
 Per ovvi motivi di protezione, la memorizzazione nella cache **non** è consigliata per scenari di livello intermedio.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)  
 Illustra i concetti di base dei criteri di cache e spiega come definirne uno.  
  
 [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 Definisce i vari tipi di criteri di cache basati sulla posizione disponibili per le risorse Hypertext Transfer Protocol (http e https).  
  
 [Criteri di cache basati sull'ora](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 Descrive i criteri che è possibile usare per personalizzare i criteri di cache basati sull'ora.  
  
 [Configurazione della memorizzazione nella cache per applicazioni di rete](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 Descrive come creare a livello di codice criteri di cache e richieste in cui viene usata la memorizzazione nella cache.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Net.Cache>  
 Definisce i tipi e le enumerazioni usati per impostare i criteri di cache per le risorse ottenute mediante le classi <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> e <xref:System.Net.FtpWebRequest>.
