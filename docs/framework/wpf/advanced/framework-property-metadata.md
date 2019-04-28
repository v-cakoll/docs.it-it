---
title: Metadati delle proprietà del framework
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 2a20e5a2bdbcbb36f6f06bbbadb2a46743ca5eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703335"
---
# <a name="framework-property-metadata"></a>Metadati delle proprietà del framework
Per le proprietà degli elementi oggetto considerati situati a livello di framework WPF nell'architettura di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono segnalate le opzioni di metadati delle proprietà del framework. In generale, la designazione a livello di framework WPF implica che funzionalità quali il rendering, il data binding e i miglioramenti del sistema di proprietà vengano gestite dalle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di presentazione di [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] e dai file eseguibili. Questi sistemi eseguono una query sui metadati delle proprietà del framework per determinare le caratteristiche specifiche delle funzionalità di particolari proprietà dell'elemento.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). È inoltre necessario aver letto l'argomento [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Contenuto dei metadati delle proprietà del framework  
 I metadati delle proprietà del framework possono essere suddivisi nelle seguenti categorie:  
  
- Proprietà di layout che influiscono su un elemento di report (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). È possibile impostare questi flag nei metadati se la proprietà influisce sui rispettivi aspetti e si implementano anche il <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi nella classe per fornire informazioni al layout e il comportamento di rendering specifiche System. In genere, tale implementazione verificherebbe le convalide delle proprietà nelle proprietà di dipendenza, qualora una di tali proprietà di layout risultasse impostata su true nei metadati della proprietà; solo tali convalide richiederebbero un nuovo passaggio di layout.  
  
- Proprietà di layout che influiscono sull'elemento padre di un elemento di report (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). Sono riportati alcuni esempi in cui questi flag sono impostati per impostazione predefinita <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> e <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. Per impostazione predefinita, le proprietà di dipendenza non ereditano valori. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> Consente di trasferire il percorso dell'ereditarietà anche in una struttura ad albero visuale, operazione necessaria per alcuni scenari di composizione del controllo.  
  
    > [!NOTE]
    >  Il termine "ereditarietà" nel contesto dei valori della proprietà è specifico delle proprietà di dipendenza e indica che gli elementi figlio possono ereditare il valore della proprietà di dipendenza effettivo dagli elementi padre grazie a una funzionalità a livello di framework WPF del sistema di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Non è correlato direttamente al tipo di codice gestito né all'ereditarietà dei membri tramite tipi derivati. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).  
  
- La segnalazione delle caratteristiche di associazione dati (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). Per impostazione predefinita, le proprietà di dipendenza nel framework supportano il data binding, con un comportamento di associazione unidirezionale. Se non è immaginabile alcuno scenario per il data binding, è possibile disabilitare questa funzionalità (dal momento che sono progettate per essere flessibili ed estensibili, non sono previsti molti esempi di proprietà di questo tipo nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] predefinite). È possibile impostare l'associazione per avere un'impostazione predefinita bidirezionale per le proprietà che collegano i comportamenti di un controllo tra i suoi componenti (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> è riportato un esempio) o in cui associazione bidirezionale è lo scenario comune e previsto per gli utenti (<xref:System.Windows.Controls.TextBox.Text%2A> è riportato un esempio). La modifica dei metadati correlati al data binding ha effetto sull'impostazione predefinita. È sempre possibile modificare l'impostazione predefinita per una singola associazione. Per maggiori dettagli sulle modalità di associazione e sull'associazione in generale, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).  
  
