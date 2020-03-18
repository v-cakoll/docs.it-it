---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Eseguire la migrazione a scenari di cloud ibridoMigrate to hybrid cloud scenarios
ms.date: 04/30/2018
ms.openlocfilehash: dcbb799a45609f8bb811866c4041951abf1fda8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937371"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Eseguire la migrazione a scenari di cloud ibrido

Alcune organizzazioni e aziende non possono eseguire la migrazione di alcune delle applicazioni a cloud pubblici come Microsoft Azure o qualsiasi altro cloud pubblico a causa di normative o dei propri criteri. Tuttavia, è probabile che qualsiasi organizzazione potrebbe trarre vantaggio dalla presenza di alcune delle applicazioni nel cloud pubblico e altre applicazioni in locale. Tuttavia, un ambiente misto può causare un'eccessiva complessità negli ambienti a causa di diverse piattaforme e tecnologie utilizzate nei cloud pubblici rispetto agli ambienti locali.

Microsoft offre la migliore soluzione cloud ibrida, in cui è possibile ottimizzare gli asset esistenti in locale e nel cloud pubblico, assicurando la coerenza in un cloud ibrido di Azure.Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud. È possibile ottimizzare le competenze esistenti e ottenere un approccio flessibile e unificato alla creazione di app che possono essere eseguite nel cloud o in locale, grazie ad Azure Stack (locale) e Azure (cloud pubblico).

Quando si tratta di sicurezza, è possibile centralizzare la gestione e la sicurezza nel cloud ibrido. È possibile ottenere il controllo su tutti gli asset, dal data center al cloud, fornendo l'accesso Single Sign-On alle app locali e cloud. A tale scopo, estendere Active Directory a un cloud ibrido e utilizzando la gestione delle identità.

Infine, è possibile distribuire e analizzare i dati senza problemi, usare gli stessi linguaggi di query per gli asset cloud e locali e applicare analisi e deep learning in Azure per arricchire i dati, indipendentemente dalla relativa origine.

## <a name="azure-stack"></a>Azure Stack

Azure Stack è una piattaforma cloud ibrida che consente di fornire servizi di Azure dal data center dell'organizzazione. Azure Stack è progettato per supportare nuove opzioni per le applicazioni moderne in scenari chiave, ad esempio ambienti perimetrali e non connessi o per soddisfare requisiti di sicurezza e conformità specifici.

Nella figura 4-13 viene illustrata una panoramica della vera piattaforma cloud ibrida offerta da Microsoft.

![Diagramma della piattaforma cloud ibrida Microsoft con Azure Stack e Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

**Figura 4-13.** Piattaforma cloud ibrida Microsoft con Azure Stack e Azure

Lo stack di Azure è disponibile in due opzioni di distribuzione per soddisfare le esigenze:Azure Stack is offered in two deployment options, to meet your needs:

- Sistemi integrati di Azure StackAzure Stack integrated systems

- Azure Stack Development Kit

### <a name="azure-stack-integrated-systems"></a>Sistemi integrati di Azure StackAzure Stack integrated systems

I sistemi integrati di Azure Stack sono offerti tramite una partnership di Microsoft e dei partner hardware. La partnership crea una soluzione che offre innovazione basata sul cloud, bilanciata con semplicità di gestione. Dato che Azure Stack è disponibile come sistema integrato di hardware e software, si ottiene il giusto livello di flessibilità e controllo, pur adottando l'innovazione dal cloud. Le dimensioni dei sistemi integrati di Azure Stack variano da 4 a 12 nodi e sono supportati congiuntamente dal partner hardware e da Microsoft. Usare i sistemi integrati di Azure Stack per implementare nuovi scenari per i carichi di lavoro di produzione.

### <a name="azure-stack-development-kit"></a>Azure Stack Development Kit

Microsoft Azure Stack Development Kit è una distribuzione a nodo singolo di Azure Stack, che è possibile usare per valutare e imparare a conoscere Azure Stack. You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure. Azure Stack Development Kit non è destinato all'uso in ambiente di produzione.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Cloud ibrido di AzureAzure hybrid cloud**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Account del servizio Active Directory per i contenitori di Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Creare un contenitore con supporto active DirectoryCreate a container with Active Directory support**

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- **Licenze per i vantaggi ibridi di AzureAzure Hybrid Benefit licensing**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Successivo](life-cycle-ci-cd-pipelines-devops-tools.md)
>[precedente](../walkthroughs-technical-get-started-overview.md)
