---
title: Bilanciamento del carico gRPC-gRPC per sviluppatori WCF
description: Scelta di un servizio di bilanciamento del carico per lavorare con i servizi gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5d4a9be9b8f4e511a72af6b68d8a005604fd984d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184393"
---
# <a name="load-balancing-grpc"></a>Bilanciamento del carico gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una distribuzione tipica di un'applicazione gRPC include un numero di istanze identiche del servizio, garantendo resilienza e scalabilità orizzontale. Bilanciamento del carico delle richieste in ingresso distribuite in queste istanze per fornire l'utilizzo completo di tutte le risorse disponibili. Per rendere invisibile questo bilanciamento del carico al client, è comune usare un server del servizio di bilanciamento del carico proxy per gestire le richieste provenienti dai client e instradarle alle istanze back-end.

I bilanciamenti del carico sono classificati in base al *livello* su cui operano. I bilanciamenti del carico di livello 4 funzionano a livello di *trasporto* , ad esempio con socket TCP, connessioni e pacchetti. I bilanciamenti del carico di livello 7 funzionano a livello di *applicazione* , gestendo in modo specifico le richieste http/2 per le applicazioni gRPC.

## <a name="l4-load-balancers"></a>Bilanciamento del carico L4

Un servizio di bilanciamento del carico L4 accetta una richiesta di connessione TCP da un client, apre un'altra connessione a una delle istanze back-end e copia i dati tra le due connessioni senza alcuna elaborazione reale. L4 offre prestazioni ottimali e bassa latenza, ma un controllo o un'intelligenza molto limitata. Fino a quando il client mantiene la connessione aperta, tutte le richieste verranno indirizzate alla stessa istanza back-end.

Un esempio di servizio di bilanciamento del carico L4 è il [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).

## <a name="l7-load-balancers"></a>Bilanciamento del carico L7

Un servizio di bilanciamento del carico L7 analizza le richieste HTTP/2 in ingresso e le passa alle istanze back-end in base a una richiesta per richiesta, indipendentemente dal tempo di attesa della connessione da parte del client.

Esempi di bilanciamenti del carico L7 includono:

- [Nginx](https://www.nginx.com/)
- [HAproxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

Come regola generale, i bilanciamenti del carico L7 rappresentano la scelta migliore per gRPC e altre applicazioni HTTP/2 (e, in realtà, per le applicazioni HTTP). I bilanciamenti del carico *L4 funzioneranno con le* applicazioni gRPC, ma sono principalmente utili quando la bassa latenza e il sovraccarico basso sono di importanza fondamentale.

> [!IMPORTANT]
> Al momento della stesura di questo articolo, non tutti i servizi di bilanciamento del carico L7 supportano tutte le parti della specifica HTTP/2 richieste dai servizi gRPC, ad esempio le intestazioni finali.

Quando si usa la crittografia TLS, i bilanciamenti del carico possono terminare la connessione TLS e passare le richieste non crittografate all'applicazione back-end oppure passare la richiesta crittografata insieme. In entrambi i casi, è necessario configurare il servizio di bilanciamento del carico con la chiave pubblica e privata del server, in modo che sia in grado di decrittografare le richieste di elaborazione.

Per informazioni su come configurarlo per gestire le richieste HTTP/2 con i servizi back-end, vedere la documentazione relativa al servizio di bilanciamento del carico preferito.

## <a name="load-balancing-within-kubernetes"></a>Bilanciamento del carico in Kubernetes

Per una discussione sul bilanciamento del carico tra servizi interni in Kubernetes, vedere [la sezione sulle reti mesh](service-mesh.md) dei servizi.

>[!div class="step-by-step"]
>[Precedente](service-mesh.md)
>[Successivo](application-performance-management.md)