- Creazione di report se le proprietà devono essere inserite nel journal da applicazioni o servizi che supportano l'inserimento nel journal (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). Per impostazione predefinita, l'inserimento nel giornale di registrazione non è abilitato per gli elementi generali, ma è abilitato in maniera selettiva per determinati controlli di input dell'utente. Questa proprietà deve essere letta dai servizi di inserimento nel giornale di registrazione, inclusa l'implementazione dell'inserimento nel giornale di registrazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è impostata nei controlli utente, ad esempio le selezioni dell'utente all'interno di elenchi che devono essere resi persistenti nei vari passaggi di navigazione. Per informazioni sull'inserimento nel giornale di registrazione, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Lettura di FrameworkPropertyMetadata  
 Ognuna delle proprietà con collegata riportato sopra sono le proprietà specifiche che il <xref:System.Windows.FrameworkPropertyMetadata> aggiunge alla relativa classe base immediata <xref:System.Windows.UIPropertyMetadata>. Per impostazione predefinita, ognuna di queste proprietà sarà `false`. Una richiesta di metadati per una proprietà in cui è importante conoscere il valore di queste proprietà tenti di eseguire il cast dei metadati restituiti al <xref:System.Windows.FrameworkPropertyMetadata>e quindi controllare i valori delle singole proprietà in base alle esigenze.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Specifica dei metadati  
 Quando si crea una nuova istanza di metadati per scopi di applicare i metadati per una nuova registrazione di proprietà di dipendenza, è possibile scegliere quali della classe di metadati da utilizzare: di base <xref:System.Windows.PropertyMetadata> o, ad esempio una classe derivata <xref:System.Windows.FrameworkPropertyMetadata>. In generale, è consigliabile usare <xref:System.Windows.FrameworkPropertyMetadata>, in particolare se la proprietà qualsiasi interazione con il sistema di proprietà e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzioni quali layout e il data binding. Deve derivare da un'altra opzione per scenari più sofisticati <xref:System.Windows.FrameworkPropertyMetadata> per creare i propri metadati reporting classe con informazioni aggiuntive contenute nei relativi membri. In alternativa è possibile utilizzare <xref:System.Windows.PropertyMetadata> o <xref:System.Windows.UIPropertyMetadata> per comunicare il livello di supporto delle funzionalità dell'implementazione.  
  
 Per le proprietà esistenti (<xref:System.Windows.DependencyProperty.AddOwner%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> chiamare), è sempre consigliabile eseguire l'override con il tipo di metadati usato nella registrazione originale.  
  
 Se si sta creando un <xref:System.Windows.FrameworkPropertyMetadata> dell'istanza, esistono due modi per popolare i metadati con i valori per le proprietà specifiche che comunicano le caratteristiche delle proprietà del framework:  
  
1. Usare la <xref:System.Windows.FrameworkPropertyMetadata> firma del costruttore che accetta un `flags` parametro. Questo parametro deve essere riempito con desiderati tutti i valori combinati del <xref:System.Windows.FrameworkPropertyMetadataOptions> flag dell'enumerazione.  
  
2. Usare una delle firme senza un `flags` parametro e quindi impostare ciascuna proprietà booleana di creazione di report sul <xref:System.Windows.FrameworkPropertyMetadata> a `true` per ogni modifica delle caratteristiche desiderata. In questo caso, è necessario impostare queste proprietà prima della costruzione di qualsiasi elemento con questa proprietà di dipendenza. Le proprietà booleane sono configurate per la lettura e la scrittura, in modo da consentire di popolare i metadati evitando l'inserimento del parametro `flags`; tuttavia, i metadati devono essere contrassegnati come sealed prima che la proprietà venga usata. Il tentativo di impostare le proprietà dopo la richiesta dei metadati sarà pertanto considerato un'operazione non valida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Comportamento di unione dei metadati delle proprietà del framework  
 Quando si esegue l'override dei metadati delle proprietà del framework, le diverse caratteristiche dei metadati vengono unite o sostituite.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> viene unito. Se si aggiunge un nuovo <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, quel callback viene archiviato nei metadati. Se non si specifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> nell'override, il valore di <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> viene promosso come riferimento dal predecessore più vicino che lo aveva specificato nei metadati.  
  
- Il comportamento effettivo della proprietà del sistema per <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> è che le implementazioni per tutti i proprietari di metadati nella gerarchia vengano mantenuti e aggiunte a una tabella, con ordine di esecuzione dal sistema di proprietà è che i callback della classe derivata richiamato per primo. I callback ereditati vengono eseguiti solo una volta, essendo considerati come appartenenti alla classe che li aveva posizionati nei metadati.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A> è stato sostituito. Se non si specifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> nell'override, il valore di <xref:System.Windows.PropertyMetadata.DefaultValue%2A> proviene dal predecessore più vicino che lo aveva specificato nei metadati.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> le implementazioni vengono sostituite. Se si aggiunge un nuovo <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, quel callback viene archiviato nei metadati. Se non si specifica un <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> nell'override, il valore di <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> viene promosso come riferimento dal predecessore più vicino che lo aveva specificato nei metadati.  
  
- Il comportamento del sistema di proprietà è che solo il <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> dei metadati immediati viene richiamato. Nessun riferimento ad altri <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> vengono mantenute le implementazioni della gerarchia.  
  
- I flag di <xref:System.Windows.FrameworkPropertyMetadataOptions> enumerazione vengono combinati in un'operazione OR bit per bit.  Se si specifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, le opzioni originali non vengono sovrascritti.  Per modificare un'opzione, impostare la proprietà corrispondente su <xref:System.Windows.FrameworkPropertyMetadata>. Ad esempio, se originale <xref:System.Windows.FrameworkPropertyMetadata> set di oggetti di <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> flag, è possibile modificarlo impostando <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> a `false`.  
  
 Questo comportamento viene implementato mediante <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>e può essere sottoposto a override nelle classi di metadati derivate.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
