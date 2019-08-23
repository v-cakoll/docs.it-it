---
title: Metadati delle proprietà del framework
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: c08cf28880d86331e3b561f1749333d401ba903e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964208"
---
# <a name="framework-property-metadata"></a>Metadati delle proprietà del framework
Per le proprietà degli elementi oggetto considerati situati a livello di framework WPF nell'architettura di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono segnalate le opzioni di metadati delle proprietà del framework. In generale, la designazione a livello di Framework WPF comporta che funzionalità quali il rendering, la data binding e i perfezionamenti del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di proprietà vengono gestiti dalle API e dagli eseguibili di presentazione. Questi sistemi eseguono una query sui metadati delle proprietà del framework per determinare le caratteristiche specifiche delle funzionalità di particolari proprietà dell'elemento.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). È inoltre necessario aver letto l'argomento [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Contenuto dei metadati delle proprietà del framework  
 I metadati delle proprietà del framework possono essere suddivisi nelle seguenti categorie:  
  
- Segnalazione delle proprietà di layout che influiscono<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>su <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>un <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>elemento (,,). È possibile impostare questi flag nei metadati se la proprietà ha effetto sui rispettivi aspetti e si implementano anche i <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi nella classe per fornire un comportamento di rendering specifico e informazioni al layout. sistema. In genere, tale implementazione verificherebbe le convalide delle proprietà nelle proprietà di dipendenza, qualora una di tali proprietà di layout risultasse impostata su true nei metadati della proprietà; solo tali convalide richiederebbero un nuovo passaggio di layout.  
  
- Segnalazione delle proprietà di layout che influiscono sull'elemento padre di<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>un <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>elemento (,). Alcuni esempi in cui questi flag sono impostati per impostazione <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> predefinita <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>sono e.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. Per impostazione predefinita, le proprietà di dipendenza non ereditano valori. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>consente anche al percorso di ereditarietà di spostarsi in una struttura ad albero visuale, operazione necessaria per alcuni scenari di composizione del controllo.  
  
    > [!NOTE]
    > Il termine "ereditarietà" nel contesto dei valori della proprietà è specifico delle proprietà di dipendenza e indica che gli elementi figlio possono ereditare il valore della proprietà di dipendenza effettivo dagli elementi padre grazie a una funzionalità a livello di framework WPF del sistema di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Non è correlato direttamente al tipo di codice gestito né all'ereditarietà dei membri tramite tipi derivati. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).  
  
- Creazione di report data binding<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>caratteristiche <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>(,). Per impostazione predefinita, le proprietà di dipendenza nel framework supportano il data binding, con un comportamento di associazione unidirezionale. È possibile disabilitare Data Binding se non è presente alcuno scenario per esso (perché sono progettati per essere flessibili ed estendibili, non sono presenti molti esempi di tali proprietà nelle API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinite). È possibile impostare l'associazione in modo che abbia un valore predefinito bidirezionale per le proprietà che combinano i comportamenti di un controllo tra<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> le parti dei componenti (è un esempio) o in cui l'associazione bidirezionale è lo scenario<xref:System.Windows.Controls.TextBox.Text%2A> comune e previsto per gli utenti (è un esempio). La modifica dei metadati correlati al data binding ha effetto sull'impostazione predefinita. È sempre possibile modificare l'impostazione predefinita per una singola associazione. Per maggiori dettagli sulle modalità di associazione e sull'associazione in generale, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).  
  
