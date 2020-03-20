---
title: Opzioni tipografiche
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 501a4221c99d405484a2fb908641d27d1f38f266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187345"
---
# <a name="typography-in-wpf"></a>Funzionalità tipografiche di WPF
Questo argomento presenta le principali funzionalità tipografiche di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste funzionalità includono una migliore qualità e prestazioni del rendering del testo, il supporto tipografico OpenType, testo internazionale migliorato, il supporto avanzato dei tipi di carattere e le nuove API (Application Application Interface) di testo.  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>
## <a name="improved-quality-and-performance-of-text"></a>Qualità e prestazioni del testo migliorate  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendering del testo in viene eseguito utilizzando Microsoft ClearType, che migliora la chiarezza e la leggibilità del testo. ClearType è una tecnologia software sviluppata da Microsoft che migliora la leggibilità del testo sui display LCD (Liquid Crystal Display) esistenti, come schermi di laptop, pocket PC e monitor a pannello piatto. ClearType utilizza il rendering dei subpixel che consente di visualizzare il testo con una maggiore fedeltà alla forma vera allineando i caratteri su una parte frazionaria di un pixel. La risoluzione aggiuntiva aumenta la nitidezza dei piccoli dettagli nella visualizzazione del testo, rendendone più facile la lettura per periodi prolungati. Un altro miglioramento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ClearType in è l'anti-aliasing della direzione y, che smussa la parte superiore e inferiore delle curve poco profonde nei caratteri di testo. Per ulteriori informazioni sulle funzionalità ClearType, vedere Cenni preliminari su [ClearType](cleartype-overview.md).  
  
 ![Testo con anti-aliasing della direzione y ClearType](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Testo con anti-aliasing della direzione y ClearType  
  
 È possibile applicare l'accelerazione hardware all'intera pipeline di rendering del testo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], purché il computer in uso soddisfi i requisiti hardware minimi richiesti. Se non è possibile eseguire il rendering tramite hardware, viene eseguito il rendering software. L'accelerazione hardware influisce su tutte le fasi della pipeline di rendering del testo, dall'archiviazione di singoli glifi, alla composizione dei glifi nelle esecuzioni dei glifi, all'applicazione degli effetti, all'applicazione dell'algoritmo di fusione ClearType all'output visualizzato finale. Per altre informazioni sull'accelerazione hardware, vedere [Livelli di rendering della grafica](graphics-rendering-tiers.md).  
  
 ![Diagramma della pipeline di rendering del testo](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Il testo animato, mediante carattere o glifo, sfrutta inoltre completamente la funzionalità hardware grafica abilitata da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], con il risultato di ottenere un'animazione del testo uniforme.  
  
