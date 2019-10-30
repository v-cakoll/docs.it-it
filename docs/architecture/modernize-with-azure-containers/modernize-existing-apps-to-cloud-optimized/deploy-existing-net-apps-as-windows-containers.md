---
title: Distribuire app .NET esistenti come contenitori Windows
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Distribuire app .NET esistenti come contenitori di Windows
ms.date: 04/29/2018
ms.openlocfilehash: 28568ca363bfc8100f78b100f8a7f0242c4f04c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089552"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Distribuire app .NET esistenti come contenitori Windows

Le distribuzioni basate sui contenitori di Windows sono applicabili alle applicazioni ottimizzate per il cloud e alle applicazioni native del cloud.

Tuttavia, in questa guida e soprattutto nelle sezioni seguenti, si concentra principalmente sull'uso di contenitori di Windows per applicazioni *ottimizzate* per il cloud in cui non è necessario riprogettare l'applicazione.

## <a name="what-are-containers-linux-or-windows"></a>Che cosa sono i contenitori? (Linux o Windows)

I contenitori sono un modo per eseguire il wrapping di un'applicazione nel proprio pacchetto isolato. Nel contenitore, l'applicazione non è interessata dalle applicazioni o dai processi esistenti all'esterno del contenitore. Tutti gli elementi da cui dipende l'applicazione vengono eseguiti correttamente quando un processo si trova all'interno del contenitore. Laddove il contenitore potrebbe essere spostato, i requisiti dell'applicazione verranno sempre soddisfatti, in termini di dipendenze dirette, perché sono aggregati con tutti gli elementi necessari per l'esecuzione (dipendenze della libreria, Runtime e così via).

La caratteristica principale di un contenitore è che rende l'ambiente lo stesso in distribuzioni diverse perché il contenitore stesso è dotato di tutte le dipendenze necessarie. È possibile eseguire il debug dell'applicazione nel computer, quindi distribuirla in un altro computer, con lo stesso ambiente garantito.

Un contenitore è un'istanza di un'immagine del contenitore. Un'immagine del contenitore è un modo per creare un pacchetto di un'app o di un servizio (ad esempio uno snapshot) e quindi distribuirla in modo affidabile e riproducibile. Si potrebbe dire che Docker non è solo una tecnologia, ma anche una filosofia e un processo.

Poiché i contenitori quotidianamente diventano più comuni, stanno diventando un'unità di distribuzione "a livello di settore".

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vantaggi dei contenitori (motore Docker in Linux o Windows)

La creazione di applicazioni tramite contenitori, che possono essere definiti come blocchi predefiniti leggeri, offre un aumento significativo della flessibilità per la creazione, la distribuzione e l'esecuzione di qualsiasi applicazione, in qualsiasi infrastruttura.

Con i contenitori, è possibile usare qualsiasi app dallo sviluppo alla produzione con modifiche minime o senza modifiche al codice, grazie all'integrazione di Docker su strumenti di sviluppo Microsoft, sistemi operativi e cloud.

Quando si esegue la distribuzione in macchine virtuali semplici, probabilmente è già presente un metodo per la distribuzione delle app ASP.NET nelle VM. È probabile, tuttavia, che il metodo includa più passaggi manuali o processi automatici complessi usando uno strumento di distribuzione come Puppet o uno strumento simile. Potrebbe essere necessario eseguire attività quali la modifica di elementi di configurazione, la copia del contenuto dell'applicazione tra server e l'esecuzione di programmi di installazione interattiva basati su configurazioni con estensione msi, seguiti dai test. Tutti i passaggi della distribuzione aggiungono tempo e rischi per le distribuzioni. Si otterranno errori ogni volta che una dipendenza non è presente nell'ambiente di destinazione.

Nei contenitori di Windows, il processo di creazione dei pacchetti di applicazioni è completamente automatizzato. I contenitori di Windows sono basati sulla piattaforma Docker, che offre aggiornamenti automatici e rollback per le distribuzioni di contenitori. Il miglioramento principale ottenuto dall'uso del motore Docker è la creazione di immagini, simili agli snapshot dell'applicazione, con tutte le relative dipendenze. Le immagini sono immagini Docker, in questo caso un'immagine contenitore di Windows. Le immagini eseguono app ASP.NET nei contenitori, senza tornare al codice sorgente. Lo snapshot del contenitore diventa l'unità di distribuzione.

