---
title: Ridimensionamento di contenitori e applicazioni senza server
description: Ridimensionamento di applicazioni native del cloud con il servizio Azure Kubernetes per soddisfare le richieste degli utenti aumentando le risorse di singoli computer o aumentando il numero di macchine virtuali in un cluster di applicazioni.
ms.date: 09/23/2019
ms.openlocfilehash: 2d0537fb3ed56beb4eccbf9b8c34a5d87793413b
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184799"
---
# <a name="scaling-containers-and-serverless-applications"></a>Ridimensionamento di contenitori e applicazioni senza server

È possibile ridimensionare un'applicazione in due modi tipici: scalabilità verticale e orizzontale. Il primo si riferisce all'aggiunta di funzionalità a un host, mentre quest'ultimo si riferisce all'aggiunta al numero totale di host. Un'analogia comune da usare per pensare a questo concetto è come ottenere se stessi e alcuni amici in città. Se si tratta solo di un amico, è possibile passare all'auto da corsa a due sedi. Tuttavia, se è costituito da tre o quattro, potrebbe essere necessario eseguire uno dei SUV o un minivan, aumentando la capacità. Quando il numero totale passa a una decina o più, tuttavia, probabilmente è necessario prendere più veicoli (a meno che qualcuno non guidi un bus), che illustra il concetto di scalabilità orizzontale aggiungendo più istanze (in questo caso, più veicoli). Ecco come si applicano alle applicazioni.

## <a name="the-simple-solution-scaling-up"></a>Soluzione semplice: scalabilità verticale

Il processo di aggiornamento dei server esistenti per fornire loro più risorse (CPU, memoria, velocità di I/O del disco, velocità di I/O della rete) è noto come *scalabilità verticale*. Nelle applicazioni native del cloud, la scalabilità verticale non si riferisce in genere all'acquisto e all'installazione di hardware effettivo sui computer fisici, così come la scelta di un piano più idoneo da un elenco di opzioni disponibili. Le app native del cloud vengono in genere aumentate modificando le dimensioni della macchina virtuale (VM) usate per ospitare i singoli nodi nel pool di nodi Kubernetes. I concetti relativi a Kubernetes come nodi, cluster e pod sono descritti più avanti nella [sezione successiva](leverage-containers-orchestrators.md). Azure supporta un'ampia gamma di dimensioni di VM che eseguono [Windows](https://docs.microsoft.com/azure/virtual-machines/windows/sizes?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json) e [Linux](https://docs.microsoft.com/azure/virtual-machines/linux/sizes). Per ridimensionare verticalmente l'applicazione, creare un nuovo pool di nodi con dimensioni di macchina virtuale del nodo maggiori e quindi migrare i carichi di lavoro nel nuovo pool. Questa operazione richiede [più pool di nodi per il cluster AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools), una funzionalità attualmente in anteprima. Per le app senza server è necessario scegliere un [piano Premium](https://docs.microsoft.com/azure/azure-functions/functions-scale) e le dimensioni delle istanze Premium oppure scegliendo un altro piano di servizio App dedicato.

## <a name="scaling-out-cloud-native-apps"></a>Scalabilità orizzontale delle app native del cloud

Le app native del cloud supportano la scalabilità orizzontale aggiungendo nodi o Pod aggiuntivi alle richieste di servizio. Questa operazione può essere eseguita manualmente modificando le impostazioni di configurazione per l'app, ad esempio il [ridimensionamento di un pool di nodi](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually), o tramite la *scalabilità*automatica. La scalabilità automatica regola le risorse usate da un'app per rispondere alla richiesta, in modo analogo a come un termostato risponde alla temperatura chiamando per un riscaldamento o un raffreddamento aggiuntivo. Quando si usa la scalabilità automatica, la scalabilità manuale è disabilitata.

I cluster AKS possono essere ridimensionati in uno dei due modi seguenti:

- Il servizio di [scalabilità](https://docs.microsoft.com/azure/aks/cluster-autoscaler) automatica del cluster controlla i pod che non possono essere pianificati nei nodi a causa di vincoli di risorse. Aggiunge altri nodi come richiesto.
- Il servizio di **scalabilità automatica di Pod orizzontale** usa il server delle metriche in un cluster Kubernetes per monitorare le richieste di risorse dei pod. Se un servizio necessita di più risorse, il ridimensionamento automatico aumenta il numero di Pod.

La figura 3-13 Mostra la relazione tra questi due servizi di scalabilità.

![Scalabilità orizzontale di un piano di servizio app.](./media/aks-cluster-autoscaler.png)

**Figura 3-13**. Scalabilità orizzontale di un piano di servizio app.

Questi servizi possono anche ridurre il numero di pod o nodi in base alle esigenze. Questi due servizi possono interagire insieme e spesso vengono distribuiti insieme in un cluster. In combinazione, il ridimensionamento automatico del Pod orizzontale si concentra sull'esecuzione del numero di Pod necessari per soddisfare le richieste dell'applicazione. Il ridimensionamento automatico del cluster si concentra sull'esecuzione del numero di nodi necessari per supportare i pod pianificati.

### <a name="scaling-azure-functions"></a>Ridimensionamento di funzioni di Azure

Funzioni di Azure supporta automaticamente il ridimensionamento. Il piano a consumo predefinito aggiunge e rimuove le risorse in modo dinamico in base al numero di eventi di trigger in arrivo. Vengono addebitate solo le risorse di calcolo usate quando le funzioni sono in esecuzione in base al numero di esecuzioni, al tempo di esecuzione e alla memoria usata. Usando il piano Premium, si ottengono queste stesse funzionalità, ma è anche possibile controllare le dimensioni dell'istanza usate, avere istanze già attivate (per evitare ritardi di avvio a freddo) e configurare VM dedicate su cui eseguire le funzioni. Sebbene la configurazione predefinita fornisca una soluzione economica e scalabile per la maggior parte delle app, l'opzione Premium consente agli sviluppatori di flessibilità per i requisiti di funzioni di Azure personalizzate.

## <a name="references"></a>Riferimenti

- [Più pool di nodi AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [Scalabilità automatica del cluster AKS](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [Esercitazione: Ridimensionare le applicazioni in AKS](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Scalabilità e hosting di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-scale)

>[!div class="step-by-step"]
>[Precedente](deploy-containers-azure.md)
>[Successivo](other-deployment-options.md)
