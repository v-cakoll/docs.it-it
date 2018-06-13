---
title: Distribuire app .NET esistenti come contenitori di Windows
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Distribuire le app .NET esistenti dei contenitori di Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 829f33aba14d79d7d9003d1ac7472a19060d401a
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958001"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Distribuire app .NET esistenti come contenitori di Windows

Le distribuzioni che si basano sui contenitori di Windows sono applicabili alle applicazioni ottimizzato su Cloud e le applicazioni Cloud nativo.

Tuttavia, in questa Guida e in particolare nelle sezioni seguenti principalmente si concentra sull'uso dei contenitori di Windows per *ottimizzato su Cloud* applicazioni in cui non è necessario ridefinizione dell'architettura dell'applicazione.

## <a name="what-are-containers-linux-or-windows"></a>Che cosa sono contenitori? (Linux o Windows)

I contenitori sono un modo per eseguire il wrapping di un'applicazione in un proprio pacchetto isolato. Il relativo contenitore, l'applicazione non sia influenzata da applicazioni o i processi che esistono di fuori del contenitore. Tutto ciò che l'applicazione dipende dal accesso per effettuare correttamente come un processo è all'interno del contenitore. Ovunque potrebbe spostare il contenitore, i requisiti dell'applicazione verranno sempre essere soddisfatti, in termini di dipendenze dirette, perché in dotazione tutto ciò che deve essere eseguito (dipendenze di libreria, Runtime e così via).

Le caratteristiche principali di un contenitore sono che rende l'ambiente uguali tra le diverse distribuzioni poiché il contenitore include tutte le dipendenze che necessarie. Il debug dell'applicazione nel computer e quindi distribuirla in un altro computer, con lo stesso ambiente garantito.

Un contenitore è un'istanza di un'immagine contenitore. Un'immagine contenitore è un modo per un'app o un servizio (ad esempio, uno snapshot) del pacchetto e distribuirlo in modo affidabile e riproducibile. È possibile specificare che Docker non è che solo un oggetto la tecnologia del anche degli scopi e un processo.

Come contenitori quotidianamente diventano più comuni, essi sono sempre un settore "unità di distribuzione".

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Vantaggi dei contenitori (motore di Docker in Linux o Windows)

Anche la creazione di applicazioni utilizzando contenitori, che potrebbe essere definito come offerte di blocchi predefiniti di leggere un aumento significativo in termini di flessibilità per la compilazione, spedizione e l'esecuzione di qualsiasi altra applicazione, in qualsiasi infrastruttura.

Con i contenitori, è possibile eseguire qualsiasi app dallo sviluppo alla produzione con senza alcuna modifica del codice, grazie all'integrazione di Docker, gli strumenti di sviluppo Microsoft, i sistemi operativi e nel cloud.

Quando si distribuiscono macchine virtuali normale, probabilmente si ha un metodo sul posto per la distribuzione di applicazioni ASP.NET per le macchine virtuali. È probabile che, tuttavia, che il metodo prevede più passaggi manuali o complessi processi automatizzati tramite uno strumento di distribuzione come Puppet o uno strumento simile. Potrebbe essere necessario eseguire attività quali la modifica degli elementi di configurazione, la copia il contenuto dell'applicazione tra server e in esecuzione programmi di installazione interattiva, in base alle impostazioni di file con estensione msi, seguite dal test. Tutte le fasi di distribuzione aggiungere tempo e al rischio per le distribuzioni. Vengono generati errori ogni volta che una dipendenza non è presente nell'ambiente di destinazione.

Nei contenitori di Windows, il processo di package delle applicazioni è completamente automatizzato. Contenitori di Windows si basa sulla piattaforma Docker, che offre aggiornamenti automatici e i ripristini per le distribuzioni di contenitori. I miglioramenti principali ottenute tramite il motore Docker sono creare immagini, sono ad esempio snapshot dell'applicazione, con tutte le relative dipendenze. Le immagini sono immagini Docker (una contenitore immagine Windows, in questo caso). Le immagini di eseguire le applicazioni ASP.NET in contenitori, senza tornare al codice sorgente. Lo snapshot contenitore diventa l'unità di distribuzione.

Molte organizzazioni sono containerizing applicazioni monolitiche esistenti per i motivi seguenti:

-   **Versione flessibilità durante la distribuzione migliorata**. I contenitori offrono un contratto di distribuzione coerente tra lo sviluppo e operazioni. Quando si utilizzano contenitori, non verrà riprodotto gli sviluppatori ad esempio, "Funziona nel computer, non vengono visualizzati nell'ambiente di produzione?" È possibile ad esempio, "Viene eseguito come un contenitore, in modo che verrà eseguito nell'ambiente di produzione." In qualsiasi ambiente supportato da basate sul contenitore, è possibile eseguire l'applicazione del pacchetto, con tutte le relative dipendenze. Verrà eseguito il modo in cui che è stato progettato per l'esecuzione in tutte le destinazioni di distribuzione (sviluppo, QA, gestione temporanea, produzione). Contenitori di eliminano la maggior parte delle frictions quando si spostano da una fase a quella successiva, consente di migliorare notevolmente la distribuzione, ed è possibile distribuire più velocemente.

-   **Riduzioni dei costi**. Contenitori di portare a ridurre i costi, tramite il consolidamento e la rimozione dell'hardware esistente, o da applicazioni in esecuzione in una densità più elevata per unità di hardware.

-   **Portabilità**. I contenitori sono modularità e portabili. Contenitori di docker sono supportati in qualsiasi sistema operativo server Linux e Windows, in qualsiasi cloud pubblico principali (Microsoft Azure, AWS Amazon, Google, IBM) e in locale e private o ambienti cloud ibridi.

-   **Controllo**. I contenitori offrono un ambiente flessibile e sicuro che è controllato a livello di contenitore. Un contenitore può essere protetto, isolato e anche limitato impostando esecuzione criteri di vincolo per il contenitore. Come descritto in dettaglio nella sezione sui contenitori di Windows, i contenitori di Windows Server 2016 e Hyper-V offrono opzioni di supporto aggiuntivi dell'organizzazione.

La riduzione dei costi significativi miglioramenti significativi in agilità, la portabilità e il controllo alla fine causare quando si utilizzano contenitori per sviluppare e gestire le applicazioni.

## <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) che consente di automatizzare la distribuzione di applicazioni come portabile, autosufficiente contenitori che è possibile eseguire nel cloud o locale. Docker è anche un'[azienda](https://www.docker.com/) che promuove questa tecnologia e ne guida l'evoluzione. La società funziona in collaborazione con fornitori di Windows, inclusi Microsoft di cloud, Linux e.

![](./media/image6.png)

> **Figura 4-6.** Docker distribuisce contenitori a tutti i livelli del cloud ibrido

A un utente ha familiarità con le macchine virtuali, i contenitori potrebbero risultare molto simile. Un contenitore esegue un sistema operativo, dispone di un file system e sia accessibile tramite una rete, esattamente come un sistema di computer fisici o virtuali. Tuttavia, la tecnologia e i concetti di base dei contenitori sono molto diversi dalle macchine virtuali. Da un punto di vista di sviluppatore, un contenitore deve essere considerato più come un singolo processo. In effetti, un contenitore ha un singolo punto di ingresso per un processo.

Contenitori di docker (per motivi di semplicità, *contenitori*) può eseguire in modo nativo in Linux e Windows. Quando si esegue contenitori normali, i contenitori di Windows è possono eseguire solo negli host Windows (un server host o una macchina virtuale) e i contenitori di Linux può essere eseguito solo gli host Linux. Tuttavia, nelle versioni recenti di contenitori di Windows Server e Hyper-V, un contenitore di Linux anche possibile eseguire in modo nativo in Windows Server utilizzando la tecnologia di isolamento di Hyper-V che è attualmente disponibile solo in contenitori di Windows Server.

Nel prossimo futuro, ambienti misti che sono contenitori di Linux e Windows sarà possibile e anche comuni.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Vantaggi di contenitori di Windows per le applicazioni .NET esistenti

Vantaggi dell'utilizzo di contenitori di Windows sono fondamentalmente gli stessi vantaggi che si ottiene in genere dai contenitori. Utilizzo di contenitori di Windows sta migliorando agilità, la portabilità e il controllo.

Le applicazioni .NET esistenti fanno riferimento a queste applicazioni create utilizzando .NET Framework. Ad esempio, potrebbero essere le applicazioni web ASP.NET tradizionale-non usano .NET Core, che è più recente ed esegue multipiattaforma in Linux, Windows e MacOS.

