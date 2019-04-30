---
title: Casi in cui distribuire i contenitori Windows in macchine virtuali di Azure (cloud IaaS)
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Casi in cui distribuire i contenitori di Windows per le VM di Azure (cloud IaaS)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 51217e2c94fd9727c8f7907e791cdebaec98f14f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011957"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Casi in cui distribuire i contenitori Windows in macchine virtuali di Azure (cloud IaaS)

Se l'organizzazione Usa macchine virtuali di Azure, anche se si usa anche i contenitori di Windows, si è ancora occuparsi della tecnologia IaaS. Ciò significa che la gestione di operazioni sull'infrastruttura, patch del sistema operativo della macchina virtuale e la complessità dell'infrastruttura per applicazioni a scalabilità elevata quando è necessario distribuire più macchine virtuali in un'infrastruttura con bilanciamento di carico. Gli scenari principali per l'uso dei contenitori di Windows in una VM di Azure sono:

- **Ambiente di sviluppo/test**: Una macchina virtuale nel cloud è ideale per sviluppo e test nel cloud. Rapidamente, è possibile creare o arrestare l'ambiente in base alle esigenze.

- **Necessita di scalabilità di piccole e medie dimensioni**: In scenari in cui potrebbe essere necessario un paio di macchine virtuali nell'ambiente di produzione, gestisce un numero ridotto di macchine virtuali potrebbe essere conveniente fino a quando non è possibile spostare in ambienti PaaS più avanzati, quali gli agenti di orchestrazione.

- **Ambiente di produzione con gli strumenti di distribuzione esistenti**: Si potrebbe essere lo spostamento da un ambiente locale in cui si è investito in strumenti di rendere le distribuzioni complesse in macchine virtuali o server bare metal, come Puppet o strumenti simili. Per spostare nel cloud con modifiche minime per le procedure di distribuzione di ambiente di produzione, si potrebbe continuare a usare questi strumenti per distribuire in macchine virtuali di Azure. Tuttavia, è opportuno usare i contenitori di Windows come unità di distribuzione per migliorare l'esperienza di distribuzione.

>[!div class="step-by-step"]
>[Precedente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Successivo](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)