---
title: Sicurezza nelle applicazioni gRPC - gRPC per gli sviluppatori WCFSecurity in gRPC applications - gRPC for WCF developers
description: Panoramica dell'autenticazione e dell'autorizzazione delle chiamate e dei canali in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147815"
---
# <a name="security-in-grpc-applications"></a>Sicurezza nelle applicazioni gRPC

In qualsiasi scenario reale, la protezione di applicazioni e servizi è essenziale. La sicurezza copre tre aree chiave:

* Crittografia del traffico di rete per impedire a hacker malintenzionati di intercettarlo.
* Autenticazione di client e server per stabilire identità e attendibilità.
* Autorizzazione dei client a controllare l'accesso ai sistemi e applicare le autorizzazioni in base all'identità.

> [!NOTE]
> *L'autenticazione* riguarda la determinazione dell'identità di un client o di un server. *L'autorizzazione* riguarda la determinazione se un client dispone dell'autorizzazione per accedere a una risorsa o eseguire un comando.

Questo capitolo tratterà le funzionalità per l'autenticazione e l'autorizzazione in gRPC per ASP.NET Core. Discuterà anche la sicurezza di rete attraverso le connessioni crittografate TLS.

## <a name="wcf-authentication-and-authorization"></a>Autenticazione e autorizzazione WCFWCF authentication and authorization

In Windows Communication Foundation (WCF), l'autenticazione e l'autorizzazione sono state gestite in modi diversi, a seconda dei trasporti e delle associazioni in uso. WCF supportava\* vari standard di sicurezza WS.WCF supported various WS- security standards. Supporta inoltre l'autenticazione di Windows per i servizi HTTP in esecuzione nei servizi IIS o NetTCP tra sistemi Windows.

## <a name="grpc-authentication-and-authorization"></a>Autenticazione e autorizzazione gRPC

L'autenticazione e l'autorizzazione gRPC funzionano su due livelli:

* L'autenticazione/autorizzazione a livello di chiamata viene in genere gestita tramite token applicati nei metadati quando viene effettuata la chiamata.
* L'autenticazione a livello di canale utilizza un certificato client applicato a livello di connessione. Può anche includere automaticamente le credenziali di autenticazione/autorizzazione a livello di chiamata da applicare a ogni chiamata sul canale.

È possibile utilizzare uno o entrambi questi meccanismi per proteggere il servizio.

L'implementazione ASP.NET Core di gRPC supporta l'autenticazione e l'autorizzazione attraverso la maggior parte dei meccanismi standard ASP.NET Core:

- Autenticazione delle chiamate
  - Azure Active Directory
  - Server identità
  - JWT Bearer Token
  - OAuth 2.0
  - OpenID Connect
  - WS-Federation
- Autenticazione del canale
  - Certificato client

I metodi di autenticazione delle chiamate sono tutti basati sui *token.* L'unica vera differenza è il modo in cui vengono generati i token e le librerie utilizzate per convalidare i token nel servizio ASP.NET Core.

Per altre informazioni, vedere l'articolo [Autenticazione e autorizzazione.](/aspnet/core/grpc/authn-and-authz)

> [!NOTE]
> Quando si utilizza gRPC su una connessione HTTP/2 crittografata con TLS, tutto il traffico tra client e server viene crittografato, anche se non si utilizza l'autenticazione a livello di canale.

In questo capitolo verrà illustrato come applicare le credenziali di chiamata e le credenziali del canale a un servizio gRPC. Verrà inoltre illustrato come utilizzare le credenziali da un client gRPC di .NET Core per l'autenticazione con il servizio.

>[!div class="step-by-step"]
>[Successivo](client-libraries.md)
>[precedente](call-credentials.md)
