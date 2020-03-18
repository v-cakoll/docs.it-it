---
title: Casi in cui distribuire i contenitori Windows in macchine virtuali di Azure (cloud IaaS)
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Quando distribuire i contenitori di Windows nelle macchine virtuali di Azure (cloud IaaS)When to deploy Windows Containers to Azure VMs (IaaS cloud)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577904"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Casi in cui distribuire i contenitori Windows in macchine virtuali di Azure (cloud IaaS)

If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS. Ciò significa che la gestione delle operazioni dell'infrastruttura, delle patch del sistema operativo delle macchine virtuali e della complessità dell'infrastruttura per le applicazioni altamente scalabili quando è necessario eseguire la distribuzione in più macchine virtuali in un'infrastruttura con bilanciamento del carico. Gli scenari principali per l'uso di contenitori di Windows in una macchina virtuale di Azure sono:The main scenarios for using Windows Containers in an Azure VM are:

- Ambiente di **sviluppo/test:** una macchina virtuale nel cloud è perfetta per lo sviluppo e il test nel cloud. È possibile creare o arrestare rapidamente l'ambiente in base alle proprie esigenze.

- Esigenze di **scalabilità piccole e medie:** in scenari in cui potrebbero essere necessarie solo un paio di macchine virtuali per l'ambiente di produzione, la gestione di un numero ridotto di macchine virtuali potrebbe essere conveniente fino a quando non è possibile passare ad ambienti PaaS più avanzati, ad esempio gli agenti di orchestrazione.

- **Ambiente di produzione con strumenti**di distribuzione esistenti: è possibile che si stia passando da un ambiente locale in cui è stato investito in strumenti per eseguire distribuzioni complesse a macchine virtuali o server bare metal (ad esempio Puppet o strumenti simili). To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs. Tuttavia, è consigliabile usare i contenitori di Windows come unità di distribuzione per migliorare l'esperienza di distribuzione.

>[!div class="step-by-step"]
>[Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[precedente](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
