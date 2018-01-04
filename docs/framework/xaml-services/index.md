---
title: Servizi XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 458b4c94d26b7bc083c5d31fcbccf05b42bba52e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-services"></a>Servizi XAML
In questo argomento vengono descritte le funzionalità di un set di tecnologie noto come XAML di .NET Framework di servizi. La maggior parte dei servizi e le API descritte si trovano nell'assembly System. XAML, che è un assembly è stato introdotto con la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] set di assembly di .NET core. I servizi includono lettori e writer, le classi dello schema e supporto dello schema, le factory, assegnazione di attributi di classi, supporto intrinseco del linguaggio XAML e altre funzionalità del linguaggio XAML.  
  
## <a name="about-this-documentation"></a>Informazioni sulla documentazione  
 Documentazione concettuale per i servizi XAML di .NET Framework si presuppone che si ha esperienza con il linguaggio XAML e come può applicare a un framework specifico, ad esempio [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] o [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)], o una tecnologia specifica area di funzionalità di esempio di personalizzazione compilazioni di funzionalità in <xref:Microsoft.Build.Framework.XamlTypes>. Questa documentazione non tenta di spiegare i concetti di base di XAML come linguaggio di markup, terminologia della sintassi XAML o altro materiale introduttivo. Al contrario, questa documentazione è incentrata sull'utilizzo specifico di servizi XAML di .NET Framework abilitati nella libreria dell'assembly System. Xaml. La maggior parte di queste API sono valide per scenari di integrazione di linguaggio XAML e l'estensibilità. Ciò potrebbe includere le seguenti:  
  
-   Estensione delle funzionalità della base reader XAML o i writer XAML (elaborazione direttamente il flusso del nodo XAML, derivare la propria reader XAML o writer XAML).  
  
-   Definizione di tipi personalizzati utilizzabili con XAML che non hanno dipendenze framework specifici e assegnando i tipi per comunicare loro XAML digitare le caratteristiche del sistema di servizi XAML di .NET Framework.  
  
-   Hosting di reader XAML o writer XAML come un componente di un'applicazione, ad esempio una finestra di progettazione visiva o editor interattivo per le origini di markup XAML.  
  
-   Scrittura di convertitori di valori XAML (estensioni di markup, i convertitori di tipi per i tipi personalizzati).  
  
-   Definizione di un contesto dello schema XAML personalizzato (tramite tecniche alternative di caricamento di assembly per le origini di tipo sottostante; utilizzando tecniche di ricerca di tipi noti anziché sempre reflection di assembly; utilizzando i concetti di assembly caricati che non utilizzano CLR `AppDomain` e il modello di sicurezza associato).  
  
-   Estendere il sistema di tipi XAML base.  
  
-   Utilizzo di `Lookup` o `Invoker` tecniche per influenzare il codice XAML digitare system e modalità di valutazione dei tipi di supporto.  
  
 Se sta cercando materiale introduttivo su XAML come linguaggio, è possibile provare a [Panoramica di XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Tale argomento sono illustrate XAML per un gruppo di destinatari che è una novità per [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] e anche all'utilizzo di markup XAML e funzionalità del linguaggio XAML. Un altro documento utile è il materiale introduttivo nel [specifiche del linguaggio XAML](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>Servizi XAML di .NET framework e System. XAML nell'architettura di .NET  
 Nelle versioni precedenti di [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)], il supporto per funzionalità del linguaggio XAML è stata implementata da Framework basati su [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] e [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]) e pertanto variare il relativo comportamento e l'API usata a seconda di quale si utilizza un framework specifico. Questo incluso il codice XAML parser e il relativo oggetto grafico meccanismo di creazione, intrinseci del linguaggio XAML, supporto della serializzazione e così via.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], servizi XAML di .NET Framework e l'assembly System. Xaml definiscono la maggior parte degli elementi necessari per il supporto delle funzionalità del linguaggio XAML. Questo include classi di base per i reader XAML e writer XAML. La funzionalità più importante aggiunta ai servizi XAML .NET Framework che non era presente in una qualsiasi delle implementazioni specifiche del framework XAML è una rappresentazione del sistema di tipo per il codice XAML. La rappresentazione del sistema di tipo XAML è presentato in orientata agli oggetti in modo che si concentra sulle funzionalità di XAML senza le dipendenze sulle funzionalità specifiche del Framework.  
  
 Sistema di tipi XAML non è limitato dal modulo di markup o in fase di esecuzione specifiche dell'origine XAML; né è limitata da qualsiasi sistema di tipi di supporto specifici. Sistema di tipi XAML include rappresentazioni di oggetti per i tipi, membri, contesti dello schema XAML, i concetti di livello di XML e altri concetti del linguaggio XAML o intrinseci XAML. Utilizzo o l'estensione di sistema di tipi XAML rende possibile il derivino da classi quali reader XAML e writer XAML ed estendere le funzionalità delle rappresentazioni XAML in specifiche funzionalità abilitate da una struttura, una tecnologia o un'applicazione che utilizza o genera XAML. Il concetto di un contesto dello schema XAML consente operazioni di scrittura pratiche oggetto grafico in base alla combinazione di un'implementazione del writer di oggetti XAML, sistema di tipi di supporto di una tecnologia, comunicato tramite le informazioni sull'assembly nel contesto e il nodo XAML origine. Per ulteriori informazioni sul concetto dello schema XAML. vedere [predefinito contesto dello Schema XAML e il contesto dello Schema XAML WPF](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Flussi di nodi XAML reader XAML e writer XAML  
 Per comprendere il ruolo svolto nella relazione tra il linguaggio XAML e le tecnologie specifiche che usano XAML come linguaggio di servizi XAML di .NET Framework, è utile comprendere il concetto di flusso di nodi XAML e come tale concetto forme dell'API e terminologia. Flusso di nodi XAML è un concettuale intermedio tra una rappresentazione del linguaggio XAML e l'oggetto grafico che rappresenta il codice XAML o che definisce.  
  