Molte organizzazioni sono inserimento applicazioni monolitiche esistenti per i motivi seguenti:

- **Rilascia agilità grazie a una distribuzione migliorata**. I contenitori offrono un contratto di distribuzione coerente tra lo sviluppo e le operazioni. Quando si usano i contenitori, gli sviluppatori non dicono che "funziona nel computer, perché non sono in produzione?" Si può dire che "viene eseguito come contenitore, in modo che venga eseguito in produzione". L'applicazione in pacchetto, con tutte le relative dipendenze, può essere eseguita in qualsiasi ambiente basato su contenitori supportato. Verrà eseguito il modo in cui è stato progettato per essere eseguito in tutti gli obiettivi di distribuzione (sviluppo, controllo di qualità, gestione temporanea, produzione). I contenitori eliminano la maggior parte degli attriti quando passano da una fase all'altra, migliorando notevolmente la distribuzione, ed è possibile spedire più velocemente.

- **Riduzioni dei costi**. I contenitori portano a costi ridotti, sia per il consolidamento che per la rimozione dell'hardware esistente o per l'esecuzione di applicazioni a una densità più elevata per unità di hardware.

- **Portabilità**. I contenitori sono modulari e portatili. I contenitori Docker sono supportati in qualsiasi sistema operativo server (Linux e Windows), in qualsiasi cloud pubblico principale (Microsoft Azure, Amazon AWS, Google, IBM) e in ambienti cloud in locale e privato o ibrido.

- **Controllo**. I contenitori offrono un ambiente flessibile e sicuro che è controllato a livello di contenitore. Un contenitore può essere protetto, isolato e persino limitato impostando criteri di vincolo di esecuzione nel contenitore. Come descritto in dettaglio nella sezione relativa ai contenitori di Windows, i contenitori di Windows Server 2016 e Hyper-V offrono opzioni di supporto aziendale aggiuntive.

I miglioramenti significativi in termini di agilità, portabilità e controllo, infine, comportano riduzioni dei costi significative quando si usano i contenitori per sviluppare e gestire le applicazioni.

## <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) che automatizza la distribuzione di applicazioni come contenitori portabili e autosufficienti che possono essere eseguiti nel cloud o in locale. Docker è anche un'[azienda](https://www.docker.com/) che promuove questa tecnologia e ne guida l'evoluzione. La società collabora con i fornitori di cloud, Linux e Windows, tra cui Microsoft.

