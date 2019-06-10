---
title: Distribuire app .NET esistenti come contenitori Windows
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Distribuire le app .NET esistenti come contenitori di Windows
ms.date: 04/29/2018
ms.openlocfilehash: ba9af3fc3a5bf285830bb873fa6a5da8390dc6b4
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758840"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Distribuire app .NET esistenti come contenitori Windows

Le distribuzioni basate su contenitori Windows sono applicabili alle applicazioni ottimizzato per il Cloud e applicazioni Native del Cloud.

Tuttavia, in questa Guida e in particolare nelle sezioni seguenti, principalmente è incentrata sull'uso dei contenitori di Windows per *ottimizzato per il Cloud* applicazioni in cui non è necessario riprogettare l'applicazione.

## <a name="what-are-containers-linux-or-windows"></a>Quali sono i contenitori? (Linux o Windows)

I contenitori sono un modo per eseguire il wrapping di un'applicazione in un proprio pacchetto isolato. Nel contenitore, l'applicazione non sia influenzata da applicazioni o processi esistenti all'esterno del contenitore. Tutto ciò che l'applicazione dipende run correttamente come processo è all'interno del contenitore. Ovunque si potrà spostare il contenitore, i requisiti dell'applicazione verranno sempre soddisfatto, in termini di dipendenze dirette, perché si è abbinato a tutto ciò che deve essere eseguito (dipendenze di libreria, Runtime e così via).

Se la caratteristica principale di un contenitore è rendere l'ambiente uguale su distribuzioni diverse in quanto il contenitore stesso è dotato di tutte le dipendenze che necessarie. È possibile eseguire il debug dell'applicazione nel computer e quindi distribuirla in un altro computer, con lo stesso ambiente garantito.

Un contenitore è un'istanza di un'immagine del contenitore. Un'immagine del contenitore è un modo per creare un pacchetto un'app o un servizio (ad esempio, uno snapshot) e quindi distribuirlo in modo affidabile e riproducibile. Si potrebbe dire che Docker non è che solo una tecnologia IT, del anche una filosofia e un processo.

Come i contenitori ogni giorno diventano più comuni, si stanno diventando un settore di "unità di distribuzione".

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vantaggi dei contenitori (motore di Docker in Linux o Windows)

Creazione di applicazioni tramite contenitori, che potrebbe essere anche definiti come blocchi predefiniti-offers leggero un aumento significativo in termini di flessibilità per la creazione, spedizione e l'esecuzione di qualsiasi applicazione, in qualsiasi infrastruttura di.

Con i contenitori, è possibile eseguire qualsiasi app dallo sviluppo alla produzione con minima o senza alcuna modifica del codice, grazie all'integrazione di Docker in strumenti di sviluppo Microsoft, i sistemi operativi e nel cloud.

Quando si distribuisce le macchine virtuali semplice, probabilmente già un metodo sul posto per la distribuzione di App ASP.NET per le macchine virtuali. È probabile che, tuttavia, che il metodo prevede più passaggi manuali o complessi processi automatizzati tramite uno strumento di distribuzione, come Puppet, o uno strumento simile. Potrebbe essere necessario eseguire attività quali la modifica di elementi di configurazione, copia il contenuto dell'applicazione tra server e l'esecuzione di programmi di installazione interattiva basati su installazioni di file con estensione msi, seguite dal test. Tutti i passaggi della distribuzione aggiungere tempi e rischi per le distribuzioni. Vengono generati errori ogni volta che una dipendenza non è presente nell'ambiente di destinazione.

Il processo di creazione delle applicazioni in contenitori Windows, è completamente automatizzato. I contenitori Windows si basa sulla piattaforma Docker, che offre aggiornamenti automatici e i ripristini per le distribuzioni di contenitori. Il principale miglioramento ottenuto tramite il motore Docker è di creare immagini, che sono, ad esempio snapshot dell'applicazione, con tutte le relative dipendenze. Le immagini sono immagini Docker (un Windows immagine del contenitore, in questo caso). Le immagini di eseguire le app ASP.NET nei contenitori, senza tornare al codice sorgente. Lo snapshot del contenitore diventa l'unità di distribuzione.

