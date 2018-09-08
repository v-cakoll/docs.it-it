---
title: Servizi XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 373478e8c21fca66cbfbf7a58fc7d53f65ce5d0b
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141087"
---
# <a name="xaml-services"></a>Servizi XAML
In questo argomento descrive le funzionalità di un set di tecnologie noto come .NET Framework XAML Services. La maggior parte dei servizi e le API descritte si trovano nell'assembly System. XAML, che è un assembly è stato introdotto con la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] set degli assembly di .NET core. I servizi includono lettori e writer, le classi dello schema e supporto dello schema, factory, assegnazione di attributi di classi di supporto intrinseco del linguaggio XAML e altre funzionalità del linguaggio XAML.  
  
## <a name="about-this-documentation"></a>Informazioni sulla documentazione  
 Documentazione concettuale per i servizi XAML di .NET Framework presuppone che si ha esperienza precedente con il linguaggio XAML e come può applicare a un framework specifico, ad esempio [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Windows Workflow Foundation o una caratteristica di tecnologia specifica area, ad esempio la personalizzazione di compilazione funzionalità nella <xref:Microsoft.Build.Framework.XamlTypes>. Questa documentazione non tenta di spiegare i concetti fondamentali di XAML come linguaggio di markup, terminologia della sintassi XAML o altro materiale introduttivo. Al contrario, questa documentazione illustra l'uso in modo specifico i servizi XAML di .NET Framework che sono abilitati nella libreria dell'assembly System. Xaml. La maggior parte di queste API sono per gli scenari di estendibilità e integrazione del linguaggio XAML. Ciò potrebbe includere gli elementi seguenti:  
  
-   Estendere le funzionalità del reader XAML base o i writer XAML (elaborazione direttamente il flusso del nodo XAML, che deriva il proprio reader XAML o writer XAML).  
  
-   La definizione XAML utilizzabile tipi personalizzati che non hanno dipendenze framework specifico e assegnazione di attributi ai tipi per indicare loro XAML digitare le caratteristiche del sistema di servizi XAML di .NET Framework.  
  
-   Hosting XAML lettori o writer XAML come componente di un'applicazione, ad esempio una finestra di progettazione visiva o un editor interattivo per le origini di markup XAML.  
  
-   Scrittura di XAML convertitori di valori (estensioni di markup; convertitori di tipi per i tipi personalizzati).  
  
-   Definisce un contesto dello schema XAML personalizzato (usando tecniche di caricamento di assembly alternative per le origini di tipo sottostante; usando tecniche di ricerca di tipi noti invece sempre che riflette gli assembly; utilizzando i concetti di assembly caricato che non utilizzano CLR `AppDomain` e il modello di sicurezza associati).  
  
-   Estende il sistema di tipo XAML di base.  
  
-   Usando il `Lookup` o `Invoker` tecniche per influenzare il XAML digitare system e la modalità di valutazione dei tipi di supporto.  
  
 Se sta cercando il materiale introduttivo in XAML come linguaggio, è possibile provare [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Tale argomento sono illustrate XAML per un gruppo di destinatari che rappresenta una novità a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] e anche all'uso di markup XAML e le funzionalità del linguaggio XAML. Un altro documento utile è il materiale introduttivo nel [specifiche del linguaggio XAML](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>Servizi XAML di .NET framework e System. XAML dell'architettura .NET  
 Nelle versioni precedenti di Microsoft .NET Framework, il supporto per le funzionalità del linguaggio XAML è stato implementato da Framework basati su Microsoft .NET Framework ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation e Windows Communication Foundation (WCF)) e pertanto diversi a seconda del framework specifico si usava il relativo comportamento e l'API usata. Inclusi il XAML parser e il relativo oggetto grafico meccanismo di creazione, intrinseci del linguaggio XAML, il supporto della serializzazione e così via.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], dei servizi XAML di .NET Framework e l'assembly System. XAML definire gran parte delle informazioni necessarie per supportare le funzionalità del linguaggio XAML. Ciò include le classi di base per i lettori XAML e writer XAML. La caratteristica più importante aggiunta a servizi XAML .NET Framework che non era presente in una qualsiasi delle implementazioni specifiche del framework XAML è una rappresentazione di sistema di tipo per XAML. La rappresentazione del sistema tipo presenta XAML in una modalità orientata agli oggetti che si concentra sulle funzionalità di XAML senza le dipendenze sulle funzionalità specifiche del Framework.  
  
 Il sistema di tipi XAML non è limitato dal modulo di markup o in fase di esecuzione specifiche dell'origine XAML; né è limitata da qualsiasi sistema di tipi di supporto specifici. Il sistema di tipi XAML include le rappresentazioni di oggetti per i tipi, membri, contesti dello schema XAML, i concetti a livello di XML e altri concetti del linguaggio XAML o oggetti intrinseci XAML. Utilizzo o l'estensione del sistema di tipi XAML consente di derivare dalle classi, ad esempio lettori XAML e writer XAML ed estendere le funzionalità delle rappresentazioni XAML in specifiche funzionalità abilitate da un framework, una tecnologia o un'applicazione che utilizza o genera XAML. Il concetto di un contesto dello schema XAML consente le operazioni di scrittura grafo di oggetto pratico dalla combinazione di un'implementazione del writer di oggetti XAML, sistema di tipi di supporto di una tecnologia comunicato tramite informazioni sull'assembly nel contesto e il nodo XAML origine. Per altre informazioni sul concetto dello schema XAML. visualizzare [contesto dello Schema XAML predefinito e contesto dello Schema XAML WPF](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Flussi del nodo XAML reader XAML e writer XAML  
 Per comprendere il ruolo di servizi XAML di .NET Framework riproduce nel rapporto tra le tecnologie specifiche che usano XAML come linguaggio e il linguaggio XAML, è utile comprendere il concetto di un flusso del nodo XAML e come tale concetto forme dell'API e terminologia. Il flusso di nodi XAML è un concettuale intermedio tra l'oggetto grafico che rappresenta il XAML o, definisce e una rappresentazione in linguaggio XAML.  
  
