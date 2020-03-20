---
title: Metadati delle proprietà del framework
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 8fb6e1b4cf6aed9454e9e9f1a77277d2f3611ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186658"
---
# <a name="framework-property-metadata"></a>Metadati delle proprietà del framework
Per le proprietà degli elementi oggetto considerati situati a livello di framework WPF nell'architettura di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono segnalate le opzioni di metadati delle proprietà del framework. In generale, la designazione a livello di framework WPFWPF implica che funzionalità quali il rendering, l'associazione dati e i perfezionamenti del sistema di proprietà vengano gestite dalle API di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentazione e dagli eseguibili. Questi sistemi eseguono una query sui metadati delle proprietà del framework per determinare le caratteristiche specifiche delle funzionalità di particolari proprietà dell'elemento.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). È inoltre necessario aver letto l'argomento [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>
## <a name="what-is-communicated-by-framework-property-metadata"></a>Contenuto dei metadati delle proprietà del framework  
 I metadati delle proprietà del framework possono essere suddivisi nelle seguenti categorie:  
  
- Creazione di report sulle<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>proprietà <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>di layout che influiscono su un elemento ( , , ). È possibile impostare questi flag nei metadati se la proprietà <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> influisce su tali aspetti e si implementano anche i metodi nella classe per fornire informazioni e comportamento di rendering specifici al sistema di layout. In genere, tale implementazione verificherebbe le convalide delle proprietà nelle proprietà di dipendenza, qualora una di tali proprietà di layout risultasse impostata su true nei metadati della proprietà; solo tali convalide richiederebbero un nuovo passaggio di layout.  
  
- Segnalazione delle proprietà di layout che<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>influiscono sull'elemento padre di un elemento ( , ). Alcuni esempi in cui questi <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> flag <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>sono impostati per impostazione predefinita sono e .  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. Per impostazione predefinita, le proprietà di dipendenza non ereditano valori. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>consente al percorso di ereditarietà di viaggiare anche in una struttura ad albero visuale, necessaria per alcuni scenari di composizione dei controlli.  
  
    > [!NOTE]
    > Il termine "ereditarietà" nel contesto dei valori della proprietà è specifico delle proprietà di dipendenza e indica che gli elementi figlio possono ereditare il valore della proprietà di dipendenza effettivo dagli elementi padre grazie a una funzionalità a livello di framework WPF del sistema di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Non è correlato direttamente al tipo di codice gestito né all'ereditarietà dei membri tramite tipi derivati. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).  
  
- Caratteristiche di associazione dati di report (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). Per impostazione predefinita, le proprietà di dipendenza nel framework supportano il data binding, con un comportamento di associazione unidirezionale. È possibile disabilitare l'associazione dati se non vi è alcuno scenario per esso (perché sono destinati a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] essere flessibile ed estensibile, non ci sono molti esempi di tali proprietà nelle API predefinite). È possibile impostare l'associazione per avere un valore predefinito bidirezionale per le<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> proprietà che collegano i comportamenti di un controllo tra<xref:System.Windows.Controls.TextBox.Text%2A> le parti del componente (è un esempio) o in cui l'associazione bidirezionale è lo scenario comune e previsto per gli utenti (è un esempio). La modifica dei metadati correlati al data binding ha effetto sull'impostazione predefinita. È sempre possibile modificare l'impostazione predefinita per una singola associazione. Per maggiori dettagli sulle modalità di associazione e sull'associazione in generale, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Segnalazione se le proprietà devono essere inserite<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>nel journal da applicazioni o servizi che supportano l'inserimento nel journal ( ). Per impostazione predefinita, l'inserimento nel giornale di registrazione non è abilitato per gli elementi generali, ma è abilitato in maniera selettiva per determinati controlli di input dell'utente. Questa proprietà deve essere letta dai servizi di inserimento nel giornale di registrazione, inclusa l'implementazione dell'inserimento nel giornale di registrazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è impostata nei controlli utente, ad esempio le selezioni dell'utente all'interno di elenchi che devono essere resi persistenti nei vari passaggi di navigazione. Per informazioni sull'inserimento nel giornale di registrazione, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>
## <a name="reading-frameworkpropertymetadata"></a>Lettura di FrameworkPropertyMetadata  
 Ognuna delle proprietà collegate in <xref:System.Windows.FrameworkPropertyMetadata> precedenza sono le <xref:System.Windows.UIPropertyMetadata>proprietà specifiche che aggiunge alla relativa classe base immediata. Per impostazione predefinita, ognuna di queste proprietà sarà `false`. Una richiesta di metadati per una proprietà in cui conoscere il valore <xref:System.Windows.FrameworkPropertyMetadata>di queste proprietà è importante deve tentare di eseguire il cast dei metadati restituiti a , quindi controllare i valori delle singole proprietà in base alle esigenze.  
  
<a name="Specifying_Metadata"></a>
## <a name="specifying-metadata"></a>Specifica dei metadati  
 Quando si crea una nuova istanza di metadati allo scopo di applicare metadati a una nuova registrazione <xref:System.Windows.PropertyMetadata> della proprietà di <xref:System.Windows.FrameworkPropertyMetadata>dipendenza, è possibile scegliere quale classe di metadati utilizzare: la classe di base o una classe derivata, ad esempio . In generale, è <xref:System.Windows.FrameworkPropertyMetadata>consigliabile utilizzare , in particolare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se la proprietà ha alcuna interazione con il sistema di proprietà e funzioni quali il layout e l'associazione dati. Un'altra opzione per scenari <xref:System.Windows.FrameworkPropertyMetadata> più sofisticati consiste nel derivare da per creare la propria classe di report di metadati con informazioni aggiuntive trasportate nei relativi membri. In alternativa, <xref:System.Windows.PropertyMetadata> <xref:System.Windows.UIPropertyMetadata> è possibile utilizzare o comunicare il grado di supporto per le funzionalità dell'implementazione.  
  
 Per le<xref:System.Windows.DependencyProperty.AddOwner%2A> proprietà <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> esistenti (o chiamata), è sempre necessario eseguire l'override con il tipo di metadati utilizzato dalla registrazione originale.  
  
 Se si crea <xref:System.Windows.FrameworkPropertyMetadata> un'istanza, esistono due modi per popolare i metadati con i valori per le proprietà specifiche che comunicano le caratteristiche delle proprietà del framework:If you are creating a instance, there are two ways to populate that metadata with values for the specific properties that communicate the framework property characteristics:  
  
1. Utilizzare <xref:System.Windows.FrameworkPropertyMetadata> la firma del `flags` costruttore che consente un parametro. Questo parametro deve essere riempito <xref:System.Windows.FrameworkPropertyMetadataOptions> con tutti i valori combinati desiderati dei flag di enumerazione.  
  
2. Utilizzare una delle firme senza un `flags` parametro e <xref:System.Windows.FrameworkPropertyMetadata> `true` quindi impostare ogni proprietà booleana di report su per ogni modifica caratteristica desiderata. In questo caso, è necessario impostare queste proprietà prima della costruzione di qualsiasi elemento con questa proprietà di dipendenza. Le proprietà booleane sono configurate per la lettura e la scrittura, in modo da consentire di popolare i metadati evitando l'inserimento del parametro `flags`; tuttavia, i metadati devono essere contrassegnati come sealed prima che la proprietà venga usata. Il tentativo di impostare le proprietà dopo la richiesta dei metadati sarà pertanto considerato un'operazione non valida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>
## <a name="framework-property-metadata-merge-behavior"></a>Comportamento di unione dei metadati delle proprietà del framework  
 Quando si esegue l'override dei metadati delle proprietà del framework, le diverse caratteristiche dei metadati vengono unite o sostituite.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>viene unita. Se si aggiunge <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>un nuovo callback, tale callback viene archiviato nei metadati. Se non si <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> specifica un nella sostituzione, il valore di viene <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> promosso come riferimento dal predecessore più vicino che lo ha specificato nei metadati.  
  
- Il comportamento effettivo <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> del sistema di proprietà per è che le implementazioni per tutti i proprietari di metadati nella gerarchia vengono mantenute e aggiunte a una tabella, con l'ordine di esecuzione dal sistema di proprietà è che i callback della classe più profondamente derivata vengono richiamati per primi. I callback ereditati vengono eseguiti solo una volta, essendo considerati come appartenenti alla classe che li aveva posizionati nei metadati.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>viene sostituito. Se non si <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> specifica un nella sostituzione, il valore di <xref:System.Windows.PropertyMetadata.DefaultValue%2A> proviene dal predecessore più vicino che lo ha specificato nei metadati.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>le implementazioni vengono sostituite. Se si aggiunge <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>un nuovo callback, tale callback viene archiviato nei metadati. Se non si <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> specifica un nella sostituzione, il valore di viene <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> promosso come riferimento dal predecessore più vicino che lo ha specificato nei metadati.  
  
- Il comportamento del sistema <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> di proprietà è che viene richiamato solo il nei metadati immediati. Non vengono <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> mantenuti riferimenti ad altre implementazioni nella gerarchia.  
  
- I flag <xref:System.Windows.FrameworkPropertyMetadataOptions> di enumerazione vengono combinati come un'operazione OR bit per bit.  Se si <xref:System.Windows.FrameworkPropertyMetadataOptions>specifica , le opzioni originali non vengono sovrascritte.  Per modificare un'opzione, impostare la proprietà corrispondente su <xref:System.Windows.FrameworkPropertyMetadata>. Ad esempio, se <xref:System.Windows.FrameworkPropertyMetadata> l'oggetto originale imposta il <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> flag, è possibile modificarlo impostandolo su `false`.  
  
 Questo comportamento viene <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>implementato da e può essere sottoposto a override nelle classi di metadati derivate.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadati della proprietà di dipendenza](dependency-property-metadata.md)
- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