![Diagramma che illustra in che modo Docker distribuisce i contenitori nel cloud ibrido.](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**Figura 4-6.** Docker distribuisce contenitori a tutti i livelli del cloud ibrido

Per chi ha familiarità con le macchine virtuali, i contenitori potrebbero sembrare molto simili. Un contenitore esegue un sistema operativo, dispone di un file system ed è possibile accedervi tramite una rete, proprio come un computer fisico o virtuale. Tuttavia, la tecnologia e i concetti alla base dei contenitori sono molto diversi dalle macchine virtuali. Dal punto di vista dello sviluppatore, un contenitore deve essere trattato in modo più simile a un singolo processo. Un contenitore dispone infatti di un singolo punto di ingresso per un processo.

I contenitori Docker (per semplicità, *contenitori*) possono essere eseguiti in modo nativo in Linux e Windows. Quando si eseguono contenitori normali, i contenitori di Windows possono essere eseguiti solo in host Windows (un server host o una macchina virtuale) e i contenitori Linux possono essere eseguiti solo su host Linux. Nelle versioni recenti di contenitori di Windows Server e Hyper-V, tuttavia, un contenitore Linux può essere eseguito in modo nativo in Windows Server usando la tecnologia di isolamento Hyper-V attualmente disponibile solo nei contenitori di Windows Server.

Nel prossimo futuro, saranno possibili e persino comuni gli ambienti misti con contenitori sia Linux che Windows.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vantaggi dei contenitori Windows per le applicazioni .NET esistenti

I vantaggi derivanti dall'uso dei contenitori di Windows sono fondamentalmente gli stessi vantaggi che si ottengono dai contenitori in generale. L'uso dei contenitori di Windows consiste nel migliorare significativamente l'agilità, la portabilità e il controllo.

Le applicazioni .NET esistenti fanno riferimento a tali applicazioni create usando il .NET Framework. Ad esempio, possono essere applicazioni Web ASP.NET tradizionali. non usano .NET Core, che è più recente ed esegue multipiattaforma in Linux, Windows e MacOS.

La dipendenza principale nella .NET Framework è Windows. Ha anche dipendenze secondarie, ad esempio IIS e System. Web in ASP.NET tradizionali.

Un'applicazione .NET Framework deve essere eseguita in Windows, punto. Se si vuole distribuire le applicazioni .NET Framework esistenti e non si può o non si vuole investire in una migrazione a .NET Core ("se funziona correttamente, non eseguire la migrazione"), l'unica scelta per i contenitori consiste nell'usare i contenitori di Windows.

Uno dei principali vantaggi derivanti dai contenitori di Windows è quello di offrire una soluzione per modernizzare le applicazioni .NET Framework esistenti in esecuzione in contenitori di Windows. In definitiva, i contenitori di Windows ottengono i vantaggi che si stanno cercando usando i contenitori: agilità, portabilità e controllo migliore.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Scegliere un sistema operativo con cui eseguire la destinazione. Contenitori basati su rete

Considerata la diversità dei sistemi operativi supportati da Docker, nonché le differenze tra .NET Framework e .NET Core, è consigliabile usare come destinazione un sistema operativo specifico e versioni specifiche in base al Framework in uso.

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows forniscono caratteristiche diverse, ad esempio IIS rispetto a un server Web self-hosted come gheppio, che potrebbero essere necessarie per applicazioni .NET Framework o .NET Core.

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

La figura 4-7 illustra le versioni del sistema operativo a cui è possibile fare riferimento, a seconda della versione dell'app del .NET Framework.

![Diagramma che mostra il sistema operativo di destinazione in base alla versione .NET Framework.](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**Figura 4-7.** Sistemi operativi di destinazione in base alla versione .NET Framework

Negli scenari di migrazione di applicazioni esistenti o legacy basate su .NET Framework applicazioni, le dipendenze principali si trovano in Windows e IIS. L'unica opzione consiste nell'usare le immagini Docker basate su Windows Server Core e la .NET Framework.

Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione usando un tag, come negli esempi seguenti per le immagini del contenitore di Windows basate su .NET Framework:

> | **Tag** | **Sistema e versione** |
> |---|---|
> | **Microsoft/DotNet-Framework: 4. x-windowsservercore** | .NET Framework 4. x in Windows Server Core |
> | **Microsoft/ASPNET: 4. x-windowsservercore** | .NET Framework 4. x con personalizzazione ASP.NET aggiuntiva, in Windows Server Core |

Per .NET Core (multipiattaforma per Linux e Windows), i tag avranno un aspetto simile al seguente:

> | **Tag** | **Sistema e versione**
> |---|---|
> | **Microsoft/DotNet: 2.0.0-Runtime** | Runtime di .NET Core 2,0-solo in Linux |
> | **Microsoft/DotNet: 2.0.0-Runtime-nanoserver** | Runtime di .NET Core 2,0-solo in Windows nano server |

### <a name="multi-arch-images"></a>Immagini a più Arch

A partire da metà 2017, è anche possibile usare una nuova funzionalità di Docker denominata immagini [multiarch](https://github.com/moby/moby/issues/15866) . Le immagini Docker per .NET Core possono usare tag a più Arch. I file Dockerfile non devono più definire il sistema operativo di destinazione. La funzionalità multi-arch consente l'uso di un singolo tag in più configurazioni di computer. Ad esempio, con più Arch è possibile usare un tag comune: **Microsoft/DotNet: 2.0.0-Runtime**. Se si esegue il pull di tale tag da un ambiente contenitore Linux, si ottiene l'immagine basata su Debian. Se si estrae il tag da un ambiente contenitore Windows, si ottiene l'immagine basata su nano server.

Per .NET Framework immagini, perché il .NET Framework tradizionale supporta solo le finestre, non è possibile usare la funzionalità multiarch.

## <a name="windows-container-types"></a>Tipi di contenitore di Windows

Come i contenitori Linux, i contenitori di Windows Server vengono gestiti tramite il motore docker. A differenza dei contenitori Linux, i contenitori di Windows includono due tipi di contenitori diversi, o esecuzioni, i contenitori di Windows Server e l'isolamento di Hyper-V.

**Contenitori di Windows Server**: fornisce l'isolamento delle applicazioni tramite la tecnologia di isolamento processo e spazio dei nomi. Un contenitore di Windows Server condivide un kernel con l'host contenitore e tutti i contenitori in esecuzione nell'host. Questi contenitori non forniscono un limite di sicurezza ostile e non devono essere usati per isolare il codice non attendibile. A causa dello spazio del kernel condiviso, questi contenitori richiedono la stessa versione e la stessa configurazione del kernel.

**Isolamento di Hyper-V**: espande l'isolamento fornito dai contenitori di Windows Server eseguendo ogni contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione il kernel dell'host contenitore non viene condiviso con altri contenitori nello stesso host. Questi contenitori sono progettati per l'hosting multi-tenant ostile con le stesse garanzie di sicurezza di una macchina virtuale. Poiché questi contenitori non condividono il kernel con l'host o altri contenitori nell'host, possono eseguire kernel con versioni e configurazioni diverse (con versioni supportate). Ad esempio, tutti i contenitori di Windows in Windows 10 usano l'isolamento Hyper-V per usare la versione e la configurazione del kernel di Windows Server.

L'esecuzione di un contenitore in Windows con o senza isolamento Hyper-V è una decisione in fase di esecuzione. È possibile scegliere di creare inizialmente il contenitore con isolamento Hyper-V e in fase di esecuzione scegliere di eseguirlo come contenitore di Windows Server.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Documentazione dei contenitori di Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Nozioni fondamentali sui contenitori di Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografica: Microsoft e contenitori**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>Ecosistema di contenitori in Azure

Nelle sezioni precedenti sono stati illustrati i vantaggi dei contenitori Docker e i dettagli sulle immagini del contenitore specifiche per le applicazioni .NET. Tutte le informazioni generiche sono fondamentali per lo sviluppo o la distribuire di un'applicazione.
Tuttavia, quando si pensa all'ambiente di distribuzione di produzione o anche agli ambienti di test e sviluppo/test, Microsoft Azure offre un'ampia gamma di opzioni, un ecosistema di contenitori completo nel cloud (illustrato nel diagramma seguente). A seconda delle esigenze specifiche dell'applicazione, è necessario scegliere uno o un altro prodotto Azure.

![Diagramma dell'ecosistema di contenitori in Azure.](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**Figura 4-7.5.** Ecosistema di contenitori in Azure

Dall'ecosistema di contenitori di Azure, i prodotti seguenti supportano i contenitori considerati infrastruttura:

- **Istanze di contenitore di Azure (ACI)**
- **Macchine virtuali di Azure** (con supporto del contenitore)
- **Set di scalabilità di macchine virtuali di Azure** (con supporto del contenitore)

Da queste tre, ACI offre un notevole vantaggio, ovvero il fatto che non è necessario gestire il sistema operativo sottostante, non è necessario eseguire l'aggiornamento/patch e così via, ma ACI è ancora posizionato a livello di infrastruttura, come illustrato in modo più appropriato nelle prossime sezioni di questo libro.

I prodotti in Azure che supportano i contenitori che si trovano allo stesso tempo posizionati più nel livello PaaS (piattaforma distribuita come servizio) sono:

- **Servizio app di Azure**
- **Servizio Azure Kubernetes (AKS e ACS)**
- **Azure Batch**

Azure Container Registry, quindi, è un registro contenitori altamente scalabile ospitato in Azure che può essere usato da tutti i prodotti precedenti per la registrazione e la distribuzione delle immagini del contenitore personalizzato.

Dai contenitori è inoltre possibile utilizzare altri servizi gestiti in Azure, ad esempio il database SQL di Azure, cache Redis di Azure, Azure Cosmos DB e così via. in Azure Marketplace sono inoltre disponibili soluzioni/piattaforme di terze parti, ad esempio Cloud Foundry e OpenShift, in cui è possibile usare i contenitori anche in Azure.

Nelle sezioni successive è possibile esaminare le raccomandazioni di Microsoft su quando usare i prodotti e le soluzioni di Azure in modo specifico per i contenitori di Windows.

>[!div class="step-by-step"]
>[Precedente](what-about-cloud-native-applications.md)
>[Successivo](when-not-to-deploy-to-windows-containers.md)
