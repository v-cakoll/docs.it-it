---
title: Bilanciamento del carico gRPC-gRPC per sviluppatori WCF
description: Scelta di un servizio di bilanciamento del carico per lavorare con i servizi gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 215c0983146bbf9168f01956d64733f80cea6faf
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711167"
---
# <a name="load-balancing-grpc"></a>Bilanciamento del carico gRPC

Una distribuzione tipica di un'applicazione gRPC include un numero di istanze identiche del servizio, garantendo resilienza e scalabilità orizzontale. Il bilanciamento del carico distribuisce le richieste in ingresso tra queste istanze per fornire l'utilizzo completo di tutte le risorse disponibili. Per rendere invisibile questo bilanciamento del carico al client, è comune usare un server del servizio di bilanciamento del carico proxy per gestire le richieste provenienti dai client e instradarle alle istanze back-end.

I bilanciamenti del carico sono classificati in base al *livello* su cui operano. I bilanciamenti del carico di livello 4 funzionano a livello di *trasporto* , ad esempio con socket TCP, connessioni e pacchetti. I bilanciamenti del carico di livello 7 funzionano a livello di *applicazione* , gestendo in modo specifico le richieste http/2 per le applicazioni gRPC.

## <a name="l4-load-balancers"></a>Bilanciamento del carico L4

Un servizio di bilanciamento del carico L4 accetta una richiesta di connessione TCP da un client, apre un'altra connessione a una delle istanze back-end e copia i dati tra le due connessioni senza alcuna elaborazione reale. L4 offre prestazioni ottimali e bassa latenza, ma un controllo o un'intelligenza molto limitata. Fino a quando il client mantiene la connessione aperta, tutte le richieste verranno indirizzate alla stessa istanza back-end.

 [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) è un esempio di servizio di bilanciamento del carico L4.

## <a name="l7-load-balancers"></a>Bilanciamento del carico L7

Un servizio di bilanciamento del carico L7 analizza le richieste HTTP/2 in ingresso e le passa alle istanze back-end in base a una richiesta per richiesta, indipendentemente dal tempo di attesa della connessione da parte del client.

Esempi di bilanciamenti del carico L7:

- [NGINX](https://www.nginx.com/)
- [HAProxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

Come regola generale, i bilanciamenti del carico L7 rappresentano la scelta migliore per gRPC e altre applicazioni HTTP/2 (e, in realtà, per le applicazioni HTTP). I bilanciamenti del carico *L4 funzioneranno con le* applicazioni gRPC, ma sono particolarmente utili quando sono importanti la bassa latenza e il sovraccarico basso.

> [!IMPORTANT]
> Al momento della stesura di questo articolo, alcuni servizi di bilanciamento del carico L7 non supportano tutte le parti della specifica HTTP/2 richieste dai servizi gRPC, ad esempio le intestazioni finali.

Se si usa la crittografia TLS, i bilanciamenti del carico possono terminare la connessione TLS e passare le richieste non crittografate all'applicazione back-end oppure possono passare la richiesta crittografata insieme a. In entrambi i casi, è necessario configurare il servizio di bilanciamento del carico con la chiave pubblica e privata del server, in modo che sia in grado di decrittografare le richieste di elaborazione.

Vedere la documentazione per il servizio di bilanciamento del carico preferito per informazioni su come configurarlo per gestire le richieste HTTP/2 con i servizi back-end.

## <a name="load-balancing-within-kubernetes"></a>Bilanciamento del carico in Kubernetes

Per una discussione sul bilanciamento del carico tra servizi interni in Kubernetes, vedere [la sezione sulle reti mesh](service-mesh.md) dei servizi.

>[!div class="step-by-step"]
>[Precedente](service-mesh.md)
>[Successivo](application-performance-management.md)
