---
title: Sicurezza nelle applicazioni gRPC-gRPC per sviluppatori WCF
description: Panoramica dell'autenticazione e dell'autorizzazione di chiamata e canale in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: b88ed0c01d1ca4432c7e4fe7115246f4227159df
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967243"
---
# <a name="security-in-grpc-applications"></a>Sicurezza nelle applicazioni gRPC

In qualsiasi scenario reale, è essenziale proteggere le applicazioni e i servizi. La sicurezza copre tre aree principali: la crittografia del traffico di rete per impedirne l'intercettazione da attori malintenzionati. autenticazione dei client e dei server per stabilire l'identità e l'attendibilità; e autorizzare i client a controllare l'accesso ai sistemi e a applicare le autorizzazioni in base all'identità.

> [!NOTE]
> L' **autenticazione** è responsabile della definizione dell'identità di un client o di un server. L' **autorizzazione** è responsabile di determinare se un client è autorizzato ad accedere a una risorsa o a eseguire un comando.

In questo capitolo vengono illustrate le funzionalità di autenticazione e autorizzazione in gRPC per ASP.NET Core e viene illustrata la sicurezza di rete tramite connessioni crittografate TLS.

## <a name="wcf-authentication-and-authorization"></a>Autenticazione e autorizzazione WCF

In WCF, l'autenticazione e l'autorizzazione venivano gestite in modi diversi a seconda dei trasporti e delle associazioni utilizzati. WCF supporta diversi standard di sicurezza WS-\*, oltre all'autenticazione di Windows per i servizi HTTP eseguiti nei servizi IIS o NetTCP tra i sistemi Windows.

## <a name="grpc-authentication-and-authorization"></a>autenticazione e autorizzazione di gRPC

l'autenticazione e l'autorizzazione di gRPC funzionano su due livelli. L'autenticazione/autorizzazione a livello di chiamata viene in genere gestita usando token che vengono applicati ai metadati quando viene effettuata la chiamata. L'autenticazione a livello di canale utilizza un certificato client applicato a livello di connessione e può includere anche le credenziali di autenticazione/autorizzazione a livello di chiamata da applicare a ogni chiamata sul canale automaticamente. È possibile utilizzare uno o entrambi i meccanismi per proteggere il servizio.

L'implementazione ASP.NET Core di gRPC supporta l'autenticazione e l'autorizzazione utilizzando la maggior parte dei meccanismi di ASP.NET Core standard:

- Autenticazione chiamata
  - Azure Active Directory
  - IdentityServer
  - Token di porta JWT
  - OAuth 2,0
  - OpenID Connect
  - WS-Federation
- Autenticazione del canale
  - Certificato client

I metodi di autenticazione della chiamata sono tutti basati su *token*. L'unica differenza reale è il modo in cui il token viene generato e le librerie usate per convalidare i token nel servizio ASP.NET Core.

Per ulteriori informazioni, vedere la [documentazione relativa all'autenticazione e all'autorizzazione su Microsoft docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).

> [!NOTE]
> Quando si usa gRPC su una connessione HTTP/2 crittografata con TLS, tutto il traffico tra client e server viene crittografato, anche se non si usa l'autenticazione a livello di canale.

Questo capitolo illustra come applicare le credenziali di chiamata e le credenziali del canale a un servizio gRPC e come usare le credenziali da un client gRPC di .NET Core per l'autenticazione con il servizio.

>[!div class="step-by-step"]
>[Precedente](client-libraries.md)
>[Successivo](call-credentials.md)
