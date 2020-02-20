---
title: Sicurezza nelle applicazioni gRPC-gRPC per sviluppatori WCF
description: Panoramica dell'autenticazione e dell'autorizzazione di chiamata e canale in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503414"
---
# <a name="security-in-grpc-applications"></a>Sicurezza nelle applicazioni gRPC

In qualsiasi scenario reale, è essenziale proteggere le applicazioni e i servizi. La sicurezza copre tre aree principali: 

* Crittografia del traffico di rete per impedire l'intercettazione da hacker malintenzionati.
* Autenticazione dei client e dei server per stabilire l'identità e l'attendibilità.
* Autorizzazione dei client a controllare l'accesso ai sistemi e applicare le autorizzazioni in base all'identità.

> [!NOTE]
> L' *autenticazione* è responsabile della definizione dell'identità di un client o di un server. L' *autorizzazione* è responsabile di determinare se un client è autorizzato ad accedere a una risorsa o a eseguire un comando.

In questo capitolo vengono trattate le funzionalità per l'autenticazione e l'autorizzazione in gRPC per ASP.NET Core. Verrà inoltre discussa la sicurezza di rete tramite connessioni crittografate TLS.

## <a name="wcf-authentication-and-authorization"></a>Autenticazione e autorizzazione WCF

In Windows Communication Foundation (WCF), l'autenticazione e l'autorizzazione venivano gestite in modi diversi, a seconda dei trasporti e delle associazioni utilizzate. WCF supporta diversi standard di sicurezza WS-\*. Supporta inoltre l'autenticazione di Windows per i servizi HTTP in esecuzione nei servizi IIS o NetTCP tra i sistemi Windows.

## <a name="grpc-authentication-and-authorization"></a>autenticazione e autorizzazione di gRPC

l'autenticazione e l'autorizzazione di gRPC funzionano su due livelli:

* L'autenticazione/autorizzazione a livello di chiamata viene in genere gestita tramite token che vengono applicati ai metadati quando viene effettuata la chiamata. 
* L'autenticazione a livello di canale usa un certificato client applicato a livello di connessione. Può inoltre includere le credenziali di autenticazione/autorizzazione a livello di chiamata da applicare a ogni chiamata sul canale automaticamente. 

È possibile utilizzare uno o entrambi i meccanismi per proteggere il servizio.

L'implementazione ASP.NET Core di gRPC supporta l'autenticazione e l'autorizzazione attraverso la maggior parte dei meccanismi di ASP.NET Core standard:

- Autenticazione chiamata
  - Azure Active Directory
  - IdentityServer
  - Token di porta JWT
  - OAuth 2.0
  - OpenID Connect
  - WS-Federation
- Autenticazione del canale
  - Certificato client

I metodi di autenticazione della chiamata sono tutti basati su *token*. L'unica differenza reale riguarda il modo in cui vengono generati i token e le librerie usate per convalidare i token nel servizio ASP.NET Core.

Per altre informazioni, vedere l'articolo [autenticazione e autorizzazione](/aspnet/core/grpc/authn-and-authz) .

> [!NOTE]
> Quando si usa gRPC su una connessione HTTP/2 crittografata con TLS, tutto il traffico tra client e server viene crittografato, anche se non si usa l'autenticazione a livello di canale.

In questo capitolo viene illustrato come applicare le credenziali di chiamata e le credenziali del canale a un servizio gRPC. Verrà inoltre illustrato come utilizzare le credenziali di un client gRPC .NET Core per l'autenticazione con il servizio.

>[!div class="step-by-step"]
>[Precedente](client-libraries.md)
>[Successivo](call-credentials.md)
