---
title: Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft - Flusso di lavoro DevOps con strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b6a625cdf7a27748c4278c1b3f04db33a390712e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft

Microsoft Visual Studio, Visual Studio Team Services, Team Foundation Server e Application Insights offrono un ecosistema completo per lo sviluppo e le operazioni IT in grado di fornire a ogni team gli strumenti per gestire i progetti e compilare, testare e distribuire rapidamente applicazioni in contenitori.

Con Visual Studio e Visual Studio Team Services nel cloud, insieme a Team Foundation Server in locale, i team di sviluppo possono compilare, testare e rilasciare con la massima produttività applicazioni in contenitori destinate a qualsiasi piattaforma (Windows o ).

Gli strumenti Microsoft possono automatizzare la pipeline per implementazioni specifiche di applicazioni in contenitori, Docker, .NET Core o qualsiasi combinazione con altre piattaforme, da compilazioni globali, integrazione continua e test con Visual Studio Team Services o Team Foundation Server a recapito continuo in ambienti Docker (sviluppo, gestione temporanea, produzione) e trasmissione di informazioni analitiche sui servizi al team di sviluppo tramite Application Insights. Ogni commit di codice può avviare una compilazione (integrazione continua) e distribuire automaticamente i servizi in ambienti in contenitori specifici (recapito continuo).

Sviluppatori e tester possono effettuare facilmente e rapidamente il provisioning di ambienti di sviluppo e test di produzione basati su Docker usando modelli in Microsoft Azure.

La complessità dello sviluppo di applicazioni in contenitori aumenta regolarmente a seconda della complessità aziendale e delle esigenze di scalabilità. Un buon esempio di questo scenario sono le applicazioni basate su architetture di microservizi. Per creare una soluzione di successo in un ambiente di questo tipo, il progetto deve automatizzare l'intero ciclo di vita, non solo la compilazione e la distribuzione, ma deve anche gestire le versioni insieme alla raccolta di dati di telemetria. Visual Studio Team Services e Azure offrono le funzionalità seguenti:

-   Gestione del codice sorgente di Visual Studio Team Services/Team Foundation Server (in base al controllo della versione di Git o Team Foundation), pianificazione Agile (sono supportati Agile, Scrum e CMMI), integrazione continua, gestione del rilascio e altri strumenti per team Agile.

-   Visual Studio Team Services e Team Foundation Server includono un potente e sempre più grande ecosistema di estensioni proprietarie e di terze parti con cui è possibile creare facilmente una pipeline di integrazione continua, compilazione, test, distribuzione e gestione del rilascio per i microservizi.

-   Eseguire test automatici nell'ambito della pipeline di compilazione in Visual Studio Team Services.

-   Visual Studio Team Services può rafforzare il ciclo di vita DevOps con la distribuzione in più ambienti, non solo per gli ambienti di produzione, ma anche per ambienti di test, tra cui la sperimentazione A/B, le [versioni canary](http://martinfowler.com/bliki/CanaryRelease.html) e così via.

-   Le organizzazioni possono effettuare facilmente il provisioning di contenitori Docker da immagini private archiviate nel registro contenitori di Azure insieme a qualsiasi dipendenza dai componenti di Azure (dati, PaaS e così via) usando modelli di Azure Resource Manager con strumenti con cui hanno già familiarità.


>[!div class="step-by-step"]
[Indietro] (../design-develop-containerized-apps/set-up-windows-containers-with-powershell.md) [Avanti] (docker-application-outer-loop-devops-workflow.md)