- Segnalazione se le proprietà devono essere inserite nel journal da applicazioni o servizi che supportano il<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>journaling (). Per impostazione predefinita, l'inserimento nel giornale di registrazione non è abilitato per gli elementi generali, ma è abilitato in maniera selettiva per determinati controlli di input dell'utente. Questa proprietà deve essere letta dai servizi di inserimento nel giornale di registrazione, inclusa l'implementazione dell'inserimento nel giornale di registrazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è impostata nei controlli utente, ad esempio le selezioni dell'utente all'interno di elenchi che devono essere resi persistenti nei vari passaggi di navigazione. Per informazioni sull'inserimento nel giornale di registrazione, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Lettura di FrameworkPropertyMetadata  
 Ognuna delle proprietà collegate sopra sono le proprietà specifiche che l'oggetto <xref:System.Windows.FrameworkPropertyMetadata> aggiunge alla relativa classe <xref:System.Windows.UIPropertyMetadata>di base immediata. Per impostazione predefinita, ognuna di queste proprietà sarà `false`. Una richiesta di metadati per una proprietà in cui è importante conoscere il valore di queste proprietà deve tentare di eseguire il cast <xref:System.Windows.FrameworkPropertyMetadata>dei metadati restituiti a, quindi controllare i valori delle singole proprietà in base alle esigenze.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Specifica dei metadati  
 Quando si crea una nuova istanza di metadati ai fini dell'applicazione dei metadati a una nuova registrazione della proprietà di dipendenza, è possibile scegliere la classe di metadati da utilizzare <xref:System.Windows.PropertyMetadata> : la base o una classe <xref:System.Windows.FrameworkPropertyMetadata>derivata, ad esempio. In generale, è consigliabile usare <xref:System.Windows.FrameworkPropertyMetadata>, in particolare se la proprietà ha qualsiasi interazione con il sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di proprietà e funzioni quali layout e data binding. Un'altra opzione per scenari più sofisticati consiste nel derivare da <xref:System.Windows.FrameworkPropertyMetadata> per creare una classe di report dei metadati personalizzata con informazioni aggiuntive trasportate nei relativi membri. In alternativa, è <xref:System.Windows.PropertyMetadata> possibile <xref:System.Windows.UIPropertyMetadata> usare o per comunicare il livello di supporto per le funzionalità dell'implementazione.  
  
 Per le proprietà esistenti<xref:System.Windows.DependencyProperty.AddOwner%2A> ( <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> o chiamare), è sempre necessario eseguire l'override con il tipo di metadati usato dalla registrazione originale.  
  
 Se si crea un' <xref:System.Windows.FrameworkPropertyMetadata> istanza di, esistono due modi per popolare i metadati con i valori per le proprietà specifiche che comunicano le caratteristiche della proprietà del Framework:  
  
1. Usare la <xref:System.Windows.FrameworkPropertyMetadata> firma del costruttore che consente `flags` un parametro. Questo parametro deve essere compilato con tutti i valori combinati desiderati dei flag di <xref:System.Windows.FrameworkPropertyMetadataOptions> enumerazione.  
  
2. Utilizzare una delle firme senza un `flags` parametro, quindi impostare ogni proprietà booleana Reporting `true` su su <xref:System.Windows.FrameworkPropertyMetadata> per ogni modifica caratteristica desiderata. In questo caso, è necessario impostare queste proprietà prima della costruzione di qualsiasi elemento con questa proprietà di dipendenza. Le proprietà booleane sono configurate per la lettura e la scrittura, in modo da consentire di popolare i metadati evitando l'inserimento del parametro `flags`; tuttavia, i metadati devono essere contrassegnati come sealed prima che la proprietà venga usata. Il tentativo di impostare le proprietà dopo la richiesta dei metadati sarà pertanto considerato un'operazione non valida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Comportamento di unione dei metadati delle proprietà del framework  
 Quando si esegue l'override dei metadati delle proprietà del framework, le diverse caratteristiche dei metadati vengono unite o sostituite.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>viene Unito. Se si aggiunge un nuovo <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>oggetto, tale callback viene archiviato nei metadati. Se non si specifica un oggetto <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> nell'override, il valore di <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> viene promosso come riferimento dal predecessore più vicino che lo ha specificato nei metadati.  
  
- Il comportamento effettivo del sistema di <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> proprietà per è che le implementazioni per tutti i proprietari di metadati nella gerarchia vengono mantenute e aggiunte a una tabella, con ordine di esecuzione da parte del sistema di proprietà che i callback della classe derivata più profondamente sono richiamato per primo. I callback ereditati vengono eseguiti solo una volta, essendo considerati come appartenenti alla classe che li aveva posizionati nei metadati.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>viene sostituito. Se non si specifica un oggetto <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> nell'override, il valore di <xref:System.Windows.PropertyMetadata.DefaultValue%2A> deriva dal predecessore più vicino che lo ha specificato nei metadati.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>le implementazioni vengono sostituite. Se si aggiunge un nuovo <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>oggetto, tale callback viene archiviato nei metadati. Se non si specifica un oggetto <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> nell'override, il valore di <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> viene promosso come riferimento dal predecessore più vicino che lo ha specificato nei metadati.  
  
- Il comportamento del sistema di proprietà è che <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> solo l'oggetto nei metadati immediati viene richiamato. Non viene mantenuto alcun <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> riferimento ad altre implementazioni nella gerarchia.  
  
- I flag di <xref:System.Windows.FrameworkPropertyMetadataOptions> enumerazione vengono combinati come operazione OR bit per bit.  Se si specifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, le opzioni originali non vengono sovrascritte.  Per modificare un'opzione, impostare la proprietà corrispondente in <xref:System.Windows.FrameworkPropertyMetadata>. Se, ad esempio, l' <xref:System.Windows.FrameworkPropertyMetadata> oggetto originale imposta <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> il flag, è <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> possibile modificarlo impostando `false`su.  
  
 Questo comportamento viene implementato da <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>ed è possibile eseguirne l'override nelle classi di metadati derivate.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadati delle proprietà di dipendenza](dependency-property-metadata.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
