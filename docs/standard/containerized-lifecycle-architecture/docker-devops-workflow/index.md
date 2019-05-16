---
title: Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft
description: Ciclo di vita di applicazioni Docker in contenitori con flusso di lavoro di Microsoft Platform e strumenti DevOps con strumenti Microsoft
ms.date: 02/15/2019
ms.openlocfilehash: 6b138301a7e6794ce0a7b15957684b3b73e9f89f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644810"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft

*Microsoft Visual Studio, servizi di Azure DevOps, Team Foundation Server e monitoraggio di Azure offrono che un ecosistema completo per lo sviluppo e operazioni IT in grado di fornire a ogni team gli strumenti per gestire i progetti e creare rapidamente, testare e distribuire in contenitori applicazioni.*

Con Visual Studio e servizi di Azure DevOps nel cloud, insieme a Team Foundation Server in locale, i team di sviluppo possono compilare, testare e rilasciare applicazioni in contenitori destinate a Windows o Linux in modo produttivo.

Gli strumenti Microsoft possono automatizzare la pipeline per implementazioni specifiche di applicazioni in contenitori, Docker, .NET Core o qualsiasi combinazione con altre piattaforme, da compilazioni globali e integrazione continua (CI) e i test con Team o servizi di Azure DevOps Foundation Server di distribuzione Continuo in ambienti Docker (sviluppo, Staging, produzione) e per trasmettere informazioni analitica sui servizi al team di sviluppo tramite Monitoraggio di Azure. Ogni commit di codice può avviare una compilazione (integrazione continua) e distribuire automaticamente i servizi in ambienti in contenitori specifici (recapito continuo).

Sviluppatori e tester possono effettuare facilmente e rapidamente il provisioning di ambienti di sviluppo e test di produzione basati su Docker usando modelli in Microsoft Azure.

La complessità dello sviluppo di applicazioni in contenitori aumenta regolarmente a seconda della complessità aziendale e delle esigenze di scalabilità. Un buon esempio di questa complessità sono le applicazioni basate su architetture di microservizi. Per la corretta in tale ambiente, il progetto deve automatizzare l'intero ciclo di vita, ovvero non solo la compilazione e distribuzione, ma è anche necessario gestire le versioni insieme alla raccolta dei dati di telemetria. Azure Services DevOps e Azure offrono le funzionalità seguenti:

- Azure gestione del codice sorgente DevOps Services/Team Foundation Server (basata su Git o Team Foundation Version Control), pianificazione Agile (Agile, Scrum e CMMI sono supportati), integrazione continua, la gestione del rilascio e altri strumenti per i team Agile.

- Azure DevOps Services e Team Foundation Server includono un ecosistema potenti e in continua crescito di estensioni di prima e di terze parti con cui è facilmente possibile costruire un elemento di configurazione, compilazione, test, recapito e pipeline di gestione per i microservizi di rilascio.

- Eseguire test automatizzati come parte della pipeline di compilazione in servizi di Azure DevOps.

- Servizi di Azure DevOps può rafforzare il ciclo di vita DevOps con la distribuzione in più ambienti, non solo per gli ambienti di produzione, ma anche per i test, inclusi A / sperimentazione, B [versioni canary](https://martinfowler.com/bliki/CanaryRelease.html)e così via.

- Le organizzazioni possono facilmente il provisioning dei contenitori Docker da immagini private archiviate nel registro contenitori di Azure insieme a qualsiasi dipendenza dai componenti di Azure (dati, PaaS e così via) usando i modelli di Azure Resource Manager con gli strumenti sono già dimestichezza.

>[!div class="step-by-step"]
>[Precedente](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[Successivo](docker-application-outer-loop-devops-workflow.md)
