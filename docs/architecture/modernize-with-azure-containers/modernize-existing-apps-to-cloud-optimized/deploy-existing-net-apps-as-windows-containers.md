---
title: Distribuire app .NET esistenti come contenitori Windows
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Distribuire le app .NET esistenti come contenitori di WindowsDeploy existing .NET apps as Windows containers
ms.date: 04/29/2018
ms.openlocfilehash: c99c2e756320fc886203efcbf98a81e571d907e5
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987972"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Distribuire app .NET esistenti come contenitori Windows

Le distribuzioni basate su contenitori di Windows sono applicabili alle applicazioni ottimizzate per il cloud e alle applicazioni Cloud-Native.Deployments that are based on Windows Containers are applicable to Cloud-Optimized applications and Cloud-Native applications.

Tuttavia, in questa guida e soprattutto nelle sezioni seguenti, si concentra principalmente sull'utilizzo di contenitori di Windows per applicazioni *ottimizzate* per il cloud in cui non è necessario riprogettare l'applicazione.

## <a name="what-are-containers-linux-or-windows"></a>Informazioni sui contenitori (Linux o Windows)

I contenitori sono un modo per eseguire il wrapping di un'applicazione nel proprio pacchetto isolato. Nel relativo contenitore, l'applicazione non è interessata da applicazioni o processi esistenti all'esterno del contenitore. Tutto ciò da cui dipende l'esecuzione dell'applicazione quando un processo si trova all'interno del contenitore. Ovunque il contenitore possa essere spostato, i requisiti dell'applicazione saranno sempre soddisfatti, in termini di dipendenze dirette, perché è in bundle con tutto ciò che è necessario eseguire (dipendenze di libreria, runtime e così via).

La caratteristica principale di un contenitore è che rende l'ambiente lo stesso tra diverse distribuzioni perché il contenitore stesso viene fornito con tutte le dipendenze necessarie. È possibile eseguire il debug dell'applicazione nel computer e quindi distribuirla in un altro computer, con lo stesso ambiente garantito.

Un contenitore è un'istanza di un'immagine contenitore. Un'immagine contenitore è un modo per creare un pacchetto di un'app o un servizio (ad esempio uno snapshot) e quindi distribuirla in modo affidabile e riproducibile. Si potrebbe dire che Docker non è solo una tecnologia, è anche una filosofia e un processo.

Man mano che i contenitori diventano più comuni, stanno diventando un'"unità di distribuzione" a livello di settore.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vantaggi dei contenitori (Docker Engine su Linux o Windows)

La creazione di applicazioni utilizzando contenitori, che possono anche essere definiti come blocchi predefiniti leggeri, offre un aumento significativo dell'agilità per la creazione, la spedizione e l'esecuzione di qualsiasi applicazione in qualsiasi infrastruttura.

Con i contenitori, puoi portare qualsiasi app dallo sviluppo alla produzione con poche o nessuna modifica del codice, grazie all'integrazione di Docker tra gli strumenti di sviluppo Microsoft, i sistemi operativi e il cloud.

Quando si esegue la distribuzione in macchine virtuali semplici, è probabile che si disponga già di un metodo per la distribuzione di app ASP.NET nelle macchine virtuali. È probabile, tuttavia, che il metodo prevede più passaggi manuali o processi automatizzati complessi utilizzando uno strumento di distribuzione come Puppet o uno strumento simile. Potrebbe essere necessario eseguire attività come la modifica degli elementi di configurazione, la copia del contenuto dell'applicazione tra i server e l'esecuzione di programmi di installazione interattivi basati su configurazioni con estensione msi, seguite da test. Tutti questi passaggi nella distribuzione aggiungono tempo e rischi alle distribuzioni. Si otterranno errori ogni volta che una dipendenza non è presente nell'ambiente di destinazione.

