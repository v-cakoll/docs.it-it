---
title: Servizi XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 8e1e8dc9a1410d05c19e4dd1bccb30c65d7c5e66
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837285"
---
# <a name="xaml-services"></a>Servizi XAML
In questo argomento vengono descritte le funzionalità di un set di tecnologie noto come .NET Framework servizi XAML. La maggior parte dei servizi e delle API descritti si trova nell'assembly System. XAML, un assembly introdotto con il set di .NET Framework 4 degli assembly .NET Core. I servizi includono Readers e writer, classi dello schema e supporto dello schema, Factory, attribuzione di classi, supporto intrinseco del linguaggio XAML e altre funzionalità del linguaggio XAML.  
  
## <a name="about-this-documentation"></a>Informazioni su questa documentazione  
 La documentazione concettuale per i servizi XAML .NET Framework presuppone che si disponga di un'esperienza precedente con il linguaggio XAML e il modo in cui può essere applicata a un Framework specifico, ad esempio [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] o Windows Workflow Foundation o un'area funzionale della tecnologia specifica, ad esempio le funzionalità di personalizzazione della compilazione in <xref:Microsoft.Build.Framework.XamlTypes>. Questa documentazione non tenta di spiegare le nozioni di base di XAML come linguaggio di markup, terminologia di sintassi XAML o altro materiale introduttivo. Questa documentazione è invece incentrata sull'utilizzo specifico dei servizi XAML .NET Framework abilitati nella libreria di assembly System. XAML. La maggior parte di queste API è destinata a scenari di integrazione e estensibilità del linguaggio XAML. Questo potrebbe includere uno degli elementi seguenti:  
  
- Estensione delle funzionalità dei reader XAML di base o dei writer XAML (elaborazione diretta del flusso del nodo XAML; derivazione del lettore XAML o del writer XAML).  
  
- Definizione di tipi personalizzati utilizzabili da XAML che non hanno dipendenze specifiche del Framework e attribuendo i tipi per fornire le caratteristiche del sistema di tipi XAML per .NET Framework servizi XAML.  
  
- Hosting di reader XAML o writer XAML come componente di un'applicazione, ad esempio una finestra di progettazione visiva o un editor interattivo per le origini di markup XAML.  
  
- Scrittura di convertitori di valori XAML (estensioni di markup; convertitori di tipi per tipi personalizzati).  
  
- Definizione di un contesto dello schema XAML personalizzato (utilizzando tecniche di caricamento di assembly alternative per il supporto di origini dei tipi; utilizzo di tecniche di ricerca di tipi noti anziché di sempre gli assembly; utilizzo di concetti di assembly caricati che non utilizzano il `AppDomain` CLR e il modello di sicurezza associato).  
  
- Estensione del sistema di tipi XAML di base.  
  
- Utilizzando le tecniche di `Lookup` o `Invoker` per influenzare il sistema di tipi XAML e il modo in cui vengono valutati i backup dei tipi.  
  
 Se si sta cercando materiale introduttivo in XAML come linguaggio, è possibile provare [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md). In questo argomento viene illustrato XAML per un pubblico che è nuovo per [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] e anche per utilizzare markup XAML e funzionalità del linguaggio XAML. Un altro documento utile è il materiale introduttivo nella [specifica del linguaggio XAML](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET Framework i servizi XAML e System. XAML nell'architettura .NET  
 Nelle versioni precedenti di Microsoft .NET Framework, il supporto per le funzionalità del linguaggio XAML è stato implementato dai Framework basati su Microsoft .NET Framework ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation e Windows Communication Foundation (WCF)) e pertanto varia nel suo comportamento e nell'API usata a seconda del Framework specifico in uso. Sono inclusi il parser XAML e il relativo meccanismo di creazione di oggetti grafici, intrinseci del linguaggio XAML, supporto della serializzazione e così via.  
  
 In .NET Framework 4 .NET Framework servizi XAML e l'assembly System. Xaml definiscono la maggior parte degli elementi necessari per il supporto delle funzionalità del linguaggio XAML. Sono incluse le classi di base per i reader XAML e i writer XAML. La funzionalità più importante aggiunta a .NET Framework servizi XAML che non era presente in alcuna implementazione XAML specifica del Framework è una rappresentazione del sistema di tipi per XAML. La rappresentazione del sistema di tipi presenta il codice XAML in un modo orientato agli oggetti che centra sulle funzionalità XAML senza prendere le dipendenze da funzionalità specifiche dei Framework.  
  
 Il sistema di tipi XAML non è limitato dalle specifiche del formato di markup o della fase di esecuzione dell'origine XAML. né è limitato da alcun sistema di tipi di supporto specifico. Il sistema di tipi XAML include rappresentazioni di oggetti per tipi, membri, contesti di schema XAML, concetti a livello di XML e altri concetti del linguaggio XAML o funzioni intrinseche XAML. L'utilizzo o l'estensione del sistema di tipi XAML rende possibile la derivazione da classi quali reader XAML e writer XAML ed estendere la funzionalità delle rappresentazioni XAML in funzionalità specifiche abilitate da un Framework, una tecnologia o un'applicazione che utilizza o genera XAML. Il concetto di contesto dello schema XAML consente operazioni pratiche di scrittura di oggetti grafici dalla combinazione di un'implementazione di writer di oggetti XAML, un sistema di tipi di supporto della tecnologia come comunicato tramite le informazioni sull'assembly nel contesto e il nodo XAML origine. Per ulteriori informazioni sul concetto di schema XAML. vedere [contesto dello schema XAML predefinito e contesto dello schema XAML WPF](default-xaml-schema-context-and-wpf-xaml-schema-context.md).  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Flussi di nodi XAML, reader XAML e writer XAML  
 Per comprendere il ruolo che .NET Framework servizi XAML svolge nella relazione tra il linguaggio XAML e le tecnologie specifiche che usano XAML come linguaggio, è utile comprendere il concetto di flusso di nodi XAML e il modo in cui tale concetto forma l'API e terminologia. Il flusso di nodi XAML è un intermediario concettuale tra una rappresentazione del linguaggio XAML e l'oggetto grafico rappresentato o definito da XAML.  
  