-   Un reader XAML è un'entità che l'elaborazione di XAML in diversi formati e produce un flusso di nodi XAML. Nell'API di reader XAML è rappresentato dalla classe di base <xref:System.Xaml.XamlReader>.  
  
-   Un writer XAML è un'entità che elabora un flusso del nodo XAML e produce un altro elemento. Nell'API, un writer XAML è rappresentato dalla classe di base <xref:System.Xaml.XamlWriter>.  
  
 I due scenari più comuni che coinvolgono XAML sono il caricamento di XAML per creare un'istanza di un oggetto grafico e il salvataggio di un oggetto grafico da un'applicazione o lo strumento e che produce una rappresentazione XAML (in genere in formato di markup salvato come file di testo). Il caricamento di XAML e la creazione di un oggetto grafico viene spesso definito in questa documentazione come percorso di caricamento. Il salvataggio o la serializzazione di un oggetto grafico esistente in XAML viene spesso definito in questa documentazione Salva percorso.  
  
 Il tipo più comune di percorso di caricamento può essere descritta come segue:  
  
-   Iniziare con una rappresentazione XAML, in formato XML con codifica UTF- e salvato come file di testo.  
  
-   Caricamento in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader>è un <xref:System.Xaml.XamlReader> sottoclasse.  
  
-   Il risultato è un flusso del nodo XAML. È possibile accedere ai singoli nodi del flusso di nodi XAML tramite <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API. In questo caso l'operazione più comune è di avanzare il flusso del nodo XAML, l'elaborazione di ogni nodo con un record"corrente" metafora.  
  
-   Passare i nodi risultanti dal flusso del nodo XAML da un <xref:System.Xaml.XamlObjectWriter> API. <xref:System.Xaml.XamlObjectWriter>è un <xref:System.Xaml.XamlWriter> sottoclasse.  
  
-   Il <xref:System.Xaml.XamlObjectWriter> scrive un oggetto grafico, un oggetto alla volta, in base a stato di avanzamento tramite il flusso del nodo XAML di origine. Questa operazione viene eseguita con l'assistenza di un contesto dello schema XAML e un'implementazione che può accedere gli assembly e tipi di un sistema di tipi di backup e di framework.  
  
-   Chiamare <xref:System.Xaml.XamlObjectWriter.Result%2A> alla fine del flusso del nodo XAML per ottenere l'oggetto radice dell'oggetto grafico.  
  
 Il tipo più comune di percorso di salvataggio può essere descritta come segue:  
  
-   Iniziare con l'oggetto grafico di un intero runtime di applicazione, il contenuto dell'interfaccia utente e lo stato di una fase di esecuzione oppure un segmento più piccolo di rappresentazione dell'oggetto globale dell'applicazione in fase di esecuzione.  
  
-   Da un oggetto di avvio logico, ad esempio una radice dell'applicazione o la radice del documento, caricare gli oggetti in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader>è un <xref:System.Xaml.XamlReader> sottoclasse.  
  
