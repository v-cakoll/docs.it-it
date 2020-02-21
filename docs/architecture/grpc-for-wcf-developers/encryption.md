---
title: Crittografia e sicurezza di rete-gRPC per sviluppatori WCF
description: Alcune note sulla crittografia e la sicurezza di rete in gRPC
ms.date: 09/02/2019
ms.openlocfilehash: f8a7aeaf2a65e4ff56ac33d728e40f09a436f7a6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542769"
---
# <a name="encryption-and-network-security"></a>Crittografia e sicurezza di rete

Il modello di sicurezza di rete per Windows Communication Foundation (WCF) è completo e complesso. Include la sicurezza a livello di trasporto usando HTTPS o TLS-over-TCP e la sicurezza a livello di messaggio usando la specifica WS-Security per crittografare i singoli messaggi.

gRPC lascia la rete sicura al protocollo HTTP/2 sottostante, che è possibile proteggere usando i certificati TLS.

I Web browser si ostinano a usare le connessioni TLS per HTTP/2, ma la maggior parte dei client programmatici, incluso. `HttpClient`NET, può usare HTTP/2 su connessioni non crittografate. `HttpClient` richiede la crittografia per impostazione predefinita, ma è possibile eseguirne l'override usando un'opzione di <xref:System.AppContext>.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Per le API pubbliche, è consigliabile usare sempre le connessioni TLS e fornire certificati validi per i servizi da un'autorità SSL corretta. [LetsEncrypt](https://letsencrypt.org) offre certificati SSL gratuiti e automatizzati e la maggior parte dell'infrastruttura di hosting attualmente supporta lo standard LetsEncrypt con i plug-in comuni o le estensioni.

Per i servizi interni in una rete aziendale, è comunque consigliabile usare TLS per proteggere il traffico di rete da e verso i servizi gRPC.

Se è necessario usare TLS esplicito tra i servizi in esecuzione in Kubernetes, è consigliabile usare un'autorità di certificazione nel cluster e un controller di gestione certificati come [Cert-Manager](https://docs.cert-manager.io/en/latest/). È quindi possibile assegnare automaticamente i certificati ai servizi in fase di distribuzione.

>[!div class="step-by-step"]
>[Precedente](channel-credentials.md)
>[Successivo](grpc-in-production.md)
