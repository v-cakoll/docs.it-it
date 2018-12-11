---
title: Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft - Flusso di lavoro DevOps con strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: a78b6cbae88dcc39d7452a67a2bc5239135dedf9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128440"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft

Microsoft Visual Studio, servizi di Azure DevOps, Team Foundation Server e Application Insights offrono un ecosistema completo per lo sviluppo e operazioni IT che forniscono gli strumenti necessari per gestire i progetti e compilare, testare e distribuire rapidamente al team applicazioni nei contenitori.

Con Visual Studio e servizi di Azure DevOps nel cloud, insieme a Team Foundation Server in locale, i team di sviluppo possono compilare, testare e rilasciare applicazioni in contenitori destinate a qualsiasi piattaforma (Windows o Linux) in modo produttivo.

Gli strumenti Microsoft possono automatizzare la pipeline per implementazioni specifiche di applicazioni in contenitori, Docker, .NET Core o qualsiasi combinazione con altre piattaforme, da compilazioni globali e integrazione continua (CI) e i test con Team o servizi di Azure DevOps Foundation Server di distribuzione Continuo in ambienti Docker (sviluppo, Staging, produzione) e per trasmettere informazioni analitica sui servizi al team di sviluppo tramite Application Insights. Ogni commit di codice può avviare una compilazione (integrazione continua) e distribuire automaticamente i servizi in ambienti in contenitori specifici (recapito continuo).

Sviluppatori e tester possono effettuare facilmente e rapidamente il provisioning di ambienti di sviluppo e test di produzione basati su Docker usando modelli in Microsoft Azure.

La complessità dello sviluppo di applicazioni in contenitori aumenta regolarmente a seconda della complessità aziendale e delle esigenze di scalabilità. Un buon esempio di questo scenario sono le applicazioni basate su architetture di microservizi. Per la corretta in tale ambiente, il progetto deve automatizzare l'intero ciclo di vita, ovvero non solo la compilazione e distribuzione, ma è anche necessario gestire le versioni insieme alla raccolta dei dati di telemetria. Azure Services DevOps e Azure offrono le funzionalità seguenti:

-   Azure gestione del codice sorgente DevOps Services/Team Foundation Server (basata su Git o Team Foundation Version Control), pianificazione Agile (Agile, Scrum e CMMI sono supportati), integrazione continua, la gestione del rilascio e altri strumenti per i team Agile.

-   Azure DevOps Services/Team Foundation Server includono un ecosistema potenti e in continua crescito di estensioni di prima e di terze parti con cui è facilmente possibile costruire un elemento di configurazione, compilazione, test, recapito e pipeline di gestione per i microservizi di rilascio.

-   Eseguire test automatizzati come parte della pipeline di compilazione in servizi di Azure DevOps.

-   Servizi di Azure DevOps può rafforzare il ciclo di vita DevOps con la distribuzione in più ambienti, non solo per gli ambienti di produzione, ma anche per i test, inclusi A / sperimentazione, B [versioni canary](https://martinfowler.com/bliki/CanaryRelease.html)e così via.

-   Le organizzazioni possono effettuare facilmente il provisioning di contenitori Docker da immagini private archiviate nel registro contenitori di Azure insieme a qualsiasi dipendenza dai componenti di Azure (dati, PaaS e così via) usando modelli di Azure Resource Manager con strumenti con cui hanno già familiarità.

>[!div class="step-by-step"]
>[Precedente](../design-develop-containerized-apps/set-up-windows-containers-with-powershell.md)
>[Successivo](docker-application-outer-loop-devops-workflow.md)