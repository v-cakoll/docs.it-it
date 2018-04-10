---
title: Componenti aggiuntivi ed estensibilità
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: 42
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d288d321063512f91ad94b417bb1a6bf38c9ef9
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="add-ins-and-extensibility"></a>Componenti aggiuntivi ed estensibilità
<a name="top"></a> I componenti aggiuntivi forniscono funzionalità o servizi estesi per un'applicazione host. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] offre un modello di programmazione che gli sviluppatori possono usare per sviluppare componenti aggiuntivi e attivarli nella propria applicazione host. Ciò avviene attraverso la costruzione di una pipeline di comunicazione tra l'host e il componente aggiuntivo. Il modello viene implementato usando i tipi inclusi negli spazi dei nomi <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>e <xref:System.AddIn.Contract> .  
  
 In questa panoramica sono incluse le sezioni seguenti:  
  
-   [Modello dei componenti aggiuntivi](#addin_model)  
  
-   [Distinzione tra componenti aggiuntivi e host](#distinguishing_between_addins_and_hosts)  
  
-   [Argomenti correlati](#related_topics)  
  
-   [Riferimento](#reference)  
  
> [!NOTE]
>  Altro codice di esempio e alcuni strumenti per la compilazione di pipeline dei componenti aggiuntivi in versione Customer Technology Preview sono disponibili nel [sito del framework di estendibilità gestita e dei componenti aggiuntivi su CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a>Modello dei componenti aggiuntivi  
 Il modello dei componenti aggiuntivi consiste in una serie di segmenti che costituiscono la pipeline del componente aggiuntivo, chiamata anche pipeline di comunicazione, responsabile di tutta la comunicazione tra il componente aggiuntivo e l'host. La pipeline è un modello di comunicazione simmetrico di segmenti che scambia dati tra un componente aggiuntivo e il relativo host. Lo sviluppo di questi segmenti tra l'host e il componente aggiuntivo fornisce i livelli di astrazione necessari per il supporto del controllo delle versioni e l'isolamento del componente aggiuntivo.  
  
 L'illustrazione seguente mostra la pipeline.  
  
 ![Aggiungi &#45; nel modello di pipeline. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Pipeline del componente aggiuntivo  
  
 Gli assembly per questi segmenti non devono trovarsi nello stesso dominio applicazione. È possibile caricare un componente aggiuntivo nel suo nuovo dominio applicazione, in uno esistente o persino in quello dell'host. È possibile caricare più componenti aggiuntivi nello stesso dominio applicazione, in modo che condividano le risorse e i contesti di sicurezza.  
  
 Il modello dei componenti aggiuntivi supporta, e consiglia, un limite facoltativo tra l'host e il componente aggiuntivo, chiamato limite di isolamento (o anche limite remoto). Questo limite può essere un dominio applicazione o un limite di processo.  
  
 Il segmento dei contratti al centro della pipeline viene caricato sia nel dominio applicazione dell'host sia in quello del componente aggiuntivo. Il contratto definisce i metodi virtuali usati dall'host e dal componente aggiuntivo per scambiare tipi l'uno con l'altro.  
  
 Per attraversare il limite di isolamento, i tipi devono essere contratti o tipi serializzabili. I tipi che non sono contratti o tipi serializzabili devono essere convertiti in contratti dai segmenti degli adattatori nella pipeline.  
  
 I segmenti delle visualizzazioni della pipeline sono classi di base astratte o interfacce che forniscono all'host e al componente aggiuntivo una visualizzazione dei metodi che condividono, definiti dal contratto.  
  
 Per altre informazioni sullo sviluppo di segmenti della pipeline, vedere [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).  
  
 Le sezioni seguenti descrivono le funzionalità del modello dei componenti aggiuntivi.  
  
### <a name="independent-versioning"></a>Controllo delle versioni indipendente  
 Il modello dei componenti aggiuntivi permette agli host e ai componenti aggiuntivi di eseguire il controllo delle versioni in modo indipendente. Di conseguenza, il modello permette gli scenari seguenti:  
  
-   Creazione di un adattatore che permette a un host di usare un componente aggiuntivo creato per una versione precedente dell'host.  
  
-   Creazione di un adattatore che permette a un host di usare un componente aggiuntivo creato per una versione successiva dell'host.  
  
-   Creazione di un adattatore che permette a un host di usare un componente aggiuntivo creato per un host diverso.  
  
### <a name="discovery-and-activation"></a>Individuazione e attivazione  
 È possibile attivare un componente aggiuntivo usando un token da una raccolta che rappresenta i componenti aggiuntivi trovati in un archivio di informazioni. Per trovare i componenti aggiuntivi, è necessario cercare il tipo che definisce la visualizzazione dell'host del componente aggiuntivo. È possibile trovare un componente aggiuntivo anche in base al tipo che lo definisce. L'archivio di informazioni è costituito da due file di cache: l'archivio della pipeline e l'archivio del componente aggiuntivo.  
  
 Per informazioni sull'aggiornamento e la ricompilazione dell'archivio informazioni, vedere [aggiuntivo individuazione](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421). Per informazioni sull'attivazione di componenti aggiuntivi, vedere [aggiuntivo attivazione](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) e [procedura: attivare componenti aggiuntivi con isolamento diverso e sicurezza](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).  
  
### <a name="isolation-levels-and-external-processes"></a>Livelli di isolamento e processi esterni  
 Il modello dei componenti aggiuntivi supporta diversi livelli di isolamento tra il componente aggiuntivo e il relativo host o tra componenti aggiuntivi diversi. Partendo dal meno isolato, i livelli sono i seguenti:  
  
-   Il componente aggiuntivo viene eseguito nello stesso dominio applicazione dell'host. Questo livello non è consigliato, perché comporta la perdita delle funzionalità di isolamento e scaricamento ottenute usando domini applicazione diversi.  
  
-   Più componenti aggiuntivi vengono caricati nello stesso dominio applicazione, che è diverso da quello usato dall'host.  
  
-   Ogni componente aggiuntivo viene caricato in modo esclusivo nel proprio dominio applicazione. Questo è il livello di isolamento più comune.  
  
-   Più componenti aggiuntivi vengono caricati nello stesso dominio applicazione in un processo esterno.  
  
-   Ogni componente aggiuntivo viene caricato in modo esclusivo nel proprio dominio applicazione in un processo esterno. Questo è lo scenario più isolato.  
  
 Per ulteriori informazioni sull'utilizzo di processi esterni, vedere [procedura: attivare componenti aggiuntivi con isolamento diverso e sicurezza](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).  
  
### <a name="lifetime-management"></a>Gestione della durata  
 Poiché il modello dei componenti aggiuntivi si estende oltre i limiti del dominio applicazione e del processo, Garbage Collection non è in sé sufficiente per rilasciare e recuperare oggetti. Il modello dei componenti aggiuntivi offre un meccanismo di gestione della durata che usa token e conteggio dei riferimenti e che in genere non richiede programmazione aggiuntiva. Per ulteriori informazioni, vedere [la gestione della durata](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
 [Torna all'inizio](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a>Distinzione tra componenti aggiuntivi e host  
 La differenza tra un componente aggiuntivo e un host consiste semplicemente nel fatto che l'host è quello che attiva il componente aggiuntivo. L'host può essere il più grande dei due, ad esempio un'applicazione di elaborazione di testo e i suoi correttori ortografici, oppure può essere anche il più piccolo dei due, ad esempio un client di messaggistica immediata che incorpora un lettore multimediale. Il modello dei componenti aggiuntivi supporta componenti aggiuntivi in scenari client e server. Esempi di componenti aggiuntivi server includono i componenti aggiuntivi che forniscono server di posta elettronica con ricerca di virus, filtri antispam e protezione IP. Esempi di componenti aggiuntivi client includono aggiuntivi di riferimento per elaboratori di testo, funzionalità specializzate per programmi di grafica e giochi e ricerca di virus per client di posta elettronica locale.  
  
 [Torna all'inizio](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)|Descrive la pipeline di comunicazione dei segmenti dall'applicazione host al componente aggiuntivo. Fornisce esempi di codice in argomenti con procedure dettagliate che descrivono come costruire la pipeline e implementare segmenti nella pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].|  
|[Domini applicazione e assembly](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|Descrive la relazione tra domini applicazione, che forniscono un limite di isolamento per sicurezza, affidabilità e controllo delle versioni, e assembly.|  
  
 [Torna all'inizio](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>Riferimenti  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [Torna all'inizio](#top)