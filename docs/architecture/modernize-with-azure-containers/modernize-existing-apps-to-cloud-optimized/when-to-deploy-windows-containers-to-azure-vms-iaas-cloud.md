---
title: Casi in cui distribuire i contenitori Windows in macchine virtuali di Azure (cloud IaaS)
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Quando distribuire i contenitori di Windows in macchine virtuali di Azure (IaaS cloud)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577904"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Casi in cui distribuire i contenitori Windows in macchine virtuali di Azure (cloud IaaS)

Se l'organizzazione usa VM di Azure, anche se si usano i contenitori di Windows, si sta ancora usando IaaS. Ciò significa che le operazioni di infrastruttura, le patch del sistema operativo della macchina virtuale e la complessità dell'infrastruttura per le applicazioni altamente scalabili quando è necessario eseguire la distribuzione in più macchine virtuali in un'infrastruttura con bilanciamento del carico. Gli scenari principali per l'uso dei contenitori di Windows in una macchina virtuale di Azure sono i seguenti:

- **Ambiente di sviluppo/test**: una macchina virtuale nel cloud è ideale per lo sviluppo e il test nel cloud. È possibile creare o arrestare rapidamente l'ambiente in base alle esigenze.

- **Esigenze di scalabilità ridotta e media**: negli scenari in cui potrebbero essere necessarie solo un paio di macchine virtuali per l'ambiente di produzione, la gestione di un numero ridotto di macchine virtuali può essere conveniente fino a quando non è possibile passare a ambienti PaaS più avanzati, come gli agenti di orchestrazione.

- **Ambiente di produzione con gli strumenti di distribuzione esistenti**: è possibile che si stia migrando da un ambiente locale in cui si è investito in strumenti per creare distribuzioni complesse in macchine virtuali o Server Bare Metal, ad esempio marionette o strumenti simili. Per passare al cloud con modifiche minime alle procedure di distribuzione dell'ambiente di produzione, è possibile continuare a usare questi strumenti per la distribuzione in macchine virtuali di Azure. Tuttavia, è consigliabile usare i contenitori di Windows come unità di distribuzione per migliorare l'esperienza di distribuzione.

>[!div class="step-by-step"]
>[Precedente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Successivo](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
