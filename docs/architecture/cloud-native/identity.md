---
title: Identità
description: Architettura di app .NET cloud native per Azure | Identità
ms.date: 05/13/2020
ms.openlocfilehash: 9fa48977e58e2ca5a5f3e231372a4791640a85fd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614019"
---
# <a name="identity"></a>Identità

Per la maggior parte delle applicazioni software è necessario conoscere l'utente o il processo che li chiama. L'utente o il processo che interagisce con un'applicazione è noto come entità di sicurezza e il processo di autenticazione e autorizzazione di tali entità è noto come gestione delle identità o semplicemente come *identità*. Le applicazioni semplici possono includere tutta la loro gestione delle identità all'interno dell'applicazione, ma questo approccio non si adatta perfettamente a molte applicazioni e a molti tipi di entità di sicurezza. Windows supporta l'utilizzo di Active Directory per fornire l'autenticazione e l'autorizzazione centralizzate.

<!-- (insert figure showing Windows AD auth model) -->

Anche se questa soluzione è efficace all'interno delle reti aziendali, non è progettata per l'uso da parte di utenti o applicazioni che si trovano all'esterno del dominio AD. Con la crescita delle applicazioni basate su Internet e l'aumento delle app native del cloud, i modelli di sicurezza si sono evoluti.

Nel modello di identità nativo del cloud odierno, si presuppone che l'architettura sia distribuita. Le app possono essere distribuite ovunque e possono comunicare con altre app ovunque. I client possono comunicare con queste app da qualsiasi luogo e, di fatto, i client possono essere costituiti da qualsiasi combinazione di piattaforme e dispositivi. Le soluzioni di identità native del Cloud sfruttano gli standard aperti per ottenere l'accesso sicuro alle applicazioni dai client. Questi client vanno da utenti umani su PC o telefoni, ad altre app ospitate ovunque online, a set-top box e dispositivi Internet che eseguono qualsiasi piattaforma software ovunque nel mondo.

Le moderne soluzioni di identità native del cloud usano in genere i token di accesso emessi da un servizio token di sicurezza/server (STS) a un'entità di sicurezza una volta determinata l'identità. Il token di accesso, in genere un token JSON Web (JWT), include *attestazioni* sull'entità di sicurezza. Queste attestazioni includono almeno l'identità dell'utente, ma possono includere anche altre attestazioni che possono essere utilizzate dalle applicazioni per determinare il livello di accesso per concedere l'entità di protezione.

<!-- (insert figure showing basic handshake involving a principal, an STS, and an app) -->

In genere, il servizio token di protezione è responsabile solo dell'autenticazione dell'entità. La determinazione del livello di accesso alle risorse viene lasciata ad altre parti dell'applicazione.

## <a name="references"></a>Riferimenti

- [Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Precedente](azure-monitor.md) 
> [Avanti](authentication-authorization.md)
