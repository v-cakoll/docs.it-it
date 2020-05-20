---
title: Ridimensionamento di applicazioni in contenitori e serverless
description: Ridimensionamento di applicazioni native del cloud con il servizio Azure Kubernetes per soddisfare le richieste degli utenti.
ms.date: 05/13/2020
ms.openlocfilehash: a5e1e8df785fd08901d9be41c0a06db35e09296b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613720"
---
# <a name="scaling-containers-and-serverless-applications"></a>Ridimensionamento di applicazioni in contenitori e serverless

Esistono due modi per ridimensionare un'applicazione: up o out. Il primo si riferisce all'aggiunta di capacità a una singola risorsa, mentre quest'ultimo si riferisce all'aggiunta di altre risorse per aumentare la capacità.

## <a name="the-simple-solution-scaling-up"></a>Soluzione semplice: scalabilità verticale

L'aggiornamento di un server host esistente con CPU, memoria, velocità di I/O del disco e velocità di I/O di rete maggiori è noto come *scalabilità verticale*. La scalabilità verticale di un'applicazione nativa del cloud prevede la scelta di risorse più idonee per il fornitore del cloud. Ad esempio, è possibile un nuovo pool di nodi con macchine virtuali di dimensioni maggiori nel cluster Kubernetes. Eseguire quindi la migrazione dei servizi in contenitori al nuovo pool.

Per le app senza server è necessario scegliere il [piano di funzioni Premium](https://docs.microsoft.com/azure/azure-functions/functions-scale) o le dimensioni delle istanze Premium da un piano di servizio App dedicato.

## <a name="scaling-out-cloud-native-apps"></a>Scalabilità orizzontale delle app native del cloud

Le applicazioni native del cloud spesso presentano fluttuazioni di grandi dimensioni e richiedono la scalabilità in un momento di preavviso. Si favoriscono la scalabilità orizzontale. La scalabilità orizzontale viene eseguita orizzontalmente aggiungendo altri computer (detti nodi) o istanze dell'applicazione a un cluster esistente. In Kubernetes è possibile ridimensionare manualmente le impostazioni di configurazione per l'app (ad esempio, il [ridimensionamento di un pool di nodi](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)) o la scalabilità automatica.

I cluster AKS possono essere ridimensionati automaticamente in uno dei due modi seguenti:

In primo luogo, la [scalabilità automatica del Pod orizzontale](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale#autoscale-pods) monitora la richiesta di risorse e ridimensiona automaticamente le repliche pod per soddisfarle. Quando il traffico aumenta, viene effettuato automaticamente il provisioning di altre repliche per la scalabilità orizzontale dei servizi. Allo stesso modo, quando la richiesta diminuisce, vengono rimossi per la scalabilità dei servizi. Si definisce la metrica su cui applicare la scalabilità, ad esempio l'utilizzo della CPU. È anche possibile specificare il numero minimo e massimo di repliche da eseguire. AKS monitora tale metrica e scala di conseguenza.

La funzionalità di [scalabilità automatica del cluster AKS](https://docs.microsoft.com/azure/aks/cluster-autoscaler) consente quindi di ridimensionare automaticamente i nodi di calcolo in un cluster Kubernetes per soddisfare la domanda. Con esso, è possibile aggiungere automaticamente nuove macchine virtuali al set di scalabilità di macchine virtuali di Azure sottostanti ogni volta che è necessaria una maggiore capacità di calcolo. Rimuove inoltre i nodi quando non sono più necessari.

La figura 3-13 Mostra la relazione tra questi due servizi di scalabilità.

![Scalabilità orizzontale di un piano di servizio app.](./media/aks-cluster-autoscaler.png)

**Figura 3-13**. Scalabilità orizzontale di un piano di servizio app.

Interagiscono, entrambi garantiscono un numero ottimale di istanze di contenitore e nodi di calcolo per supportare la domanda fluttuante. Il ridimensionamento automatico del Pod orizzontale ottimizza il numero di Pod necessari. Il servizio di scalabilità automatica del cluster ottimizza il numero di nodi necessari.

### <a name="scaling-azure-functions"></a>Ridimensionamento di Funzioni di Azure

Funzioni di Azure viene scalato automaticamente su richiesta. Le risorse del server vengono allocate e rimosse in modo dinamico in base al numero di eventi attivati. Vengono addebitate solo le risorse di calcolo utilizzate durante l'esecuzione delle funzioni. La fatturazione è basata sul numero di esecuzioni, sul tempo di esecuzione e sulla memoria usata.

Sebbene il piano a consumo predefinito fornisca una soluzione economica e scalabile per la maggior parte delle app, l'opzione Premium consente agli sviluppatori di flessibilità per i requisiti personalizzati di funzioni di Azure. L'aggiornamento al piano Premium consente di controllare le dimensioni delle istanze, le istanze pre-surriscaldate (per evitare ritardi di avvio a freddo) e le macchine virtuali dedicate.

>[!div class="step-by-step"]
>[Precedente](deploy-containers-azure.md) 
> [Avanti](other-deployment-options.md)
