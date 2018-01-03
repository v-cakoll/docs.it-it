---
title: 'Interazione tra criteri di cache: durata massima e obsolescenza massima'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2fc28f120b76e51cd285f9b7d6a446f4835113a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a>Interazione tra criteri di cache: durata massima e obsolescenza massima
Per garantire che all'applicazione client venga restituito il contenuto più aggiornato, l'interazione tra criteri di cache del client e requisiti di riconvalida del server determina sempre la creazione dei criteri di cache più conservativi. In tutti gli esempi di questo argomento vengono illustrati i criteri di cache per una risorsa memorizzata nella cache il 1° gennaio con scadenza il 4 gennaio.  
  
 Negli esempi seguenti il valore di obsolescenza massima (`maxStale`) viene usato in combinazione con un valore di durata massima (`maxAge`):  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 5 giorni e non specificano alcun valore per `maxStale`, in base al valore di `maxAge` il contenuto può essere usato fino al 6 gennaio. In base ai requisiti di riconvalida del server, tuttavia, il contenuto scade il 4 gennaio. Poiché la data di scadenza del contenuto è più conservativa (antecedente), ha la precedenza rispetto ai criteri associati a `maxAge`. Il contenuto scade quindi il 4 gennaio e deve essere riconvalidato anche se la durata massima non è ancora stata raggiunta.  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 5 giorni e di `maxStale` su 3 giorni, in base al valore di `maxAge` il contenuto rimane valido fino al 6 gennaio, mentre in base al valore di `maxStale` è valido fino al 7 gennaio. Il contenuto viene quindi riconvalidato il 6 gennaio.  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 5 giorni e di `maxStale` su 1 giorno, in base al valore di `maxAge` il contenuto rimane valido fino al 6 gennaio, mentre in base al valore di `maxStale` è valido fino al 5 gennaio. Il contenuto viene quindi riconvalidato il 5 gennaio.  
  
 Quando il valore di durata massima è inferiore alla data di scadenza del contenuto, prevale sempre il comportamento più conservativo per la memorizzazione nella cache e il valore di obsolescenza massima non ha alcun effetto. Gli esempi seguenti illustrano l'effetto prodotto dall'impostazione di un valore di obsolescenza massima (`maxStale`) quando la durata massima (`maxAge`) viene raggiunta prima della scadenza del contenuto:  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 1 giorno e non specificano alcun valore per `maxStale`, il contenuto viene riconvalidato il 2 gennaio anche se non è ancora scaduto.  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 1 giorno e di `maxStale` su 3 giorni, il contenuto viene riconvalidato il 2 gennaio e viene quindi applicata l'impostazione relativa ai criteri più conservativi.  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 1 giorno e di `maxStale` su 1 giorno, il contenuto viene riconvalidato il 2 gennaio.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)  
 [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Criteri di cache basati sull'ora](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [Configurazione della memorizzazione nella cache per applicazioni di rete](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [Interazione tra criteri di cache: durata massima e validità minima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)
