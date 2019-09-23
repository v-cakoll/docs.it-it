---
title: Crittografia e sicurezza di rete-gRPC per sviluppatori WCF
description: Alcune note sulla crittografia e la sicurezza di rete in gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 8a115b59337003669b4e5436edffe239489ca79e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184463"
---
# <a name="encryption-and-network-security"></a>Crittografia e sicurezza di rete

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Il modello di sicurezza di rete di WCF è vasto e complesso, inclusa la sicurezza a livello di trasporto tramite HTTPS o TLS-over-TCP e la sicurezza a livello di messaggio utilizzando la specifica WS-Security per crittografare i singoli messaggi.

gRPC lascia la rete sicura al protocollo HTTP/2 sottostante, che può essere protetto usando i normali certificati TLS.

I Web browser si ostinano a usare le connessioni TLS per HTTP/2, ma la maggior parte dei client programmatici, incluso. `HttpClient`NET, può usare http/2 su connessioni non crittografate. `HttpClient`*richiede la* crittografia per impostazione predefinita, ma è possibile eseguirne l' <xref:System.AppContext> override usando un'opzione.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Per le API pubbliche, è consigliabile usare sempre le connessioni TLS e fornire certificati validi per i servizi da un'autorità SSL corretta. [LetsEncrypt](https://letsencrypt.org) offre certificati SSL gratuiti e automatizzati e la maggior parte dell'infrastruttura di hosting attualmente supporta lo standard LetsEncrypt con i plug-in comuni o le estensioni.

Per i servizi interni in una rete aziendale, è comunque consigliabile usare TLS per proteggere il traffico di rete da e verso i servizi gRPC.

La comunicazione tra microservizi in un cluster, ad esempio Kubernetes o Docker Swarm, è in genere crittografata automaticamente dal livello di rete del contenitore. Pertanto, l'implementazione di TLS nei servizi in esecuzione esclusivamente in tale cluster non è necessaria. Nella sezione "mesh dei servizi" del capitolo successivo saranno disponibili ulteriori informazioni su questo argomento.

Se è necessario usare TLS esplicito tra i servizi in esecuzione in Kubernetes, è consigliabile usare un'autorità di certificazione nel cluster e un controller di gestione certificati, ad esempio [Cert-Manager](https://docs.cert-manager.io/en/latest/) , per assegnare certificati automatici ai servizi in fase di distribuzione.

>[!div class="step-by-step"]
>[Precedente](channel-credentials.md)
>[Successivo](grpc-in-production.md)
