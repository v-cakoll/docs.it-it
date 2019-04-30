---
title: Eseguire la migrazione a scenari di cloud ibrido
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Eseguire la migrazione a scenari di cloud ibrido
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b04c6edecf5b63f191cb2e0f808fb1d0f801d0a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936728"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Eseguire la migrazione a scenari di cloud ibrido

Non è possibile eseguire la migrazione di alcune organizzazioni e aziende alcune delle proprie applicazioni per cloud pubblici, ad esempio Microsoft Azure o qualsiasi altro cloud pubblico a causa delle normative o i propri criteri. Tuttavia, è probabile che qualsiasi organizzazione potrebbe trarre vantaggio dalla disponibilità di alcune delle proprie applicazioni nel cloud pubblico e altre applicazioni in locale. Ma può causare un ambiente misto complessità eccessiva negli ambienti a causa di diverse piattaforme e tecnologie utilizzate in cloud pubblici e ambienti locali.

Microsoft offre la migliore soluzione cloud ibrida, uno in cui è possibile ottimizzare le risorse esistenti in locale e nel cloud pubblico, mentre garantire la coerenza in un cloud ibrido di Azure. È possibile ottimizzare le competenze esistenti e Ottieni un approccio flessibile e unificato alla creazione di App che è possibile eseguire nel cloud o in locale, grazie a Azure Stack (locale) e Azure (cloud pubblico).

Quando si parla di sicurezza, è possibile centralizzare sicurezza e gestione tra il cloud ibrido. È possibile ottenere il controllo su tutti gli asset, dal Data Center nel cloud, fornendo l'accesso single sign-on in locale e le app cloud. A tale scopo mediante l'estensione Active Directory per un cloud ibrido e usando la gestione delle identità.

Infine, è possibile distribuire e analizza con facilità i dati, usare gli stessi linguaggi di query per gli asset locali e cloud e applicare analitica e apprendimento avanzato in Azure per arricchire i dati, indipendentemente dalla relativa origine.

## <a name="azure-stack"></a>Azure Stack

Azure Stack è una piattaforma di cloud ibrido che ti permette di offrire servizi di Azure dal Data Center dell'organizzazione. Azure Stack è progettato per supportare le nuove opzioni per le applicazioni moderne in scenari chiave, ad esempio edge e gli ambienti non connessi o sicurezza e conformità di requisiti specifici.

Figura 4-13 mostra una panoramica della piattaforma di cloud ibrido davvero offerte da Microsoft.

![Piattaforma di cloud ibrido Microsoft con Azure Stack e Azure](./media/image13.jpg)

> **Figura 4-13.** Piattaforma di cloud ibrido Microsoft con Azure Stack e Azure

Azure Stack è disponibile in due opzioni di distribuzione, in base alle esigenze:

- Sistemi integrati di Azure Stack

- Azure Stack Development Kit

### <a name="azure-stack-integrated-systems"></a>Sistemi integrati di Azure Stack

Sistemi integrati di Stack di Azure sono disponibili tramite una collaborazione dei partner Microsoft e hardware. La relazione viene creata una soluzione che offre l'innovazione paced cloud bilanciata con semplicità di gestione. Perché Azure Stack è disponibile come sistema integrato di hardware e software, otterrai la giusta quantità di flessibilità e controllo, durante l'adozione comunque l'innovazione dal cloud. Sistemi Azure Stack integrati dimensioni variano da 4 a 12 nodi e congiuntamente supportati dai partner hardware e Microsoft. Usare i sistemi integrati di Azure Stack per implementare nuovi scenari per i carichi di lavoro di produzione.

### <a name="azure-stack-development-kit"></a>Azure Stack Development Kit

Microsoft Azure Stack Development Kit è una distribuzione a nodo singolo di Azure Stack, che è possibile usare per valutare e ottenere informazioni su Azure Stack. È anche possibile usare Azure Stack Development Kit come un ambiente di sviluppo, in cui è possibile sviluppare usando le API e strumenti che siano coerenti con Azure. Azure Stack Development Kit non deve essere utilizzato come un ambiente di produzione.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Cloud ibrido di Azure**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Account del servizio Active Directory per i contenitori Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Creare un contenitore con supporto di Active Directory**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Azure vantaggio Hybrid Use**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Precedente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Successivo](../walkthroughs-technical-get-started-overview.md)
