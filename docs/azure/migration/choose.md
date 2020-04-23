---
title: Scegliere l'opzione di hosting di Azure più adatta
description: Informazioni sul percorso di migrazione ad Azure più adatto per l'applicazione Web ASP.NET.
author: CESARDELATORRE
ms.author: cesardl
ms.date: 03/01/2020
ms.openlocfilehash: a8ad946b03f97272cb8685620858af6b21a372dc
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "82072109"
---
# <a name="choose-the-right-azure-hosting-option"></a>Scegliere l'opzione di hosting di Azure più adatta

Questo articolo illustra le considerazioni e i confronti tra le diverse opzioni disponibili in Azure quando si esegue la migrazione delle applicazioni .NET Framework esistenti dall'ambiente locale ad Azure.

Gli aspetti fondamentali da tenere presenti quando si esegue la migrazione ad Azure di applicazioni .NET esistenti sono:

1. Opzioni di calcolo
1. Opzioni di database
1. Considerazioni relative alla rete e alla sicurezza
1. Considerazioni relative all'autenticazione e all'autorizzazione

## <a name="compute-choices"></a>Opzioni di calcolo

Quando si esegue la migrazione ad Azure di applicazioni .NET Framework esistenti, sono possibili più scelte. Poiché tuttavia .NET Framework dipende da Windows, le scelte seguenti sono limitate ai servizi di calcolo basati su Windows.

La tabella seguente include diversi confronti e suggerimenti per scegliere il percorso di migrazione di calcolo adatto per l'applicazione .NET esistente.

