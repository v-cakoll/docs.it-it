---
title: Progettare applicazioni Web moderne con ASP.NET Core e Azure
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Introduzione
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.openlocfilehash: 085ec85002fc1661d6e20b3c3f11cf4b6ea2161b
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37103920"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>Progettare applicazioni Web moderne con ASP.NET Core e Azure

![Immagine di copertina](./media/cover.jpg)


.NET Core e ASP.NET Core offrono diversi vantaggi rispetto allo sviluppo .NET tradizionale. È consigliabile usare .NET Core per le applicazioni server se alcuni o tutti gli aspetti seguenti sono importanti per il successo dell'applicazione:

-   Supporto multipiattaforma

-   Uso di microservizi

-   Uso di contenitori Docker

-   Requisiti di scalabilità e prestazioni elevate

-   Controllo delle versioni side-by-side di .NET in base all'applicazione nello stesso server

Le applicazioni .NET tradizionali possono supportare e supportano questi requisiti, ma ASP.NET Core e .NET Core sono stati ottimizzati per offrire supporto migliorato per gli scenari elencati sopra.

Sempre più organizzazioni scelgono di ospitare le proprie applicazioni Web nel cloud usando servizi come Microsoft Azure. Prendere in considerazione di ospitare l'applicazione nel cloud se gli aspetti seguenti sono importanti per l'applicazione o l'organizzazione:

-   Riduzione dell'investimento nei costi del data center (hardware, software, spazio, utilità e così via)

-   Prezzi flessibili (pagamento in base all'utilizzo, non per la capacità inattiva)

-   Affidabilità estrema

-   Mobilità delle app migliorata, con semplice modifica di come e dove distribuire l'app

-   Capacità flessibile, con ridimensionamento in base alle effettive esigenze

La compilazione di applicazioni Web con ASP.NET Core, ospitato in Microsoft Azure, offre diversi vantaggi competitivi rispetto alle alternative tradizionali. ASP.NET Core è ottimizzato per procedure di sviluppo di applicazioni Web moderne e scenari di hosting sul cloud. In questa guida viene descritto come progettare applicazioni ASP.NET Core per sfruttare al meglio i vantaggi di queste funzionalità.

## <a name="purpose"></a>Scopo

Questa guida offre linee guida end-to-end sulla compilazione di applicazioni Web monolitiche usando ASP.NET Core e Azure.

Questa guida è complementare al documento "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" (Architettura e sviluppo di applicazioni basate su microservizi e in contenitori con .NET), incentrato più su Docker, microservizi e distribuzione di contenitori per ospitare applicazioni aziendali.

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a>Architecting and Developing Containerized Microservice Based Apps in .NET (Architettura e sviluppo di applicazioni basate su microservizi e in contenitori con .NET)
> - **eBook**  
> <http://aka.ms/MicroservicesEbook>
> - **Applicazione di esempio**  
> <http://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>Destinatari della guida

I destinatari di questa guida sono prevalentemente sviluppatori, responsabili dello sviluppo e progettisti di architetture interessati alla compilazione di applicazioni Web moderne con tecnologie e servizi Microsoft nel cloud.

Un'altra parte minore dei destinatari di questa guida è costituita da responsabili delle decisioni tecniche che hanno già familiarità con ASP.NET e/o Azure e vogliono ottenere informazioni sull'opportunità o meno di eseguire l'aggiornamento ad ASP.NET Core per progetti nuovi o esistenti.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

Questa guida è stata condensata in un documento relativamente piccolo, incentrato sulla compilazione di applicazioni Web con tecnologie .NET moderne e Microsoft Azure. Per questo motivo, può essere letta interamente per ottenere nozioni di base per la comprensione di tali applicazioni e delle considerazioni tecniche associate. La guida, insieme all'applicazione di esempio, può essere usata anche come punto di partenza o riferimento. Usare l'applicazione di esempio associata come modello per le applicazioni oppure per determinare come organizzare le parti che compongono l'applicazione. Tornare ai principi e alla trattazione di questa guida riguardo ad architettura, opzioni tecnologiche e considerazioni sulle decisioni per soppesare queste scelte per l'applicazione.

È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità. Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.

## <a name="references"></a>Riferimenti
- **Scelta di .NET Core o .NET Framework per le app server**  
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
[avanti](modern-web-applications-characteristics.md)