-   Il risultato è un flusso del nodo XAML. È possibile accedere ai singoli nodi del flusso di nodi XAML tramite <xref:System.Xaml.XamlObjectReader> e <xref:System.Xaml.XamlReader> API. In questo caso l'operazione più comune è di avanzare il flusso del nodo XAML, l'elaborazione di ogni nodo con un record"corrente" metafora.  
  
-   Passare i nodi risultanti dal flusso del nodo XAML da un <xref:System.Xaml.XamlXmlWriter> API. <xref:System.Xaml.XamlXmlWriter>è un <xref:System.Xaml.XamlWriter> sottoclasse.  
  
-   Il <xref:System.Xaml.XamlXmlWriter> scrive XAML in un UTF XML codifica. È possibile salvare questo come un file di testo, come un flusso o in altri moduli.  
  
-   Chiamare <xref:System.Xaml.XamlXmlWriter.Flush%2A> per ottenere l'output finale.  
  
 Per ulteriori informazioni sui concetti di flusso di nodi XAML, vedere [concetti e delle strutture di flusso di nodi XAML comprensione](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>La classe XamlServices  
 Non è sempre necessario gestire un flusso del nodo XAML. Se si desidera un percorso di caricamento di base o un percorso di salvataggio di base, è possibile utilizzare l'API di <xref:System.Xaml.XamlServices> classe.  
  
-   Diverse firme di <xref:System.Xaml.XamlServices.Load%2A> implementano un percorso di caricamento. È possibile caricare un file o un flusso o caricare un <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> che esegue il wrapping dell'input XAML tramite caricamento con API che del lettore.  
  
-   Diverse firme di <xref:System.Xaml.XamlServices.Save%2A> salvare un oggetto grafico e producono l'output come flusso, file, o <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> istanza.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A>conversione di XAML tramite il collegamento di un percorso di caricamento e salvataggio percorso come una singola operazione. Un contesto dello schema diverso o un sistema di tipi diversi di backup può essere utilizzato per <xref:System.Xaml.XamlReader> e <xref:System.Xaml.XamlWriter>, che è ciò che influenza il modo in cui il codice XAML risultante viene trasformato.  
  
 Per ulteriori informazioni su come usare <xref:System.Xaml.XamlServices>, vedere [classe XAMLServices e lettura XAML di base o la scrittura](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>Sistema di tipi XAML  
 Sistema di tipi XAML fornisce le API necessarie per lavorare con un singolo nodo specifico di un flusso del nodo XAML.  
  
 <xref:System.Xaml.XamlType>è la rappresentazione per un oggetto, ciò che si stanno elaborando tra un nodo oggetto iniziale e un nodo oggetto finale.  
  
 <xref:System.Xaml.XamlMember>è la rappresentazione per un membro di un oggetto - ciò che si stanno elaborando tra un nodo membro iniziale e un nodo membro finale.  
  
 Le interfacce API <xref:System.Xaml.XamlType.GetAllMembers%2A> e <xref:System.Xaml.XamlType.GetMember%2A> e <xref:System.Xaml.XamlMember.DeclaringType%2A> segnalano le relazioni tra un <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember>.  
  
 Il comportamento predefinito di sistema di tipi XAML come implementato dai servizi XAML di .NET Framework è basato su common language runtime (CLR) e l'analisi statica di tipi CLR negli assembly tramite reflection. Pertanto, per un tipo CLR specifico, l'implementazione predefinita di sistema di tipi XAML può esporre lo schema XAML di quel tipo e i relativi membri e segnalarlo in termini di sistema di tipi XAML. Nel sistema di tipi XAML predefinito, il concetto di assegnabilità dei tipi viene eseguito il mapping all'ereditarietà CLR e i concetti di istanze, i tipi di valore e così via vengono associati ai comportamenti e caratteristiche CLR di supporto.  
  
## <a name="reference-for-xaml-language-features"></a>Riferimento per la funzionalità del linguaggio XAML  
 Per il supporto di XAML, servizi XAML di .NET Framework fornisce l'implementazione specifica di concetti del linguaggio XAML definite dello spazio dei nomi XAML del linguaggio XAML. Questi scenari sono documentati come pagine di riferimento specifico. Le funzionalità del linguaggio sono documentate dalla prospettiva del comportano di queste funzionalità del linguaggio vengono elaborati da un reader XAML o un writer XAML definito dai servizi XAML di .NET Framework. Per altre informazioni, vedere [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).