- Un reader XAML è un'entità che elabora XAML in un formato e produce un flusso di nodi XAML. Nell'API un reader XAML è rappresentato dalla classe base <xref:System.Xaml.XamlReader>.  
  
- Un writer XAML è un'entità che elabora un flusso di nodi XAML e produce qualcos'altro. Nell'API un writer XAML è rappresentato dalla classe base <xref:System.Xaml.XamlWriter>.  
  
 I due scenari più comuni che coinvolgono XAML sono il caricamento di XAML per creare un'istanza di un oggetto grafico e il salvataggio di un oggetto grafico da un'applicazione o da uno strumento e la generazione di una rappresentazione XAML, in genere in formato di markup salvata come file di testo. Il caricamento di XAML e la creazione di un oggetto grafico vengono spesso indicati in questa documentazione come percorso di caricamento. Il salvataggio o la serializzazione di un oggetto grafico esistente in XAML viene spesso indicato in questa documentazione come percorso di salvataggio.  
  
 Il tipo più comune di percorso di caricamento può essere descritto di seguito:  
  
- Iniziare con una rappresentazione XAML, in formato XML con codifica UTF e salvata come file di testo.  
  
- Caricare il codice XAML in <xref:System.Xaml.XamlXmlReader>. <xref:System.Xaml.XamlXmlReader> è una sottoclasse <xref:System.Xaml.XamlReader>.  
  
- Il risultato è un flusso di nodi XAML. È possibile accedere ai singoli nodi del flusso del nodo XAML usando <xref:System.Xaml.XamlXmlReader>API <xref:System.Xaml.XamlReader>  / . L'operazione più comune consiste nell'avanzare nel flusso del nodo XAML, elaborando ogni nodo usando una metafora "record corrente".  
  
- Passare i nodi risultanti dal flusso del nodo XAML a un'API <xref:System.Xaml.XamlObjectWriter>. <xref:System.Xaml.XamlObjectWriter> è una sottoclasse <xref:System.Xaml.XamlWriter>.  
  
- Il <xref:System.Xaml.XamlObjectWriter> scrive un oggetto grafico, un oggetto alla volta, in base allo stato di avanzamento attraverso il flusso del nodo XAML di origine. Questa operazione viene eseguita con l'assistenza di un contesto dello schema XAML e di un'implementazione di che può accedere agli assembly e ai tipi di un Framework e di un sistema di tipi di supporto.  
  
- Chiamare <xref:System.Xaml.XamlObjectWriter.Result%2A> alla fine del flusso del nodo XAML per ottenere l'oggetto radice dell'oggetto grafico.  
  
 Il tipo più comune di percorso di salvataggio può essere descritto di seguito:  
  
- Iniziare con l'oggetto grafico di un'intera fase di esecuzione dell'applicazione, il contenuto dell'interfaccia utente e lo stato di una fase di esecuzione oppure un segmento più piccolo della rappresentazione dell'oggetto di un'applicazione complessiva in fase di esecuzione.  
  
- Da un oggetto iniziale logico, ad esempio una radice dell'applicazione o una radice del documento, caricare gli oggetti in <xref:System.Xaml.XamlObjectReader>. <xref:System.Xaml.XamlObjectReader> è una sottoclasse <xref:System.Xaml.XamlReader>.  
  
