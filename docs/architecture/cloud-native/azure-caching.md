---
title: Memorizzazione nella cache in un'applicazione nativa del cloud
description: Informazioni sulle strategie di memorizzazione nella cache in un'applicazione nativa del cloud.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 2da61a01fc53233d1934df813fcba3b91a495c43
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794968"
---
# <a name="caching-in-a-cloud-native-app"></a>Memorizzazione nella cache in un'app nativa del cloud

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

I vantaggi della memorizzazione nella cache sono ben noti. La tecnica funziona copiando temporaneamente i dati a cui si accede di frequente da un archivio dati back-end ad *archiviazione veloce* più vicina all'applicazione. La memorizzazione nella cache è spesso implementata dove...

- I dati rimangono relativamente statici.
- L'accesso ai dati è lento, soprattutto rispetto alla velocità della cache.
- I dati sono soggetti a livelli elevati di contesa.

## <a name="why"></a>Perché?

Come illustrato nella [Guida di Microsoft Caching](https://docs.microsoft.com/azure/architecture/best-practices/caching), la memorizzazione nella cache può migliorare le prestazioni, la scalabilità e la disponibilità per i singoli microservizi e il sistema nel suo complesso. Riduce la latenza e la contesa della gestione di volumi elevati di richieste simultanee a un archivio dati. Man mano che il volume dei dati e il numero di utenti aumentano, maggiori sono i vantaggi della memorizzazione nella cache.

La memorizzazione nella cache è più efficace quando un client legge ripetutamente dati non modificabili o che cambiano raramente. Gli esempi includono informazioni di riferimento, ad esempio informazioni sul prodotto e sui prezzi, o risorse statiche condivise che sono costose da costruire.

Anche se i microservizi devono essere senza stato, una cache distribuita può supportare l'accesso simultaneo ai dati dello stato della sessione quando strettamente necessario.

Prendere in considerazione anche la memorizzazione nella cache per evitare calcoli ripetitivi. Se un'operazione trasforma i dati o esegue un calcolo complesso, memorizzare nella cache il risultato per le richieste successive.

## <a name="caching-architecture"></a>Architettura di Caching

Le applicazioni cloud native implementano in genere un'architettura di Caching distribuito. La cache è ospitata come [servizio di backup](./definition.md#backing-services)basato sul cloud, separato dai microservizi. La figura 5-20 illustra l'architettura.

![Memorizzazione nella cache in un'app Cloud nativa](media/caching-in-a-cloud-native-app.png)

**Figura 5-19**: memorizzazione nella cache in un'app Cloud nativa

Nella figura precedente si noti come la cache è indipendente e condivisa dai microservizi. In questo scenario, la cache viene richiamata dal [gateway API](./front-end-communication.md). Come illustrato nel capitolo 4, il gateway funge da front-end per tutte le richieste in ingresso. La cache distribuita aumenta la velocità di risposta del sistema restituendo i dati memorizzati nella cache laddove possibile. Inoltre, la separazione della cache dai servizi consente la scalabilità verticale o orizzontale della cache per soddisfare le esigenze di traffico più elevate.

La figura presenta un modello di memorizzazione nella cache comune noto come [modello cache-aside](https://docs.microsoft.com/azure/architecture/patterns/cache-aside). Per una richiesta in ingresso, eseguire prima una query sulla cache (passaggio \#1) per una risposta. Se viene trovato, i dati vengono restituiti immediatamente. Se i dati non esistono nella cache (noto come [mancato riscontro nella cache](https://www.techopedia.com/definition/6308/cache-miss)), viene recuperato da un database locale in un servizio downstream (passaggio \#2). Viene quindi scritto nella cache per richieste future (passaggio \#3) e restituito al chiamante. È necessario prestare attenzione per rimuovere periodicamente i dati memorizzati nella cache, in modo che il sistema rimanga tempestivamente e coerente.

Con la crescita di una cache condivisa, potrebbe risultare vantaggioso partizionare i dati tra più nodi. Questa operazione consente di ridurre al minimo i conflitti e migliorare la scalabilità. Molti servizi di memorizzazione nella cache supportano la possibilità di aggiungere e rimuovere in modo dinamico i nodi e di ribilanciare i dati tra le partizioni. Questo approccio prevede in genere il clustering. Il clustering espone una raccolta di nodi federati come una singola cache semplice. Internamente, tuttavia, i dati vengono distribuiti tra i nodi dopo una strategia di distribuzione predefinita che bilancia il carico in modo uniforme.

## <a name="azure-cache-for-redis"></a>Cache Redis di Azure

[Cache di Azure per Redis](https://azure.microsoft.com/services/cache/) è un servizio di memorizzazione nella cache dei dati e broker di messaggistica protetto, completamente gestito da Microsoft. Usato come offerta di piattaforma distribuita come servizio (PaaS), garantisce velocità effettiva elevata e accesso a bassa latenza ai dati. Il servizio è accessibile da qualsiasi applicazione all'interno o all'esterno di Azure.

Il servizio cache di Azure per Redis gestisce l'accesso ai server Redis Open Source ospitati nei data center di Azure. Il servizio funge da facciata garantendo la gestione, il controllo di accesso e la sicurezza. Il servizio supporta in modo nativo un set completo di strutture di dati, tra cui stringhe, hash, elenchi e set. Se l'applicazione usa già Redis, funzionerà così com'è con cache di Azure per Redis.

Cache di Azure per Redis è più di un semplice server di cache. Può supportare diversi scenari per migliorare un'architettura di microservizi:

- Un archivio dati in memoria
- Un database non relazionale distribuito
- Broker di messaggi
- Un server di configurazione o di individuazione
  
Per gli scenari avanzati, una copia dei dati memorizzati nella cache può essere salvata [in modo permanente su disco](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-how-to-premium-persistence). Se un evento irreversibile Disabilita sia la cache primaria che quella di replica, la cache viene ricostruita dallo snapshot più recente.

Cache Redis di Azure è disponibile in diverse configurazioni predefinite e piani tariffari.  Il [livello Premium](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-premium-tier-intro) offre numerose funzionalità di livello aziendale, come il clustering, la persistenza dei dati, la replica geografica e l'isolamento della rete virtuale.

>[!div class="step-by-step"]
>[Precedente](relational-vs-nosql-data.md)
>[Successivo](elastic-search-in-azure.md)
