---
title: Quando distribuire i contenitori di Windows per Azure contenitore istanze ACI)
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Quando distribuire i contenitori di Windows per Azure contenitore istanze ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957951"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Quando distribuire i contenitori di Windows per Azure contenitore istanze ACI)

Proposta di valore principale è che è possibile distribuire i contenitori immediatamente a tale e non è necessario mantenere tale ambiente Azure istanze di contenitori, non dovrai aggiornamento/patch il sistema operativo sulla o le macchine virtuali, tutti i che è trasparente e appena distribuire contenitori in un ambiente pronto all'uso.

Motivi e degli scenari quando si desidera utilizzare ACI sono simili agli scenari principali quando si usano macchine virtuali di Azure con i contenitori, pertanto fondamentalmente, gli scenari principali per l'utilizzo di istanze di contenitori di Azure sono:

-   **Scenari di sviluppo/Test**
-   **Automazione di attività**
-   **Agenti CI/CD-ROM**
-   **Elaborazione batch di piccole e della scala**
-   **Nelle App web semplici**

Lo scenario di App web semplici è uno scenario equo per ACI ma tener conto di poiché in ACI può avere solo un'istanza singolo contenitore per ogni immagine contenitore, non sarà possibile la disponibilità elevata e avere solo una scalabilità limitata.

Tuttavia, anche quando ACI è considerato infrastruttura in quanto fornisce solo le istanze singolo contenitore, è un enorme vantaggio rispetto alle normali macchine virtuali di Azure con Windows Server. Con ACI, distribuire solo i contenitori in un ambiente di self-gestito e si paga solo per i contenitori. Non è necessario mantenere/aggiornamento/patch macchine virtuali, pertanto è una piattaforma molto migliorata per la maggior parte degli scenari in cui è possibile utilizzare le macchine virtuali con i contenitori. Utilizzando ACI è semplice, è sufficiente distribuire un contenitore, non è necessario creare un ambiente di VM distribuire solo i contenitori.

I principali vantaggi di Azure contenitore istanze ACI () sono:

-   Eseguire i contenitori di senza dover gestire i server
-   Aumentare la flessibilità con i contenitori su richiesta
-   Distribuzione di contenitori sul cloud con semplicità senza precedenti e la velocità, con un unico comando. 
-   Proteggere le applicazioni con isolamento hypervisor

In breve, con ACI è possibile sviluppare applicazioni fast senza gestire macchine virtuali o dover apprendere nuovi strumenti. È semplicemente l'applicazione, in un contenitore, in esecuzione nel cloud.

>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Successivo](when-to-deploy-windows-containers-to-service-fabric.md)
