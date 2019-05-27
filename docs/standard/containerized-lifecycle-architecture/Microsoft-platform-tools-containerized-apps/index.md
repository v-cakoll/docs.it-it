---
title: Introduzione alla piattaforma e agli strumenti Microsoft per le app in contenitori
description: Conoscere le offerte di Microsoft per il supporto del ciclo di vita delle applicazioni Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 6907528a5d7ff354a312e7575531b9c608cb479f
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195590"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Introduzione alla piattaforma Microsoft e strumenti per le App in contenitori

*Visione artificiale: Creare un adattabile, di livello aziendale in contenitori ciclo di vita dell'applicazione che si estende su sviluppo e operazioni IT, gestione di produzione.*

La figura 3-1 mostra gli elementi fondanti del ciclo di vita delle app Docker, classificati per tipo di lavoro svolto da più team (sviluppo di app, processi dell'infrastruttura DevOps e gestione e operazioni IT). In genere nell'organizzazione i profili dell'utente tipo responsabile per ogni area sono diversi. Lo stesso vale per le competenze.

![Strumenti di Microsoft. Per il carico di lavoro di elaborazione/progettazione: Motore di docker per Windows, Visual Studio e Visual Studio Code, .NET Core, Azure Kubernetes Service. Per il carico di lavoro di compilazione/Test/spedizione: Azure DevOps, Team Foundation Server, Docker CLI, Azure Kubernetes Service. Per il carico di lavoro di esecuzione/monitoraggio/gestire: Monitoraggio, portale di Azure Kubernetes servizi di Azure Service Fabric di Azure, altri agenti di orchestrazione.](./media/image1.png)

**Figura 3-1.** Concetti di base del ciclo di vita per applicazioni Docker in contenitori con piattaforma e strumenti Microsoft

Un flusso di lavoro di ciclo di vita Docker in contenitori possa essere inizialmente prescrittivo in base a "per impostazione predefinita del prodotto scelte," rendendo più semplice per gli sviluppatori per iniziare più rapidamente, ma è fondamentale che dietro le quinte deve essere un framework aperto in modo che sia un flusso di lavoro flessibile in grado di adattarsi ai diversi contesti di ogni organizzazione o azienda. L'infrastruttura del flusso di lavoro (componenti e prodotti) deve essere sufficientemente flessibile per gestire l'ambiente che avrà ogni azienda in futuro ed essere addirittura in grado di scambiare prodotti di sviluppo o DevOps gli uni con gli altri. La flessibilità, l'apertura e l'ampia scelta di tecnologie nella piattaforma e nell'infrastruttura sono esattamente le priorità di Microsoft per le applicazioni Docker in contenitori, come spiegato nei capitoli seguenti.

La tabella 3-1 mostra che l'obiettivo di Microsoft DevOps per applicazioni Docker in contenitori è definire un flusso di lavoro DevOps aperto che permetta di scegliere quali prodotti usare per ogni fase (Microsoft o terze parti), con un flusso di lavoro semplificato in grado di fornire "prodotti per impostazione predefinita" già connessi. In questo modo, è possibile avviare rapidamente il flusso di lavoro DevOps di livello aziendale per app Docker.

**Tabella 3-1.** Flussi di lavoro DevOps, open a qualsiasi tecnologia

| Host | Tecnologie Microsoft | Terze parti - Collegabili ad Azure |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Piattaforma per app Docker   | • Microsoft Visual Studio e Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Kubernetes Service (AKS)<br /> • Azure Service Fabric<br /> • Registro Azure Container<br /> | • Qualsiasi editor di codice (ad esempio, Sublime)<br /> • Qualsiasi linguaggio (Node.js, Java, Go e così via)<br /> • Qualsiasi agente di orchestrazione e utilità di pianificazione<br /> • Qualsiasi registro Docker<br /> |
| DevOps per app Docker     | • Servizi di azure DevOps<br /> • Microsoft Team Foundation Server<br /> • Azure Kubernetes Service (AKS)<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion e così via<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI e così via<br /> • Docker Datacenter, Docker Swarm, Mesos DC/OS, Kubernetes e così via in locale<br /> |
| Gestione e monitoraggio  | Monitorare azure • | • Marathon, Chronos e così via<br />|

La piattaforma e gli strumenti Microsoft per app Docker in contenitori, come definito nella tabella 3-1, includono i componenti seguenti:

- **Piattaforma per lo sviluppo di app Docker** Sviluppo di un servizio o di una raccolta di servizi che costituiscono un'"app". La piattaforma di sviluppo fornisce tutte le attività necessarie agli sviluppatori prima di inserire il codice in un repository di codice condiviso. I servizi di sviluppo, distribuiti come contenitori, sono simili allo sviluppo della stessa App o servizi senza Docker. Continuare a usare il linguaggio preferito (.NET, Node. js, Go e così via) e l'editor preferito o l'IDE come Visual Studio o Visual Studio Code. Tuttavia, invece di considerare Docker una destinazione di distribuzione, è necessario sviluppare i servizi nell'ambiente Docker. È necessario eseguire la compilazione, i test e il debug del codice nei contenitori in locale, fornendo l'ambiente di destinazione in fase di sviluppo. Fornendo l'ambiente di destinazione in locale, i contenitori Docker eseguono la configurazione in modo da contribuire notevolmente al miglioramento del ciclo di vita DevOps. Visual Studio e Visual Studio Code includono estensioni per l'integrazione di contenitori Docker nel processo di sviluppo.

- **DevOps per App Docker** gli sviluppatori creano applicazioni Docker possono usare [servizi di Azure DevOps](https://azure.microsoft.com/services/devops/) o qualsiasi altro prodotto di terze parti, come Jenkins, per compilare un'applicazione automatica completa del ciclo di vita Management (ALM).

  Con i servizi di Azure DevOps, gli sviluppatori possono creare incentrata su contenitori controllare DevOps per un processo rapido e iterativo che copre del codice sorgente ovunque (servizi DevOps di Azure-Git, GitHub, qualsiasi repository Git remoto o Subversion), integrazione continua (CI) , unit test, test di integrazione tra container o servizi, recapito continuo (CD) e la gestione del rilascio (RM). Gli sviluppatori possono automatizzare il rilascio delle applicazioni Docker in Azure Kubernetes Service (AKS), dallo sviluppo agli ambienti di staging e produzione.

- **Gestione e monitoraggio** IT può gestire e monitorare le applicazioni di produzione e i servizi in diversi modi, l'integrazione di entrambe le prospettive in un'esperienza consolidata.

  - **Portale di Azure** se si usano gli agenti di orchestrazione open source, Azure Kubernetes Service (AKS), Service Fabric e altri agenti di orchestrazione consentono di configurare e gestire gli ambienti Docker. Se si usa Azure Service Fabric, lo strumento Service Fabric Explorer permette di visualizzare e configurare il cluster.

  - **Strumenti Docker** È possibile gestire le applicazioni contenitore usando strumenti familiari. Non è necessario modificare le procedure di gestione di Docker esistenti per spostare i carichi di lavoro dei contenitori nel cloud. Usare gli strumenti di gestione delle applicazioni con cui si ha già familiarità e connettersi tramite gli endpoint API standard per l'agente di orchestrazione scelto. È anche possibile usare strumenti di terze parti per gestire le applicazioni Docker, come Docker Datacenter o addirittura strumenti Docker dell'interfaccia della riga di comando. 

    Anche se si ha familiarità con i comandi di Linux, è possibile gestire le applicazioni contenitore usando PowerShell e Microsoft Windows con una riga di comando del sottosistema di Linux e i prodotti (Docker, Kubernetes...) ai client in esecuzione su questa funzionalità di sottosistema Linux. Verranno fornite ulteriori informazioni sull'utilizzo di questi strumenti nel sottosistema Linux usando il sistema operativo Windows di Microsoft preferito più avanti in questo libro.

  - **Strumenti open source** AKS perché espone gli endpoint API standard per il motore di orchestrazione, gli strumenti più diffusi sono compatibili con servizio contenitore di AZURE e, nella maggior parte dei casi, funzioneranno per impostazione predefinita la casella, inclusi visualizzatori, monitoraggio, strumenti da riga di comando e addirittura strumenti futuri appena diventano disponibili.

  - **Monitoraggio di Azure** soluzione di Azure è a monitorare ogni aspetto dell'ambiente di produzione. È possibile monitorare le applicazioni di produzione Docker configurando semplicemente il SDK nei servizi in modo che sia possibile ottenere i dati di log generati dal sistema per le applicazioni.

In questo modo, Microsoft offre elementi di base completi per un ciclo di vita delle applicazioni Docker in contenitori end-to-end. È tuttavia *una raccolta di prodotti e tecnologie che consentono la selezione e integrazione con strumenti e processi*. La flessibilità di un ampio approccio con tutta la potenza e la completezza delle funzionalità pone Microsoft in una solida posizione per lo sviluppo di applicazioni Docker in contenitori.

>[!div class="step-by-step"]
>[Precedente](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Successivo](../design-develop-containerized-apps/index.md)