Molte organizzazioni sono di inserimento nei contenitori di applicazioni monolitiche esistenti per i motivi seguenti:

- **Versione flessibilità nel corso di distribuzione migliorata**. I contenitori offrono un contratto di distribuzione coerente tra sviluppo e operazioni. Quando si usano contenitori, non verrà riprodotto gli sviluppatori ad esempio, "Funziona sul mio computer, perché non nell'ambiente di produzione?" È possibile ad esempio, "Viene eseguito come un contenitore, in modo che possa essere eseguito in ambiente di produzione." L'applicazione in pacchetto, con tutte le relative dipendenze, può essere eseguito in qualsiasi ambiente supportato da basate su contenitori. Verrà eseguito il modo in cui che si intendeva eseguire in tutte le destinazioni di distribuzione (sviluppo, controllo qualità, staging, produzione). I contenitori di eliminano la maggior parte dei conflitti quando si spostano da una fase a quella successiva, che consente di migliorare notevolmente la distribuzione, ed è possibile fornire più rapidamente.

- **Riduzioni dei costi**. I contenitori di causare una riduzione dei costi, tramite il consolidamento e la rimozione di hardware esistente o dall'esecuzione di applicazioni su una densità maggiore per ogni unità dell'hardware.

- **Portabilità**. I contenitori sono modulari e portatile. I contenitori docker sono supportati su qualsiasi sistema operativo server, Linux e Windows, in qualsiasi cloud pubblico principali (Microsoft Azure, Amazon AWS, Google, IBM) e in locale e privato o ambienti cloud ibridi.

- **Controllo**. I contenitori offrono un ambiente flessibile e sicuro che viene controllato a livello di contenitore. Un contenitore può essere protetto, isolated e persino limitato dall'impostazione di esecuzione dei criteri di vincolo per il contenitore. Come descritto in dettaglio nella sezione sui contenitori di Windows, i contenitori di Hyper-V e Windows Server 2016 offrono opzioni di supporto aziendali aggiuntivi.

Miglioramenti significativi nell'agilità, portabilità e il controllo infine comportare la riduzione dei costi significativi quando si usano i contenitori per sviluppare e gestire le applicazioni.

## <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) che consentono di automatizzare la distribuzione di applicazioni come contenitori portabili e autosufficienti eseguibili nel cloud o in locale. Docker è anche un'[azienda](https://www.docker.com/) che promuove questa tecnologia e ne guida l'evoluzione. L'azienda collabora con il cloud, Linux e i fornitori di Windows, inclusa Microsoft.

![](./media/image6.png)

> **Figura 4 a 6.** Docker distribuisce contenitori a tutti i livelli del cloud ibrido

A un utente ha familiarità con le macchine virtuali, contenitori potrebbero sembrare molto simile. Un contenitore esegue un sistema operativo, dispone di un file system e sia accessibile tramite una rete, esattamente come un sistema di computer fisici o virtuali. Tuttavia, la tecnologia e i concetti alla base dei contenitori sono notevolmente diversi dalle macchine virtuali. Dal punto di vista per gli sviluppatori, un contenitore deve essere considerato più come un singolo processo. In effetti, un contenitore dispone di un singolo punto di ingresso per un processo.

I contenitori docker (per semplicità *contenitori*) può eseguire in modo nativo in Linux e Windows. Quando si esegue normali contenitori, i contenitori di Windows possono eseguire solo negli host Windows (un server host o una macchina virtuale) e possono eseguire contenitori Linux solo negli host Linux. Tuttavia, nelle versioni recenti di contenitori Windows Server e Hyper-V, un contenitore Linux anche possibile eseguire in modo nativo in Windows Server usando la tecnologia di isolamento di Hyper-V che è attualmente disponibile solo in contenitori di Windows Server.

Nel prossimo futuro, ambienti misti con contenitori sia Linux che Windows sarà possibile e anche i più comuni.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vantaggi dei contenitori di Windows per le applicazioni .NET esistenti

I vantaggi dell'uso dei contenitori Windows sono fondamentalmente gli stessi vantaggi ottenuti da contenitori in generale. Uso dei contenitori di Windows sta migliora notevolmente la flessibilità, portabilità e il controllo.