-   Un lettore XAML è un'entità che elabora XAML in una determinata forma e produce un flusso di nodi XAML. Nell'API, un lettore XAML è rappresentato dalla classe di base <xref:System.Xaml.XamlReader>.  
  
-   Un writer XAML è un'entità che elabora un flusso del nodo XAML e produce un altro elemento. Nell'API, un writer XAML è rappresentato dalla classe di base <xref:System.Xaml.XamlWriter>.  
  
 I due scenari più comuni che coinvolgono XAML sono il caricamento di XAML per creare un'istanza di un oggetto grafico e il salvataggio di un oggetto grafico da un'applicazione o lo strumento e creazione di una rappresentazione XAML (in genere nel modulo di markup salvato come file di testo). Caricamento XAML e la creazione di un oggetto grafico viene spesso definito in questa documentazione come percorso di caricamento. Il salvataggio o la serializzazione di un oggetto grafico esistente in XAML viene spesso definito in questa documentazione come Salva percorso.  
  
 Il tipo più comune del percorso di caricamento può essere descritte come segue:  
  
-   Iniziare con una rappresentazione XAML, in formato XML con codifica UTF- e salvati come file di testo.  
  
-   Caricamento di XAML in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> è un <xref:System.Xaml.XamlReader> sottoclasse.  
  
-   Il risultato è un flusso di nodi XAML. È possibile accedere ai singoli nodi del flusso di nodi XAML tramite <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API. In questo caso l'operazione più comune consiste nel passare attraverso il flusso di nodi XAML, l'elaborazione di ogni nodo usando un record"corrente" metafora.  
  
-   Passare i nodi risultanti dal flusso di nodi XAML per un <xref:System.Xaml.XamlObjectWriter> API. <xref:System.Xaml.XamlObjectWriter> è un <xref:System.Xaml.XamlWriter> sottoclasse.  
  
-   Il <xref:System.Xaml.XamlObjectWriter> scrive un oggetto grafico, un oggetto alla volta, in base allo stato di avanzamento tramite il flusso di nodi XAML di origine. Questa operazione viene eseguita con l'assistenza di un contesto dello schema XAML e un'implementazione che può accedere gli assembly e tipi di un sistema di tipo di supporto e framework.  
  
-   Chiamare <xref:System.Xaml.XamlObjectWriter.Result%2A> alla fine del flusso di nodi XAML per ottenere l'oggetto radice dell'oggetto grafico.  
  
 Il tipo più comune di percorso di salvataggio può essere descritte come segue:  
  
-   Iniziare con l'oggetto grafico di un'ora di esecuzione dell'intera applicazione, il contenuto dell'interfaccia utente e lo stato di una fase di esecuzione, o un segmento più piccolo di rappresentazione dell'oggetto complessiva dell'applicazione in fase di esecuzione.  
  
-   Da un oggetto di avvio logico, ad esempio una directory radice dell'applicazione o radice del documento, caricare gli oggetti in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> è un <xref:System.Xaml.XamlReader> sottoclasse.  
  
