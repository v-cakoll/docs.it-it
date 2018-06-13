---
title: Quando distribuire i contenitori di Windows in macchine virtuali di Azure (IaaS cloud)
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Quando distribuire i contenitori di Windows in macchine virtuali di Azure (cloud IaaS)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 7472745577f414062b460fd71ab45bae85d7a62e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958021"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Quando distribuire i contenitori di Windows in macchine virtuali di Azure (IaaS cloud)

Se l'organizzazione utilizza macchine virtuali di Azure, anche se si utilizza anche i contenitori di Windows, sono comunque trattare IaaS. Ciò significa che la gestione di operazioni dell'infrastruttura, patch del sistema operativo VM e la complessità dell'infrastruttura per applicazioni estremamente scalabili quando è necessario distribuire più macchine virtuali in un'infrastruttura con bilanciamento del carico. Gli scenari principali per l'utilizzo di contenitori di Windows in una macchina virtuale di Azure sono:

-   **Ambiente di sviluppo/test**: una macchina virtuale nel cloud è ideale per lo sviluppo e test nel cloud. Rapidamente, è possibile creare o arrestare l'ambiente in base alle esigenze.

-   **La scalabilità di piccola e Media deve**: In scenari in cui potrebbe essere necessario solo un paio di macchine virtuali per l'ambiente di produzione, gestisce un numero ridotto di macchine virtuali potrebbe essere conveniente fino a quando non è possibile spostare in ambienti di PaaS più avanzati, ad esempio orchestrators.

-   **Ambiente di produzione con gli strumenti di distribuzione esistenti**: si potrebbe spostare da un ambiente locale in cui si è investito in strumenti per eseguire distribuzioni complesse per le macchine virtuali o i server bare metal (ad esempio Puppet o strumenti simili inclusi). Per spostare nel cloud con modifiche minime per le procedure di distribuzione di ambiente di produzione, si potrebbe continuare a utilizzare questi strumenti per distribuire macchine virtuali di Azure. Tuttavia, è opportuno come utilizzare i contenitori di Windows come unità di distribuzione per migliorare l'esperienza di distribuzione.

>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Successivo](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