Le applicazioni .NET esistenti fanno riferimento a tali applicazioni create utilizzando .NET Framework. Ad esempio, potrebbero essere le applicazioni web ASP.NET tradizionale-non usano .NET Core, che è più recente ed esegue lo sviluppo multipiattaforma in Linux, Windows e MacOS.

La dipendenza principale in .NET Framework è Windows. Include anche le dipendenze secondarie, come IIS e System. Web in ASP.NET tradizionale.

Un'applicazione .NET Framework deve eseguire in Windows, periodo. Se si desidera distribuire in un contenitore di applicazioni .NET Framework esistenti e non è possibile o non si desidera investire in una migrazione a .NET Core ("se funziona correttamente, non eseguirne la migrazione"), l'unica scelta per i contenitori consiste nell'usare i contenitori di Windows.

Pertanto, uno dei principali vantaggi dei contenitori di Windows è che essi offrono un modo per modernizzare le applicazioni .NET Framework esistenti che sono in esecuzione in contenitori Windows-through. In definitiva, i contenitori Windows ti permette di che si siano cercando con i contenitori di agilità, portabilità e controllare meglio i vantaggi.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Scegliere un sistema operativo di destinazione. Contenitori basati su NET

Considerata la diversità dei sistemi operativi supportati da Docker, nonché le differenze tra .NET Framework e .NET Core, si deve essere indirizzata a uno specifico sistema operativo e le versioni specifiche in base al framework in uso.

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows offrono caratteristiche diverse (ad esempio IIS rispetto a un server web self-hosted come Kestrel) che potrebbero essere necessari per le applicazioni .NET Framework o .NET Core.

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

Figura 4-7 mostra le versioni del sistema operativo che è possibile impostare come destinazione, a seconda della versione dell'app di .NET Framework.

![](./media/image7.png)

> **Figura 4-7.** Sistemi operativi di destinazione in base alla versione di .NET Framework

In scenari di migrazione per le applicazioni legacy o esistenti che si basano sulle applicazioni .NET Framework, le dipendenze principale sono in Windows e IIS. L'unica opzione consiste nell'utilizzare le immagini Docker basate su Windows Server Core e .NET Framework.

Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione con un tag, come negli esempi seguenti per le immagini contenitore di Windows basata su .NET Framework:

> | **Tag** | **Sistema e la versione** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x in Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4.x con un'ulteriore personalizzazione ASP.NET, in Windows Server Core |

Per .NET Core (cross-platform per Linux e Windows), i tag sarebbe simile al seguente:

> | **Tag** | **Sistema e la versione**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET core 2.0 runtime solo in Linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET core 2.0 runtime solo in Windows Nano Server |

### <a name="multi-arch-images"></a>Immagini multi-arch