Nei contenitori Windows, il processo di creazione del pacchetto delle applicazioni è completamente automatizzato. Contenitori di Windows si basa sulla piattaforma Docker, che offre aggiornamenti automatici e rollback per le distribuzioni di contenitori. Il miglioramento principale che si ottiene dall'utilizzo del motore Docker è che si creano immagini, che sono come istantanee dell'applicazione, con tutte le relative dipendenze. Le immagini sono immagini Docker (un'immagine del contenitore Windows, in questo caso). Le immagini vengono eseguite ASP.NET le app in contenitori, senza tornare al codice sorgente. Lo snapshot del contenitore diventa l'unità di distribuzione.

Molte organizzazioni stanno containerizzando le applicazioni monolitiche esistenti per i motivi seguenti:Many organizations are containerizing existing monolithic applications for the following reasons:

- **Libera agilità grazie a una migliore distribuzione.** I contenitori offrono un contratto di distribuzione coerente tra sviluppo e operazioni. Quando si utilizzano i contenitori, non si sente gli sviluppatori dire, "Funziona sul mio computer, perché non in produzione?" Possono dire, "Funziona come un contenitore, quindi verrà eseguito in produzione." L'applicazione in pacchetto, con tutte le relative dipendenze, può essere eseguita in qualsiasi ambiente basato su contenitori supportato. Verrà eseguito nel modo in cui è stato progettato l'esecuzione in tutte le destinazioni di distribuzione (dev, QA, staging, produzione). I contenitori eliminano la maggior parte degli attriti quando si spostano da una fase all'altra, il che migliora notevolmente la distribuzione ed è possibile spedire più velocemente.

- **Riduzione dei costi**. I contenitori comportano costi inferiori, grazie al consolidamento e alla rimozione dell'hardware esistente o all'esecuzione di applicazioni a una densità più elevata per unità di hardware.

- **Portabilità**. I contenitori sono modulari e portatili. I contenitori Docker sono supportati in qualsiasi sistema operativo server (Linux e Windows), in qualsiasi cloud pubblico principale (Microsoft Azure, Amazon AWS, Google, IBM) e in ambienti cloud locali e privati o ibridi.

- **Controllare**. I contenitori offrono un ambiente flessibile e sicuro controllato a livello di contenitore. Un contenitore può essere protetto, isolato e persino limitato impostando criteri dei vincoli di esecuzione nel contenitore. Come descritto in dettaglio nella sezione sui contenitori di Windows, i contenitori di Windows Server 2016 e Hyper-V offrono ulteriori opzioni di supporto aziendale.

Miglioramenti significativi in termini di agilità, portabilità e controllo in ultima analisi portano a riduzioni significative dei costi quando si utilizzano i contenitori per sviluppare e gestire le applicazioni.

## <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) che automatizza la distribuzione di applicazioni come contenitori portatili e autosufficienti che possono essere eseguiti nel cloud o in locale. Docker è anche un'[azienda](https://www.docker.com/) che promuove questa tecnologia e ne guida l'evoluzione. L'azienda lavora in collaborazione con fornitori di cloud, Linux e Windows, tra cui Microsoft.

![Diagramma che mostra come Docker distribuisce i contenitori nel cloud ibrido.](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**Figura 4-6.** Docker distribuisce contenitori a tutti i livelli del cloud ibrido

Per gli utenti che hanno familiarità con le macchine virtuali, i contenitori potrebbero sembrare notevolmente simili. Un contenitore esegue un sistema operativo, dispone di un file system ed è accessibile tramite una rete, proprio come un sistema di computer fisico o virtuale. Ciò premesso, la tecnologia e i concetti alla base dei contenitori sono molto diversi da quelli delle macchine virtuali. Dal punto di vista dello sviluppatore, un contenitore deve essere trattato più come un singolo processo. Infatti, un contenitore ha un singolo punto di ingresso per un processo.

I contenitori Docker (per semplicità, contenitori ) possono essere eseguiti in modo nativo in Linux e Windows.Docker containers (for simplicity, *containers)* can run natively on Linux and Windows. Quando si eseguono contenitori normali, i contenitori di Windows possono essere eseguiti solo su host Windows (un server host o una macchina virtuale) e i contenitori Linux possono essere eseguiti solo su host Linux.When running regular containers, Windows containers can run only on Windows hosts (a host server or a VM), and Linux containers can run only on Linux hosts. Tuttavia, nelle versioni recenti di Windows Server e contenitori Hyper-V, un contenitore Linux può anche essere eseguito in modo nativo in Windows Server utilizzando la tecnologia di isolamento Hyper-V che attualmente è disponibile solo nei contenitori di Windows Server.

Nel prossimo futuro, gli ambienti misti che dispongono di contenitori Linux e Windows saranno possibili e persino comuni.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vantaggi dei contenitori di Windows per le applicazioni .NET esistenti

I vantaggi dell'utilizzo dei contenitori di Windows sono fondamentalmente gli stessi vantaggi che si ottengono dai contenitori in generale. L'utilizzo dei contenitori di Windows consente di migliorare notevolmente l'agilità, la portabilità e il controllo.

Le applicazioni .NET esistenti fanno riferimento alle applicazioni create utilizzando .NET Framework. Ad esempio, potrebbero essere applicazioni web ASP.NET tradizionali, ovvero non usano .NET Core, che è più recente ed esegue multipiattaforma su Linux, Windows e MacOS.

La dipendenza principale in .NET Framework è Windows. Ha anche dipendenze secondarie, come IIS, e System.Web nei ASP.NET tradizionali.

Un'applicazione .NET Framework deve essere eseguita in Windows, punto. Se si desidera containerizzare le applicazioni .NET Framework esistenti e non è possibile o non si desidera investire in una migrazione a .NET Core ("Se funziona correttamente, non eseguirne la migrazione"), l'unica scelta disponibile per i contenitori consiste nell'utilizzare i contenitori di Windows.

Pertanto, uno dei principali vantaggi dei contenitori di Windows è che offrono un modo per modernizzare le applicazioni .NET Framework esistenti in esecuzione su contenitori Windows-through. In definitiva, Windows Containers offre i vantaggi che si stanno cercando utilizzando l'agilità dei contenitori, la portabilità e un migliore controllo.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Scegliere un sistema operativo di destinazione con . Contenitori basati su rete

Data la diversità dei sistemi operativi supportati da Docker, nonché le differenze tra .NET Framework e .NET Core, è necessario scegliere come destinazione un sistema operativo specifico e versioni specifiche in base al framework in uso.

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows forniscono caratteristiche diverse (ad esempio IIS rispetto a un server Web self-hosted come Kestrel) che potrebbero essere necessarie per le applicazioni .NET Framework o .NET Core.

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

Figura 4-7 Mostra le versioni del sistema operativo che è possibile destinazione, a seconda della versione dell'applicazione di.NET Framework.

![Diagramma che mostra il sistema operativo di destinazione in base alla versione di .NET Framework.Diagram showing what OS to target based on .NET Framework version.](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**Figura 4-7.** Sistemi operativi di destinazione in base alla versione di .NET Framework

Negli scenari di migrazione per le applicazioni esistenti o legacy basate su applicazioni .NET Framework, le dipendenze principali sono in Windows e IIS. L'unica opzione consiste nell'utilizzare immagini Docker basate su Windows Server Core e .NET Framework.

Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione utilizzando un tag, come negli esempi seguenti per le immagini contenitore Windows basate su .NET Framework:

> | **Tag** | **Sistema e versione** |
> |---|---|
> | **Microsoft/dotnet-framework:4.x-windowsservercore** | .NET Framework 4.x in Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET Framework 4.x con personalizzazione di ASP.NET aggiuntiva in Windows Server Core |

Per .NET Core (multipiattaforma per Linux e Windows), i tag sono simili ai seguenti:

> | **Tag** | **Sistema e versione**
> |---|---|
> | **Microsoft/dotnet:2.0.0-runtime** | Solo runtime di .NET Core 2.0 in Linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET Core 2.0 solo runtime in Windows Nano Server |

### <a name="multi-arch-images"></a>Immagini multi-arco

A partire dalla metà del 2017, è anche possibile utilizzare una nuova funzionalità in Docker denominata immagini [multi-arco.](https://github.com/moby/moby/issues/15866) Le immagini Docker di .NET Core possono usare tag multi-arco. I file Dockerfile non è più necessario definire il sistema operativo di destinazione. La funzione multi-arco consente di utilizzare un singolo tag in più configurazioni della macchina. Ad esempio, con multi-arch, è possibile utilizzare un tag comune: **microsoft/dotnet:2.0.0-runtime**. Se si estrae il tag da un ambiente contenitore Linux, si ottiene l'immagine basata su Debian. Se si estrae il tag da un ambiente contenitore Windows, si ottiene l'immagine basata su Nano Server.If you pull that tag from a Windows container environment, you get the Nano Server-based image.

Per le immagini .NET Framework, poiché la tradizionale .NET Framework supporta solo Windows, non è possibile utilizzare la funzionalità multi-arco.

## <a name="windows-container-types"></a>Tipi di contenitori di Windows

Come i contenitori Linux, i contenitori di Windows Server vengono gestiti tramite Docker Engine.Like Linux containers, Windows Server containers are managed by using Docker Engine. A differenza dei contenitori Linux, i contenitori di Windows includono due tipi di contenitori diversi o i contenitori di Windows Server di esecuzione e l'isolamento Hyper-V.

**Contenitori**di Windows Server: fornisce l'isolamento delle applicazioni tramite la tecnologia di isolamento di processi e spazi dei nomi. Un contenitore di Windows Server condivide un kernel con l'host contenitore e tutti i contenitori in esecuzione nell'host. Questi contenitori non forniscono un limite di sicurezza ostile e non devono essere utilizzati per isolare il codice non attendibile. Poiché lo spazio kernel è condiviso, è necessario che questi contenitori abbiano la stessa versione di kernel e la stessa configurazione.

**Isolamento Hyper-V:** espande l'isolamento fornito dai contenitori di Windows Server eseguendo ogni contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione il kernel dell'host contenitore non è condiviso con gli altri contenitori dello stesso host. Questi contenitori sono progettati per l'hosting multi-tenant ostile, con le stesse garanzie di sicurezza di una macchina virtuale. Poiché questi contenitori non condividono il kernel con l'host o altri contenitori nell'host, possono eseguire kernel con versioni e configurazioni diverse (con versioni supportate). Ad esempio, tutti i contenitori di Windows in Windows 10 utilizzano l'isolamento Hyper-V per utilizzare la versione e la configurazione del kernel di Windows Server.

L'esecuzione di un contenitore in Windows con o senza isolamento Hyper-V è una decisione in fase di esecuzione. È possibile scegliere di creare inizialmente il contenitore con isolamento Hyper-V e, in fase di esecuzione, scegliere di eseguirlo come contenitore di Windows Server.You might choose to create the container with Hyper-V isolation initially, and at run time, choose to run it as a Windows Server container instead.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Documentazione relativa ai contenitori di WindowsWindows Containers**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Nozioni fondamentali sui contenitori di WindowsWindows Containers fundamentals**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografica: Microsoft e contenitori**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>L'ecosistema dei contenitori in AzureThe container ecosystem in Azure

Nelle sezioni precedenti, è stato spiegato quali sono i vantaggi dei contenitori Docker e i dettagli sulle immagini specifiche del contenitore per le applicazioni .NET. Tutte queste informazioni generiche sono fondamentali per sviluppare o containerizzare un'applicazione.
Tuttavia, quando si pensa all'ambiente di distribuzione di produzione o anche agli ambienti di controllo qualità e sviluppo/test, Microsoft Azure offre una gamma aperta e ampia di scelte, un ecosistema di contenitori completo nel cloud (illustrato nel diagramma seguente). A seconda delle esigenze dell'applicazione specifica, è consigliabile scegliere uno o un altro prodotto Azure.Depending on your specific application's needs, you should choose one or another Azure product.

![Diagramma dell'ecosistema del contenitore in Azure.Diagram of the container ecosystem in Azure.](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**Figura 4-7,5.** L'ecosistema dei contenitori in AzureThe container ecosystem in Azure

Dall'ecosistema dei contenitori in Azure, i prodotti seguenti supportano i contenitori considerati infrastruttura:From the container ecosystem in Azure, the following products supporting containers that are considered infrastructure:

- **Istanze di Azure Container**
- **Macchine virtuali di Azure** (con il supporto del contenitore)Azure Virtual Machines (With container's support)
- Set di **scalabilità di macchine virtuali di Azure** (con il supporto del contenitore)Azure Virtual Machine Scale Sets (With container's support)

Da questi tre, ACI fornisce un grande vantaggio, che è il fatto che non è necessario mantenere il sistema operativo sottostante, non c'è bisogno di aggiornare / patch, ecc, ma ACI è ancora posizionato a livello di infrastruttura, come meglio spiegato nelle prossime sezioni di questo libro.

I prodotti in Azure che supportano i contenitori che sono allo stesso tempo posizionati più nel livello PaaS (Piattaforma come servizio) sono:The products in Azure supporting containers that are at the same time positioned more in the PaaS (Platform as a Service) level are:

- **Servizio app di Azure**
- **Servizio Azure Kubernetes (AKS e ACS)**
- **Azure Batch**

Il Registro di sistema contenitore di Azure è quindi un registro contenitore scalabile elevato ospitato in Azure che è possibile usare da tutti i prodotti precedenti durante la registrazione e la distribuzione delle immagini del contenitore personalizzato.

Inoltre, dai contenitori, è possibile usare altri servizi gestiti in Azure come il database SQL di Azure, la cache di Azure Redis, il database Cosmos di Azure e così via. sono disponibili soluzioni/piattaforme di terze parti in Azure Marketplace come Cloud Foundry e OpenShift, dove è anche possibile usare i contenitori all'interno di Azure.

In the next sections, you can explore Microsoft's recommendations on when to use each of those Azure products and solutions specifically when targeting Windows Containers.

>[!div class="step-by-step"]
>[Successivo](what-about-cloud-native-applications.md)
>[precedente](when-not-to-deploy-to-windows-containers.md)