<a name="Rich_Typography"></a>
## <a name="rich-typography"></a>Funzionalità tipografiche avanzate  
 Il formato del carattere OpenType è un'estensione del formato di carattere TrueType®. Il formato di carattere OpenType è stato sviluppato congiuntamente da Microsoft e Adobe e offre un ricco assortimento di funzionalità tipografiche avanzate. L'oggetto <xref:System.Windows.Documents.Typography> espone molte delle funzionalità avanzate dei tipi di carattere OpenType, ad esempio alternative stilistiche e caratteri ortici. Windows SDK fornisce un set di tipi di carattere OpenType di esempio progettati con funzionalità avanzate, ad esempio i tipi di carattere Pericles e Pescadero. Per ulteriori informazioni, consultate Esempio di pacchetto di [caratteri OpenType](sample-opentype-font-pack.md).  
  
 Il font Pericles OpenType contiene glifi aggiuntivi che forniscono alternative stilistiche al set standard di glifi. Il testo seguente mostra glifi con stile alternativo.  
  
 ![Testo con glifi con stile alternativo OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Testo con glifi con stile alternativo OpenType")  
  
 I glifi ornati sono glifi decorativi che usano ornamenti elaborati spesso associati alla calligrafia. Il testo seguente mostra glifi standard e ornati per il tipo di carattere Pescadero.  
  
 ![Testo con glifi standard e ornati OpenType](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Testo con glifi standard e ornati OpenType")  
  
 Per ulteriori informazioni sulle funzioni OpenType, consultate Funzionalità dei tipi di [carattere OpenType](opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>
## <a name="enhanced-international-text-support"></a>Supporto del testo internazionale migliorato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un migliore supporto del testo internazionale grazie alle funzionalità seguenti:  
  
- Interlinea automatica in tutti i sistemi di scrittura, tramite misurazione adattiva.  
  
- Ampio supporto per il testo internazionale. Per altre informazioni, vedere [Globalizzazione per WPF](globalization-for-wpf.md).  
  
- Interruzione di riga, sillabazione e giustificazione in base alla lingua.  
  
<a name="Enhanced_Font_Support"></a>
## <a name="enhanced-font-support"></a>Supporto dei tipi di carattere migliorato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un migliore supporto dei tipi di carattere grazie alle funzionalità seguenti:  
  
- Unicode per ogni testo. Il comportamento e la selezione del tipo di carattere non richiedono più set di caratteri o tabelle codici.  
  
- Comportamento del tipo di carattere indipendente dalle impostazioni globali, ad esempio le impostazioni locali del sistema.  
  
- <xref:System.Windows.FontWeight>Separare <xref:System.Windows.FontStretch>i <xref:System.Windows.FontStyle> tipi , <xref:System.Windows.Media.FontFamily>e per la definizione di un oggetto . Ciò offre una maggiore flessibilità rispetto alla programmazione Win32, in cui le combinazioni booleane di corsivo e grassetto vengono utilizzate per definire una famiglia di caratteri.  
  
- Direzione di scrittura (orizzontale o verticale) gestita indipendentemente dal nome del carattere.  
  
- Collegamento di tipi di carattere e fallback dei tipi di carattere in un file XML portatile, utilizzando la tecnologia dei tipi di carattere compositi. I tipi di carattere compositi consentono la costruzione di una gamma completa di tipi di carattere multilingua. Offrono inoltre un meccanismo che evita la visualizzazione di glifi mancanti. Per altre informazioni, vedere <xref:System.Windows.Media.FontFamily> le osservazioni nella classe.  
  
- Tipi di carattere internazionali compilati da tipi di carattere compositi, mediante un gruppo di tipi di carattere di una singola lingua. In questo modo, si risparmiano risorse durante lo sviluppo dei tipi di carattere per più lingue.  
  
- Tipi di carattere compositi incorporati in un documento, per offrire maggiore portabilità dei documenti. Per altre informazioni, vedere <xref:System.Windows.Media.FontFamily> le osservazioni nella classe.  
  
<a name="New_Text_APIs"></a>
## <a name="new-text-application-programming-interfaces-apis"></a>Nuove API (Application Programming Interface) di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce diverse API di testo che gli sviluppatori possono utilizzare quando includono testo nelle applicazioni. Queste API sono raggruppate in tre categorie:These APIs are grouped into three categories:  
  
- **Layout e interfaccia utente**. Controlli di testo comuni per l'interfaccia utente grafica (GUI).  
  
- **Disegno di testo leggero**. Consente di disegnare testo direttamente sugli oggetti.  
  
- **Formattazione avanzata del testo**. Consente di implementare un motore di testo personalizzato.  
  
### <a name="layout-and-user-interface"></a>Layout e interfaccia utente  
 Al più alto livello di funzionalità, le [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] API <xref:System.Windows.Controls.Label>di <xref:System.Windows.Controls.TextBlock>testo <xref:System.Windows.Controls.TextBox>forniscono controlli comuni quali , e . Questi controlli offrono gli elementi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di base all'interno di un'applicazione e un modo semplice per presentare il testo e interagire con esso. Controlli quali <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.PasswordBox> e consentono una gestione del testo più avanzata o specializzata. E classi <xref:System.Windows.Documents.TextRange>come <xref:System.Windows.Documents.TextSelection>, <xref:System.Windows.Documents.TextPointer> , e consentono un'utile manipolazione del testo. Questi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli forniscono <xref:System.Windows.Controls.Control.FontFamily%2A> <xref:System.Windows.Controls.Control.FontSize%2A>proprietà <xref:System.Windows.Controls.Control.FontStyle%2A>quali , e , che consentono di controllare il tipo di carattere utilizzato per eseguire il rendering del testo.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Uso di effetti bitmap, trasformazioni ed effetti di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di usare il testo in modi visivamente interessanti grazie a funzionalità come effetti bitmap, trasformazioni ed effetti di testo. L'esempio seguente illustra un tipico effetto di ombreggiatura applicato al testo.  
  
 ![Ombreggiatura del testo con &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg)
  
 L'esempio seguente illustra un effetto di ombreggiatura con rumore applicato al testo.  
  
 ![Ombreggiatura del testo con rumore](./media/typography-in-wpf/drop-shadow-noise-text.jpg)
  
 L'esempio seguente illustra un effetto di alone esterno applicato al testo.  
  
 ![Ombreggiatura del testo con OuterGlowBitmapEffect](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 L'esempio seguente illustra un effetto di sfocatura applicato al testo.  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 Nell'esempio seguente la seconda riga del testo è ridimensionata del 150% lungo l'asse x, mentre la terza riga del testo è ridimensionata del 150% lungo l'asse y.  
  
 ![Testo ridimensionato con ScaleTransform](./media/typography-in-wpf/scaled-text-scaletransform.jpg)
  
 Nell'esempio seguente il testo è inclinato lungo l'asse x.  
  
 ![Testo inclinato con SkewTransform](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 Un <xref:System.Windows.Media.TextEffect> oggetto è un oggetto helper che consente di trattare il testo come uno o più gruppi di caratteri in una stringa di testo. L'esempio seguente mostra la rotazione di un singolo carattere. Ogni carattere viene ruotato in modo indipendente a intervalli di 1 secondo.  
  
 ![Schermata di effetto rotazione del testo](./media/typography-in-wpf/rotating-text-effect.jpg)
  
#### <a name="using-flow-documents"></a>Uso di documenti dinamici  
 Oltre ai [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comuni, offre un controllo <xref:System.Windows.Documents.FlowDocument> di layout per la presentazione di testo, ovvero l'elemento. L'elemento, <xref:System.Windows.Documents.FlowDocument> insieme <xref:System.Windows.Controls.DocumentViewer> all'elemento, fornisce un controllo per grandi quantità di testo con requisiti di layout diversi. I controlli di layout forniscono <xref:System.Windows.Documents.Typography> l'accesso alla tipografia [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] avanzata tramite le proprietà relative all'oggetto e al tipo di carattere di altri controlli.  
  
 Nell'esempio seguente viene illustrato <xref:System.Windows.Controls.FlowDocumentReader>il contenuto di testo ospitato in un oggetto , che fornisce il supporto per la ricerca, la navigazione, l'impaginazione e il ridimensionamento del contenuto.  
  
 ![Screenshot che mostra i font OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Per altre informazioni, vedere [Documenti in WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Disegno di testo leggero  
 È possibile disegnare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il testo <xref:System.Windows.Media.DrawingContext.DrawText%2A> direttamente sugli <xref:System.Windows.Media.DrawingContext> oggetti utilizzando il metodo dell'oggetto. Per utilizzare questo metodo, <xref:System.Windows.Media.FormattedText> creare un oggetto. Questo oggetto consente di creare testo su più righe, in cui ogni carattere può essere formattato singolarmente. La funzionalità <xref:System.Windows.Media.FormattedText> dell'oggetto contiene gran parte della funzionalità dei flag DrawText nell'API di Windows. Inoltre, l'oggetto contiene funzionalità quali il supporto dei puntini di sospensione, in cui vengono visualizzati i puntini di sospensione quando il <xref:System.Windows.Media.FormattedText> testo supera i limiti. L'esempio seguente illustra un testo a cui sono stati applicati diversi formati, inclusa una sfumatura lineare sulla seconda e la terza parola.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)
  
 È possibile convertire il <xref:System.Windows.Media.Geometry> testo formattato in oggetti, consentendo di creare altri tipi di testo visivamente interessante. Ad esempio, è <xref:System.Windows.Media.Geometry> possibile creare un oggetto in base al contorno di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Testo con pennello immagine applicato al tratto e all'evidenziazione](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Per ulteriori informazioni <xref:System.Windows.Media.FormattedText> sull'oggetto, vedere [Disegno di testo formattato](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Al livello più avanzato delle API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di testo, ti offre la <xref:System.Windows.Media.TextFormatting.TextFormatter> possibilità di creare <xref:System.Windows.Media.TextFormatting> un layout di testo personalizzato usando l'oggetto e altri tipi nello spazio dei nomi. Le <xref:System.Windows.Media.TextFormatting.TextFormatter> classi e associate consentono di implementare un layout di testo personalizzato che supporta la definizione personalizzata di formati di carattere, stili di paragrafo, regole di interruzione di riga e altre funzionalità di layout per il testo internazionale. Sono pochi i casi in cui occorre eseguire l'override dell'implementazione predefinita del supporto di layout di testo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se tuttavia occorre creare un controllo o un'applicazione di modifica del testo, potrebbe essere necessaria un'implementazione diversa da quella predefinita di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 A differenza di un'API di testo tradizionale, l'interagiva <xref:System.Windows.Media.TextFormatting.TextFormatter> con un client di layout di testo tramite un set di metodi di callback. Richiede al client di fornire questi metodi <xref:System.Windows.Media.TextFormatting.TextSource> in un'implementazione della classe. Nel diagramma seguente viene illustrata l'interazione del layout di testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramma del client del layout di testo e TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Per informazioni dettagliate sulla creazione di layout di testo personalizzati, vedere [Formattazione del testo avanzata](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Panoramica su ClearType](cleartype-overview.md)
- [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md)
- [Disegno di testo formattato](drawing-formatted-text.md)
- [Formattazione del testo avanzata](advanced-text-formatting.md)
- [Testo](optimizing-performance-text.md)
- [Microsoft Typography](https://docs.microsoft.com/typography/)
