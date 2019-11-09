---
title: Quando distribuire i contenitori di Windows in istanze di contenitore di Azure (ACI)
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Quando distribuire i contenitori di Windows in istanze di contenitore di Azure (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577934"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Quando distribuire i contenitori di Windows in istanze di contenitore di Azure (ACI)

Istanze di contenitore di Azure la proposta di valore principale è che è possibile distribuire immediatamente i contenitori e non è necessario mantenere tale ambiente, non è necessario aggiornare/applicare patch al sistema operativo o alle macchine virtuali sottostanti, tutto trasparente ed è sufficiente distribuire i contenitori in un ambiente pronto per l'uso.

I motivi e gli scenari in cui si vuole usare ACI sono simili agli scenari principali quando si usano macchine virtuali di Azure con contenitori, quindi fondamentalmente gli scenari principali per l'uso di istanze di contenitore di Azure sono:

- **Scenari di sviluppo/test**
- **Automazione delle attività**
- **Agenti CI/CD**
- **Elaborazione batch ridotta/scalabile**
- **App Web semplici**

Lo scenario di app Web semplici è uno scenario equo per ACI, ma tenere presente che, poiché in ACI è possibile avere una sola istanza di contenitore per ogni immagine del contenitore, non si avrà una disponibilità elevata e si avrà solo una scalabilità limitata.

Tuttavia, anche quando ACI viene considerato infrastruttura perché fornisce solo istanze di contenitore singolo, si verifica un enorme vantaggio rispetto alle normali macchine virtuali di Azure con Windows Server. Con ACI è sufficiente distribuire i contenitori in un ambiente autogestito ed è sufficiente pagare per questi contenitori. Non è necessario gestire/aggiornare/applicare patch alle macchine virtuali, quindi è una piattaforma molto migliore per la maggior parte degli scenari in cui è possibile usare macchine virtuali con i contenitori. L'uso di ACI è semplice, ma è sufficiente distribuire un contenitore. non è necessario creare un ambiente di macchina virtuale in cui si distribuiscono semplicemente i contenitori.

I principali vantaggi delle istanze di contenitore di Azure sono:

- Esegui contenitori senza gestire i server
- Aumento della flessibilità con i contenitori su richiesta
- Distribuisci i contenitori nel cloud con semplicità e velocità senza precedenti, con un unico comando.
- Proteggere le applicazioni con isolamento hypervisor

In breve, con ACI è possibile sviluppare rapidamente app senza dover gestire macchine virtuali o dover apprendere nuovi strumenti. Si tratta solo dell'applicazione, in un contenitore, in esecuzione nel cloud.

> [!div class="step-by-step"]
> [Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
