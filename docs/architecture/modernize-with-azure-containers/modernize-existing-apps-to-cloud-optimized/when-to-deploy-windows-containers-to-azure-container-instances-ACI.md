---
title: Quando distribuire i contenitori di Windows alle istanze del contenitore di Azure (ACI)When to deploy Windows Containers to Azure Container Instances (ACI)
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Quando distribuire i contenitori di Windows alle istanze del contenitore di Azure (ACI)When to deploy Windows Containers to Azure Container Instances (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 6c889db6f0475f24a196144c7fb62faec4c173ed
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989155"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Quando distribuire i contenitori di Windows alle istanze del contenitore di Azure (ACI)When to deploy Windows Containers to Azure Container Instances (ACI)

Proposta di valore principale di Istanze contenitore di Azure è che è possibile distribuire immediatamente i contenitori e non è necessario gestire tale ambiente, non è necessario aggiornare/applicare la patch del sistema operativo o delle macchine virtuali sottostanti, tutto ciò che è trasparente e si distribuiscono semplicemente i contenitori in un ambiente pronto per l'uso.

I motivi e gli scenari in cui si vuole usare l'aCI sono simili agli scenari principali quando si usano macchine virtuali di Azure con contenitori, pertanto, fondamentalmente, gli scenari principali per l'uso di istanze del contenitore di Azure sono:The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:

- **Scenari di sviluppo/test**
- **Automazione delle attività**
- **Agenti CI/CD**
- **Elaborazione batch su piccola/scala**
- **App Web semplici**

Lo scenario di app Web semplici è uno scenario equo per ACI, ma tenere in considerazione che, poiché in ACI è possibile avere una sola istanza del contenitore per ogni immagine del contenitore, non si avrà disponibilità elevata e solo una scalabilità limitata.

Tuttavia, anche quando ACI è considerato infrastruttura perché fornisce solo istanze di un singolo contenitore, c'è un enorme vantaggio rispetto alle normali macchine virtuali di Azure con Windows Server.However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server. Con ACI, è sufficiente distribuire i contenitori in un ambiente self-maintained e si paga solo per quei contenitori. Non è necessario gestire/aggiornare/applicare patch alle macchine virtuali, pertanto è una piattaforma molto migliore per la maggior parte degli scenari in cui potrebbero usare macchine virtuali con contenitori. L'uso di ACI è semplice, basta distribuire un contenitore, non è necessario creare un ambiente VM per distribuire semplicemente i contenitori.

I principali vantaggi delle istanze del contenitore di Azure (ACI) sono:The main benefits of Azure Container Instances (ACI) are:

- Eseguire i contenitori senza gestire i serverRun containers without managing servers
- Aumenta l'agilità con i contenitori su richiesta
- Distribuisci i contenitori nel cloud con semplicità e velocità senza precedenti, con un unico comando.
- Applicazioni sicure con isolamento dell'hypervisor

In breve, con ACI è possibile sviluppare applicazioni rapidamente senza gestire macchine virtuali o dover imparare nuovi strumenti. È solo la tua applicazione, in un contenitore, in esecuzione nel cloud.

> [!div class="step-by-step"]
> [Successivo](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