La dipendenza principale in .NET Framework è Windows. Include inoltre le dipendenze secondarie, come IIS e System. Web in ASP.NET tradizionale.

Un'applicazione .NET Framework deve eseguire in Windows, periodo. Se si desidera inserita in un contenitore esistente nelle applicazioni .NET Framework e non è possibile o non si desidera investire in una migrazione a .NET Core ("se il corretto funzionamento, non la migrazione"), l'unica scelta è per i contenitori consiste nell'usare i contenitori di Windows.

Pertanto, uno dei principali vantaggi di contenitori di Windows è che essi offrono un modo per modernizzare le applicazioni .NET Framework esistenti che eseguono Windows-through containerizzazione. Infine, i contenitori di Windows consente i vantaggi che si siano cercando tramite un migliore controllo contenitori flessibilità e portabilità.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Scegliere un sistema operativo di destinazione. Contenitori basati su NET

Considerata la diversità dei sistemi operativi supportati da Docker, nonché le differenze tra .NET Framework e .NET Core, si deve essere indirizzata a uno specifico sistema operativo e le versioni specifiche in base al framework in uso.

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows forniscono caratteristiche diverse (ad esempio, IIS e un server web self-hosted come Kestrel) che potrebbero essere necessari per le applicazioni .NET Framework o .NET Core.

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

Figura 4-7 mostra versioni del sistema operativo che è possibile impostare come destinazione, a seconda della versione dell'app di .NET Framework.

![](./media/image7.png)

> **Figura 4-7.** Sistemi operativi di destinazione in base a una versione di .NET Framework

In scenari di migrazione per le applicazioni legacy o esistenti che si basano sulle applicazioni .NET Framework, le dipendenze principale sono in Windows e IIS. L'unica possibilità consiste nell'utilizzare le immagini Docker basate su Windows Server Core e .NET Framework.

Quando si aggiunge il nome dell'immagine nel file Dockerfile, è possibile selezionare il sistema operativo e la versione con un tag, come negli esempi seguenti per le immagini contenitore di Windows basate su .NET Framework:

> | **tag** | **Sistema e versione** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4. x in Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4. x con un'ulteriore personalizzazione di ASP.NET, in Windows Server Core |

.NET Core (multipiattaforma per Linux e Windows), i tag sarebbero simile al seguente:

> | **tag** | **Sistema e versione**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET core 2.0 runtime solo in Linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET core 2.0 runtime solo in Windows Nano Server |

### <a name="multi-arch-images"></a>Multi-architettura immagini