|                 | Macchine virtuali di Azure | Servizio app di Azure | Contenitori Windows |
|-----------------|-----------|-------------------|--------------------|
|Utilizzo      |<ul><li>L'applicazione dipende fortemente dal server e dalle installazioni MSI locali.</li><li>Si vuole semplificare il più possibile il percorso di migrazione dell'applicazione</li></ul>|L'app non dipende in alcun modo dal server, è solo un'app Web ASP.NET pulita (MVC, WebForm) o un'app a più livelli (API Web, WCF) che accede a un server di database. |<ul><li>L'applicazione ha dipendenze dal server originale, ma tali dipendenze possono essere incluse nell'immagine Windows di Docker.</li><li>Si vuole modernizzare l'app in modo che sia pronta per il [cloud devops](../../architecture/modernize-with-azure-containers/modernize-existing-apps-to-cloud-optimized/reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</li></ul>|
|Vantaggi  |<ul><li>Percorso di migrazione molto semplice</li><li>Ambiente familiare. L'ambiente di distribuzione è una macchina virtuale, quindi è simile ai server locali.</li></ul> |Manutenzione PaaS continua, massima semplicità di gestione e ridimensionamento delle app in Azure. |<ul><li>Preparato per il futuro, cloud DevOps-Ready con dipendenze incluse nei contenitori dell'app.</li><li>Non è necessario eseguire il refactoring del codice .NET/C #.</li></ul> |
|Svantaggi             |Si tratta di IaaS. La manutenzione è costosa. È necessario gestire l'infrastruttura della macchina virtuale su rete, bilanciamento del carico, scalabilità orizzontale, gestione IIS e così via. |<ul><li>Non tutte le app sono [supportate](https://appmigration.microsoft.com/assessment)</li><li>Alcune app potrebbero dover essere sottoposte a refactoring e persino leggermente riprogettate, in modo da supportare app Azure servizio.</li></ul> |<ul><li>Curva di apprendimento delle competenze di Docker</li><li>Alcune impostazioni del codice e di configurazione dell'app vengono modificate</li></ul>|
|Requisiti |VM Windows Server con gli stessi requisiti dell'app per l'ambiente locale | Requisiti del servizio app Azure specificati in [controlli di conformità](https://github.com/Azure/App-Service-Migration-Assistant/wiki/Readiness-Checks). |<ul><li>[Motore Docker-Enterprise per Windows Server 2019](https://azuremarketplace.microsoft.com/marketplace/apps/cloud-infrastructure-services.docker-windows-2019)<br />o</li><li>[servizio Azure Container](https://azure.microsoft.com/services/container-service/) (agente di orchestrazione Kubernetes)<br />o<li>[Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)</li></ul> |
|Come eseguire la migrazione |Vedere [Eseguire la migrazione a macchine virtuali di Azure](vm.md) | Vedere [Eseguire la migrazione al servizio app di Azure](app-service.md) | Seguire le considerazioni, gli scenari e le procedure dettagliate illustrate nella pagina relativa alla [modernizzazione di app .NET esistenti con Azure e i contenitori di Windows eBook](https://aka.ms/liftandshiftwithcontainersebook) |

Il diagramma di flusso seguente mostra un albero delle decisioni quando si pianifica una migrazione ad Azure per le applicazioni .NET Framework esistenti. Se è possibile, provare A usare prima l'opzione A, ma l'opzione B è il percorso più semplice da eseguire.

![Diagramma di flusso che illustra l'albero delle decisioni relativo all'hosting](../media/migration/choose/decision-tree.png)

## <a name="database-choices"></a>Opzioni di database

Quando si esegue la migrazione di database relazionali ad Azure sono disponibili più opzioni. Per scegliere il percorso di migrazione del database adatto all'applicazione .NET esistente, vedere [Eseguire la migrazione del database SQL Server ad Azure](sql.md).

## <a name="networking-and-security-considerations"></a>Considerazioni relative alla rete e alla sicurezza

Quando si distribuiscono le applicazioni in un cloud pubblico come Microsoft Azure, potrebbe essere necessario isolare e proteggere determinate reti [creando reti perimetrali](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/), ad esempio una [rete perimetrale tra Azure e l'ambiente locale](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid) o una [rete perimetrale tra Azure e Internet](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-dmz). Le reti perimetrali possono essere implementate con [Rete virtuale di Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview).

Le reti virtuali di Azure consentono di:

- Creare un'infrastruttura ibrida facile da controllare
- Usare indirizzi IP e server DNS personali
- Proteggere le connessioni con una VPN IPSec o ExpressRoute
- Ottenere il controllo granulare del traffico tra subnet
- Creare topologie di rete sofisticate con appliance virtuali
- Ottieni un ambiente isolato e altamente sicuro per le tue applicazioni

Per iniziare a creare la rete virtuale, vedere la [documentazione di Rete virtuale di Azure](https://docs.microsoft.com/azure/virtual-network/).

## <a name="authentication-and-authorization-considerations-when-migrating-to-azure"></a>Considerazioni relative all'autenticazione e all'autorizzazione quando si esegue la migrazione ad Azure

Una delle preoccupazioni principali delle organizzazioni che passano al cloud è la sicurezza. La maggior parte delle aziende ha investito una notevole quantità di tempo, denaro e ingegneria nella progettazione e nello sviluppo di un modello di sicurezza ed è importante che siano in grado di sfruttare gli investimenti esistenti, ad esempio gli archivi di identità e le soluzioni Single Sign-On.

Molte applicazioni .NET B2E aziendali esistenti in esecuzione in locale usano Active Directory per l'autenticazione e la gestione delle identità. Azure AD Connect consente di integrare le directory locali con Azure Active Directory. Per iniziare, vedere [Integrare le directory locali con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

Per una maggiore pianificazione relativa ad Azure Active Directory, vedere [Requisiti per la soluzione ibrida di gestione delle identità](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-business-needs).

Le altre opzioni per il protocollo di autenticazione sono [OAuth](https://en.wikipedia.org/wiki/OAuth) e [OpenID](https://en.wikipedia.org/wiki/OpenID), che sono comuni nelle applicazioni rivolte agli utenti. Quando si usano database di identità autonomi, ad esempio un database SQL di identità ASP.NET di cui viene eseguito il wrapping con IdentityServer4 tramite OAuth, in genere non è necessaria la connettività ai database o alle directory locali.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Eseguire la migrazione di un'applicazione Web ASP.NET al servizio app di Azure](app-service.md)