- Il risultato è un flusso di nodi XAML. È possibile accedere ai singoli nodi del flusso del nodo XAML usando <xref:System.Xaml.XamlObjectReader> e <xref:System.Xaml.XamlReader> API. L'operazione più comune consiste nell'avanzare nel flusso del nodo XAML, elaborando ogni nodo usando una metafora "record corrente".  
  
- Passare i nodi risultanti dal flusso del nodo XAML a un'API <xref:System.Xaml.XamlXmlWriter>. <xref:System.Xaml.XamlXmlWriter> è una sottoclasse <xref:System.Xaml.XamlWriter>.  
  
- Il <xref:System.Xaml.XamlXmlWriter> scrive XAML in una codifica UTF XML. È possibile salvarlo come file di testo, come flusso o in altri moduli.  
  
- Chiamare <xref:System.Xaml.XamlXmlWriter.Flush%2A> per ottenere l'output finale.  
  
 Per altre informazioni sui concetti relativi al flusso di nodi XAML, vedere [informazioni sulle strutture e sui concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md).  
  
### <a name="the-xamlservices-class"></a>Classe XamlServices  
 Non è sempre necessario gestire un flusso di nodi XAML. Se si vuole un percorso di caricamento di base o un percorso di salvataggio di base, è possibile usare le API nella classe <xref:System.Xaml.XamlServices>.  
  
- Diverse firme di <xref:System.Xaml.XamlServices.Load%2A> implementano un percorso di caricamento. È possibile caricare un file o un flusso oppure è possibile caricare un <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> o <xref:System.Xaml.XamlReader> che esegue il wrapping dell'input XAML caricando le API del lettore.  
  
- Diverse firme di <xref:System.Xaml.XamlServices.Save%2A> salvano un oggetto grafico e producono l'output come flusso, file o <xref:System.Xml.XmlWriter>/istanza <xref:System.IO.TextWriter>.  
  
- <xref:System.Xaml.XamlServices.Transform%2A> converte XAML collegando un percorso di caricamento e un percorso di salvataggio come singola operazione. È possibile usare un contesto dello schema diverso o un sistema di tipi di supporto diverso per <xref:System.Xaml.XamlReader> e <xref:System.Xaml.XamlWriter>, che influisce sul modo in cui il codice XAML risultante viene trasformato.  
  
 Per ulteriori informazioni sull'utilizzo di <xref:System.Xaml.XamlServices>, vedere [classe XamlServices e lettura o scrittura di codice XAML di base](xamlservices-class-and-basic-xaml-reading-or-writing.md).  
  
## <a name="xaml-type-system"></a>Sistema di tipi XAML  
 Il sistema di tipi XAML fornisce le API necessarie per lavorare con un singolo nodo di un flusso di nodi XAML.  
  
 <xref:System.Xaml.XamlType> è la rappresentazione per un oggetto, ovvero ciò che si sta elaborando tra un nodo oggetto iniziale e un nodo oggetto finale.  
  
 <xref:System.Xaml.XamlMember> è la rappresentazione per un membro di un oggetto, che viene elaborato tra un nodo membro iniziale e un nodo membro finale.  
  
 API come <xref:System.Xaml.XamlType.GetAllMembers%2A> e <xref:System.Xaml.XamlType.GetMember%2A> e <xref:System.Xaml.XamlMember.DeclaringType%2A> segnalano le relazioni tra un <xref:System.Xaml.XamlType> e un <xref:System.Xaml.XamlMember>.  
  
 Il comportamento predefinito del sistema di tipi XAML implementato da .NET Framework servizi XAML è basato sul Common Language Runtime (CLR) e sull'analisi statica dei tipi CLR negli assembly tramite reflection. Pertanto, per un tipo CLR specifico, l'implementazione predefinita del sistema di tipi XAML può esporre lo schema XAML di quel tipo e i relativi membri e segnalarlo in termini di sistema di tipi XAML. Nel sistema di tipi XAML predefinito, il concetto di assegnabilità dei tipi viene mappato all'ereditarietà CLR e i concetti di istanze, tipi di valore e così via vengono mappati anche ai comportamenti e alle funzionalità di supporto di CLR.  
  
## <a name="reference-for-xaml-language-features"></a>Informazioni di riferimento sulle funzionalità del linguaggio XAML  
 Per supportare XAML, .NET Framework servizi XAML fornisce un'implementazione specifica dei concetti del linguaggio XAML come definito per lo spazio dei nomi XAML del linguaggio XAML. Questi sono documentati come pagine di riferimento specifiche. Le funzionalità del linguaggio sono documentate dal punto di vista del comportamento di queste funzionalità del linguaggio quando vengono elaborate da un reader XAML o da un writer XAML definito da .NET Framework servizi XAML. Per altre informazioni, vedere [XAML Namespace (x:) Language Features](xaml-namespace-x-language-features.md).
