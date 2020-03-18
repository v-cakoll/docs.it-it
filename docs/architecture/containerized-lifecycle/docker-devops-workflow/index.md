---
title: Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft
description: Ciclo di vita delle applicazioni Docker in contenitori con flusso di lavoro DevOps della piattaforma e degli strumenti Microsoft con strumenti Microsoft
ms.date: 02/15/2019
ms.openlocfilehash: 6b138301a7e6794ce0a7b15957684b3b73e9f89f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70295742"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flusso di lavoro DevOps per le applicazioni Docker con strumenti Microsoft

*Microsoft Visual Studio, Azure DevOps Services, Team Foundation Server e Monitoraggio di Azure offrono un ecosistema completo per lo sviluppo e le operazioni IT in grado di fornire a ogni team gli strumenti per gestire i progetti e compilare, testare e distribuire rapidamente applicazioni in contenitori.*

Con Visual Studio e Azure DevOps Services nel cloud, insieme a Team Foundation Server in locale, i team di sviluppo possono compilare, testare e rilasciare con la massima produttività applicazioni in contenitori destinate a Windows o a Linux.

Gli strumenti Microsoft possono automatizzare la pipeline per implementazioni specifiche di applicazioni in contenitori (Docker, .NET Core o qualsiasi combinazione con altre piattaforme) da compilazioni globali, integrazione continua e test con Azure DevOps Services o Team Foundation Server a recapito continuo in ambienti Docker (sviluppo, gestione temporanea, produzione) e trasmissione di informazioni analitiche sui servizi al team di sviluppo tramite Monitoraggio di Azure. Ogni commit di codice può avviare una compilazione (integrazione continua) e distribuire automaticamente i servizi in ambienti in contenitori specifici (recapito continuo).

Sviluppatori e tester possono effettuare facilmente e rapidamente il provisioning di ambienti di sviluppo e test di produzione basati su Docker usando modelli in Microsoft Azure.

La complessità dello sviluppo di applicazioni in contenitori aumenta regolarmente a seconda della complessità aziendale e delle esigenze di scalabilità. Un buon esempio di questa complessità sono le applicazioni basate su architetture di microservizi. Per creare una soluzione di successo in un ambiente di questo tipo, il progetto deve automatizzare l'intero ciclo di vita, non solo la compilazione e la distribuzione, ma deve anche gestire le versioni insieme alla raccolta di dati di telemetria. Azure DevOps Services e Azure offrono le funzionalità seguenti:

- Gestione del codice sorgente di Azure DevOps Services/Team Foundation Server (in base al controllo della versione di Git o Team Foundation), pianificazione Agile (sono supportati Agile, Scrum e CMMI), integrazione continua, gestione del rilascio e altri strumenti per team Agile.

- Azure DevOps Services e Team Foundation Server includono un ecosistema potente e sempre più grande di estensioni proprietarie e di terze parti con cui è possibile creare facilmente una pipeline di integrazione continua, compilazione, test, distribuzione e gestione del rilascio per i microservizi.

- Eseguire test automatici nell'ambito della pipeline di compilazione in Azure DevOps Services.

- Azure DevOps Services può rafforzare il ciclo di vita DevOps con la distribuzione in più ambienti, non solo per gli ambienti di produzione, ma anche per ambienti di test, tra cui la sperimentazione A/B, le [versioni canary](https://martinfowler.com/bliki/CanaryRelease.html) e così via.

- Le organizzazioni possono effettuare facilmente il provisioning di contenitori Docker da immagini private archiviate in Registro Azure Container insieme a qualsiasi dipendenza dai componenti di Azure (dati, PaaS e così via) usando modelli di Azure Resource Manager con strumenti con cui hanno già familiarità.

>[!div class="step-by-step"]
>[Successivo](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[precedente](docker-application-outer-loop-devops-workflow.md)