-   Il risultato è un flusso di nodi XAML. È possibile accedere ai singoli nodi del flusso di nodi XAML tramite <xref:System.Xaml.XamlObjectReader> e <xref:System.Xaml.XamlReader> API. In questo caso l'operazione più comune consiste nel passare attraverso il flusso di nodi XAML, l'elaborazione di ogni nodo usando un record"corrente" metafora.  
  
-   Passare i nodi risultanti dal flusso di nodi XAML per un <xref:System.Xaml.XamlXmlWriter> API. <xref:System.Xaml.XamlXmlWriter> è un <xref:System.Xaml.XamlWriter> sottoclasse.  
  
-   Il <xref:System.Xaml.XamlXmlWriter> scrive XAML in un UTF XML codifica. È possibile salvare questo come file di testo, come un flusso o in altri formati.  
  
-   Chiamare <xref:System.Xaml.XamlXmlWriter.Flush%2A> per ottenere l'output finale.  
  
 Per altre informazioni sui concetti di flusso di nodi XAML, vedere [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>Classe XamlServices  
 Non è sempre necessario gestire un flusso di nodi XAML. Se si desidera che un percorso di caricamento di base o un percorso di salvataggio di base, è possibile usare le API nel <xref:System.Xaml.XamlServices> classe.  
  
-   Varie firme di <xref:System.Xaml.XamlServices.Load%2A> implementare un percorso di caricamento. È possibile caricare un file o un flusso o in grado di caricare un' <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> che eseguono il wrapping l'input XAML tramite caricamento con le API del lettore.  
  
-   Varie firme dei <xref:System.Xaml.XamlServices.Save%2A> salvare un grafico di oggetti e producono l'output come un flusso, file, oppure <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> istanza.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A> Converte XAML mediante il collegamento di un percorso di caricamento e salvataggio percorso come un'unica operazione. Un contesto dello schema diverso o un sistema di tipi di backup può essere usato per <xref:System.Xaml.XamlReader> e <xref:System.Xaml.XamlWriter>, ossia ciò che influenza il modo in cui il XAML risultante viene trasformato.  
  
 Per altre informazioni su come usare <xref:System.Xaml.XamlServices>, vedere [classe XAMLServices e lettura di XAML di base o la scrittura](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>Sistema di tipi XAML  
 Il sistema di tipi XAML fornisce le API necessarie per lavorare con un determinato nodo singolo di un flusso di nodi XAML.  
  
 <xref:System.Xaml.XamlType> è la rappresentazione per un oggetto - che cosa si sta elaborando tra un nodo oggetto iniziale e un nodo oggetto finale.  
  
 <xref:System.Xaml.XamlMember> è la rappresentazione per un membro di un oggetto - che cosa si sta elaborando tra un nodo membro iniziale e un nodo membro finale.  
  
 Le API, ad esempio <xref:System.Xaml.XamlType.GetAllMembers%2A> e <xref:System.Xaml.XamlType.GetMember%2A> e <xref:System.Xaml.XamlMember.DeclaringType%2A> segnalano le relazioni tra una <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember>.  
  
 Il comportamento predefinito del sistema di tipi XAML come implementato dai servizi XAML di .NET Framework è basato su common language runtime (CLR) e l'analisi statica di tipi CLR negli assembly tramite reflection. Pertanto, per un tipo CLR specifico, l'implementazione predefinita del sistema di tipi XAML possa esporre lo schema XAML di quel tipo e i relativi membri e segnalarlo in termini di sistema di tipi XAML. Nel sistema di tipi XAML predefinito, il concetto di assegnabilità dei tipi viene eseguito il mapping all'ereditarietà CLR e i concetti di istanze, i tipi di valore e così via vengono associati ai comportamenti e caratteristiche CLR di supporto.  
  
## <a name="reference-for-xaml-language-features"></a>Informazioni di riferimento per le funzionalità del linguaggio XAML  
 Per supportare XAML, dei servizi XAML di .NET Framework fornisce l'implementazione specifica di concetti del linguaggio XAML definite per spazio dei nomi XAML del linguaggio XAML. Questi scenari sono documentati come pagine di riferimento specifiche. Le funzionalità del linguaggio sono documentate dalla prospettiva del comportano di queste funzionalità del linguaggio quando vengono elaborati da un writer XAML che è definito dai servizi XAML di .NET Framework o un lettore XAML. Per altre informazioni, vedere [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).