A partire dalla metà del 2017, è inoltre possibile utilizzare una nuova funzionalità in Docker chiamato [multi-arch](https://github.com/moby/moby/issues/15866) immagini. Le immagini Docker per .NET core è possono usare tag per più architetture. Il Dockerfile file non è più necessario definire il sistema operativo di destinazione. La funzionalità multi-arch consente un singolo tag da utilizzare in più configurazioni di computer. Con multi-arch, ad esempio, è possibile usare un tag comune: **microsoft/dotnet:2.0.0-runtime**. Se si visualizzano i tag da un ambiente del contenitore Linux, si ottiene l'immagine basate su Debian. Se si visualizzano i tag da un ambiente di contenitori Windows, si ottiene l'immagine basata su Nano Server.

Per le immagini di .NET Framework, poiché .NET Framework tradizionale supporta solo Windows, è possibile utilizzare la funzionalità multi-arch.

## <a name="windows-container-types"></a>Tipi di contenitori Windows

Come i contenitori Linux, contenitori di Windows Server vengono gestiti tramite il motore Docker. A differenza dei contenitori Linux, contenitori di Windows includono due tipi di contenitore diverso, oppure eseguono contenitori volte-Windows Server e l'isolamento di Hyper-V.

**Contenitori di Windows Server**: Fornisce l'isolamento dell'applicazione tramite la tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore di Windows Server condivide un kernel con l'host contenitore e tutti i contenitori in esecuzione nell'host. Questi contenitori non forniscono un limite di sicurezza potenzialmente ostile e non devono essere utilizzati per isolare il codice non attendibile. A causa di spazio del kernel condiviso, questi contenitori richiedono la stessa versione del kernel e la configurazione.

**Isolamento Hyper-V**: Amplia l'isolamento fornito dai contenitori di Windows Server eseguendo ciascun contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione il kernel dell'host contenitore non viene condivisa con altri contenitori nello stesso host. Questi contenitori sono progettati per multi-tenant ospita ostili, con le stesse garanzie di sicurezza di una macchina virtuale. Poiché questi contenitori non condividono il kernel con l'host o in altri contenitori nell'host, possono essere eseguiti i kernel con diverse versioni e le configurazioni (con le versioni supportate). Ad esempio, tutti i contenitori di Windows in Windows 10 usano isolamento Hyper-V usare la versione del kernel di Windows Server e la configurazione.

Esecuzione di un contenitore in Windows con o senza isolamento Hyper-V è una decisione relativa alla fase di esecuzione. È possibile scegliere per creare inizialmente il contenitore con l'isolamento di Hyper-V e in fase di esecuzione, scegliere di eseguirlo come un contenitore di Windows Server.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Documentazione sui contenitori di Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Nozioni di base sui contenitori di Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografica: Microsoft e i contenitori**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>L'ecosistema di contenitori in Azure

Nelle sezioni precedenti, si è stato illustrato che cosa sono i vantaggi dei contenitori Docker, nonché informazioni dettagliate sulle immagini contenitore specifico per le applicazioni .NET. Informazioni generiche tutto questo sono fondamentale per poter sviluppare o distribuire un'applicazione in un contenitore.
Tuttavia, quando si pensa l'ambiente di distribuzione di produzione o anche negli ambienti di sviluppo/Test e controllo di qualità, Microsoft Azure offre un aperta e una vasta gamma di scelte, un ecosistema completo del contenitore nel cloud (illustrata nel diagramma riportato di seguito). In base alle esigenze specifiche dell'applicazione, è necessario scegliere uno o un altro prodotto di Azure.

![](./media/image7.5.png)

> **Figura 4-7.5.** L'ecosistema di contenitori in Azure

Dall'ecosistema di contenitori in Azure, i prodotti seguenti che supportano i contenitori che vengono considerati infrastruttura:
- **Istanze di contenitore di Azure (ACI)**
- **Macchine virtuali di Azure** (con supporto del contenitore)
- **Set di scalabilità di macchine virtuali Azure** (con supporto del contenitore)

Da queste tre, ACI offre un notevole vantaggio, ovvero il fatto che non è necessario mantenere il sistema operativo sottostante, non è necessario per l'aggiornamento/patch e così via, ma comunque ACI viene posizionato nel livello di infrastruttura, come spiegato meglio nelle sezioni successive di questo libro.

I prodotti in contenitori con supporti di Azure che sono allo stesso tempo posizionato più in PaaS (piattaforma distribuita come servizio) sono:

- **Servizio app di Azure**
- **Azure Kubernetes Service (servizio contenitore di AZURE e servizio contenitore di AZURE)**
- **Azure Batch** 

Quindi, registro contenitori di Azure è un registro contenitori di scalabilità elevata ospitato in Azure che è possibile usare da tutti i prodotti precedenti durante la registrazione e distribuzione di immagini contenitore personalizzate.

Inoltre, dai contenitori, è possibile usare altri servizi gestiti in Azure, ad esempio Azure SQL Database, cache Redis di Azure, Azure Cosmos DB, e così via. Inoltre, sono disponibili soluzioni/piattaforme di terze parti in Azure Marketplace, ad esempio Cloud Foundry e OpenShift in cui è anche possibile usare i contenitori all'interno di Azure. 

Nelle sezioni successive, è possibile esplorare le raccomandazioni di Microsoft su quando usare ognuna di queste soluzioni e i prodotti di Azure in modo specifico quando la destinazione dei contenitori di Windows.

>[!div class="step-by-step"]
>[Precedente](what-about-cloud-native-applications.md)
>[Successivo](when-not-to-deploy-to-windows-containers.md)