A partire da mid 2017, è inoltre possibile utilizzare una nuova funzionalità in Docker chiamato [multi-arch](https://github.com/moby/moby/issues/15866) immagini. Immagini Docker di .NET core è possono utilizzare più arch tag. Il Dockerfile i file non è più necessario definire il sistema operativo di destinazione. La funzionalità multi-architettura consente un singolo tag da utilizzare in più configurazioni della macchina. Con multi-arch, ad esempio, è possibile utilizzare un tag comune: **microsoft/dotnet:2.0.0-runtime**. Se si trascina il tag da un ambiente di contenitori di Linux, si recupererà l'immagine di base Debian. Se si trascina il tag da un ambiente di contenitore di Windows, si recupererà l'immagine base di Nano Server.

Per le immagini di .NET Framework, poiché le tradizionali di .NET Framework supporta solo Windows, è possibile utilizzare la funzionalità multi-arch.

## <a name="windows-container-types"></a>Tipi di contenitori di Windows

Contenitori di Linux, contenitori di Windows Server vengono gestiti tramite il motore Docker. A differenza dei contenitori di Linux, i contenitori di Windows includono due tipi di contenitore diverso oppure eseguono i contenitori di volte in cui Windows Server e l'isolamento di Hyper-V.

**Contenitori di Windows Server**: fornisce l'isolamento dell'applicazione attraverso una tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore di Windows Server condivide un kernel con l'host contenitore e tutti i contenitori in esecuzione nell'host. Questi contenitori non forniscono un limite di sicurezza ostile e non devono essere utilizzati per isolare il codice non attendibile. A causa dello spazio di kernel condiviso, questi contenitori di richiedono la stessa versione del kernel e la configurazione.

**Isolamento di Hyper-V**: amplia l'isolamento fornito dai contenitori di Windows Server eseguendo ciascun contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione il kernel dell'host contenitore non viene condiviso con gli altri contenitori nello stesso host. Questi contenitori sono progettati per multi-tenant hosting ostile, con le stesse garanzie di sicurezza di una macchina virtuale. Poiché questi contenitori non condividono il kernel con l'host o in altri contenitori nell'host, possono essere eseguite kernel con diverse versioni e le configurazioni (con le versioni supportate). Ad esempio, tutti i contenitori di Windows in Windows 10 uso dell'isolamento di Hyper-V per usare la versione del kernel di Windows Server e la configurazione.

L'esecuzione di un contenitore in Windows con o senza isolamento Hyper-V è una decisione in fase di esecuzione. Si potrebbe scegliere di creare il contenitore di isolamento di Hyper-V inizialmente e in fase di esecuzione, scegliere di eseguirlo come un contenitore di Windows Server.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Documentazione sui contenitori di Windows**

    [https://docs.microsoft.com/virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Nozioni di base sui contenitori di Windows**

    [https://docs.microsoft.com/virtualization/windowscontainers/about/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **Infografica: Microsoft e i contenitori**

    [https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)


## <a name="the-container-ecosystem-in-azure"></a>L'ecosistema di contenitori in Azure

Nelle sezioni precedenti, si è stato illustrato che cosa sono i vantaggi di contenitori di Docker, nonché informazioni dettagliate sulle immagini contenitore specifico per le applicazioni .NET. Tutto il generiche informazioni sono fondamentali per lo sviluppo o containerize un'applicazione.
Tuttavia, quando si pensa l'ambiente di distribuzione di produzione o anche negli ambienti di sviluppo/Test e QA, Microsoft Azure offre un ampio e aprire ampia gamma di opzioni, un ecosistema di contenitori completa nel cloud (illustrato nel diagramma seguente). In base alle esigenze dell'applicazione specifico, è necessario scegliere uno o un altro prodotto Azure.

![](./media/image7.5.png)

> **Figura 4-7.5.** L'ecosistema di contenitori in Azure

Dall'ecosistema di contenitori in Azure, i prodotti seguenti contenitori che vengono considerati come infrastruttura di supporto:
-   **Istanze di contenitore di Azure (ACI)**
-   **Macchine virtuali di Azure** (con il supporto del contenitore)
-   **Set di scalabilità di macchine virtuali Azure** (con il supporto del contenitore)

Da queste tre ACI fornisce comporta notevoli vantaggi, che è il fatto che non è necessario gestire il sistema operativo sottostante, non è necessario per l'aggiornamento/patch e così via, ma ancora ACI viene posizionato nel livello di infrastruttura, come una migliore illustrato nelle sezioni successive di questo manuale.

I prodotti nei contenitori supporto Azure appartenenti allo stesso tempo posizionato più in PaaS (piattaforma distribuita come servizio) a livello sono:

-   **Servizio app di Azure**
-   **Servizio Azure Kubernetes (AKS e ACS)**
-   **Azure Service Fabric** 
-   **Azure Batch** 

Quindi, Registro di sistema contenitore di Azure è un registro di sistema elevata contenitore scalabile ospitato in Azure che è possibile utilizzare da tutti i prodotti precedenti durante la registrazione e la distribuzione delle immagini contenitore personalizzato.

Inoltre, ai contenitori, è possibile utilizzare altri servizi gestiti in Azure come Database SQL di Azure cache Redis di Azure, Azure Cosmos DB, e così via. Inoltre, sono disponibili piattaforme/soluzioni di terze parti in Azure Marketplace, ad esempio Cloud Foundry e OpenShift in cui è inoltre possibile utilizzare i contenitori all'interno di Azure. 

Nelle sezioni successive, è possibile esplorare le indicazioni di Microsoft su quando usare ognuna di tali prodotti Azure e soluzioni in particolare quando la destinazione dei contenitori di Windows.


>[!div class="step-by-step"]
[Precedente](what-about-cloud-native-applications.md)
[Successivo](when-not-to-deploy-to-windows-containers.md)
