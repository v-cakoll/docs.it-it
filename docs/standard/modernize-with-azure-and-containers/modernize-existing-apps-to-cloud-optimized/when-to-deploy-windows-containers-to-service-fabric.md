---
title: Casi in cui distribuire i contenitori Windows in Service Fabric
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Casi in cui distribuire i contenitori Windows in Service Fabric
ms.date: 04/30/2018
ms.openlocfilehash: d29a358fb039eb3390910958b1b1080698d730e0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643355"
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Casi in cui distribuire i contenitori Windows in Service Fabric

Le applicazioni basate su contenitori Windows rapidamente dovrà utilizzare piattaforme allontana ulteriormente dalle macchine virtuali IaaS. Si tratta di migliorare la scalabilità automatica e scalabilità elevata e per ottenere miglioramenti significativi in un'esperienza di gestione completa per le distribuzioni, aggiornamenti, controllo delle versioni, rollback e monitoraggio dell'integrità. È possibile raggiungere questi obiettivi con l'agente di orchestrazione Azure Service Fabric, disponibile in cloud di Microsoft Azure, ma anche in locale o persino in un altro cloud.

Molte organizzazioni sono sollevamento e spostamento di applicazioni monolitiche esistenti per i contenitori per due motivi:

- Riduzioni dei costi, a causa di consolidamento e la rimozione di hardware esistente o dall'esecuzione di applicazioni su una densità maggiore.

- Un contratto di distribuzione coerente tra sviluppo e operazioni.

Cercando di ottenere riduzioni dei costi è comprensibile, ed è probabile che tutte le organizzazioni sono chasing tale obiettivo. Distribuzione uniforme è più difficile da valutare, ma è ugualmente importante. Un contratto di distribuzione coerente afferma che gli sviluppatori sono liberi di scegliere di usare la tecnologia e adeguato alle esigenze, e il team operativo Ottiene un unico modo per distribuire e gestire le applicazioni. Questo contratto consente di attenuare i problemi della presenza di operazioni di gestire la complessità di molte tecnologie diverse o imporre agli sviluppatori di usare solo alcune delle tecnologie. Essenzialmente, ogni applicazione viene inserita in un'immagine di distribuzione autonoma.

Alcune organizzazioni continueranno modernizzazione aggiungendo i microservizi (applicazioni Native del Cloud), ma molte altre organizzazioni interromperà qui (ottimizzato per il Cloud le applicazioni). Come illustrato nella figura 4-8, queste organizzazioni non spostare in architetture di microservizi in quanto si potrebbe non essere necessario. In ogni caso, sono già ottenere i vantaggi che usando Service Fabric e contenitori esperienza offre una gestione completa che include la distribuzione, aggiornamento, il controllo delle versioni, rollback e monitoraggio dell'integrità.

> ![Lift- and -shift un'applicazione di Service Fabric](./media/image8.png)
>
> **Figura 4-8.** Lift- and -shift un'applicazione di Service Fabric

Una chiave a Service Fabric consiste nel riutilizzare il codice esistente e lift- and -shift. Pertanto, è possibile eseguire la migrazione di applicazioni .NET Framework corrente, usando i contenitori Windows e distribuirle in Service Fabric. Sarà più semplice mantenere sarà relativa alla modernizzazione, alla fine, aggiungendo nuovi microservizi.

Durante il confronto di Service Fabric per altri agenti di orchestrazione, è importante evidenziare che Service Fabric è maturo in esecuzione dei servizi e applicazioni basate su Windows. Service Fabric è stato in esecuzione servizi basati su Windows e le applicazioni, inclusi i prodotti di livello 1 di importanza critica da Microsoft per gli anni. È verificato l'agente di orchestrazione prima di avere disponibilità a livello generale per i contenitori di Windows. Altri contenitori, ad esempio Kubernetes, DC/OS e Docker Swarm, sono più maturi in Linux, ma meno maturo rispetto alle applicazioni basate su Service Fabric per Windows e i contenitori di Windows.

L'obiettivo finale di Service Fabric consiste nel ridurre la complessità della creazione di applicazioni usando un approccio ai microservizi. Alla fine si desidera un microservizi per determinati tipi di applicazioni per evitare costose riprogettazioni. È possibile iniziare in piccolo quando necessario, deprecare servizi, aggiungere nuovi servizi e le evolvere l'applicazione a seconda dell'uso dei clienti. Esistono molti altri problemi che devono ancora essere risolti per rendere i microservizi più accessibili per la maggior parte degli sviluppatori. Se attualmente vengono semplicemente sollevamento e spostamento un'applicazione con i contenitori di Windows, ma si sta valutando l'aggiunta di microservizi basati su contenitori in futuro, ovvero la condizione ideale Service Fabric.

>[!div class="step-by-step"]
>[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
>[Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
