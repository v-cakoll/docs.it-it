---
title: Funzionalità tipografiche di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 0fba0b8814597f58018c4c5feba85082ef035e1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031317"
---
# <a name="typography-in-wpf"></a>Funzionalità tipografiche di WPF
Questo argomento presenta le principali funzionalità tipografiche di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste includono qualità e prestazioni migliorate nel rendering del testo, supporto tipografico di [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], testo internazionale migliorato, supporto avanzato dei tipi di carattere e nuove API (Application Programming Interface) di testo.  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Qualità e prestazioni del testo migliorate  
 Il rendering del testo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene eseguito usando [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], che ne migliora la chiarezza e la leggibilità. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] è una tecnologia software sviluppata da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] che consente di migliorare la leggibilità del testo sui display LCD (Liquid Crystal Display), ad esempio gli schermi di computer portatili, Pocket PC e i monitor a schermo piatto. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] usa il rendering dei subpixel, che consente di visualizzare il testo con maggiore fedeltà alla forma effettiva grazie all'allineamento dei caratteri a una parte frazionaria di un pixel. La risoluzione aggiuntiva aumenta la nitidezza dei piccoli dettagli nella visualizzazione del testo, rendendone più facile la lettura per periodi prolungati. Un altro miglioramento di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è l'anti-aliasing con direzione y che smussa le parti superiori e inferiori delle curve poco pronunciate nei caratteri di testo. Per informazioni dettagliate sulle funzionalità di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], vedere [Cenni preliminari su ClearType](cleartype-overview.md).  
  
 ![Testo con anti-aliasing della direzione y ClearType](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Testo con anti-aliasing della direzione y ClearType  
  
 È possibile applicare l'accelerazione hardware all'intera pipeline di rendering del testo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], purché il computer in uso soddisfi i requisiti hardware minimi richiesti. Se non è possibile eseguire il rendering tramite hardware, viene eseguito il rendering software. L'accelerazione hardware influisce su tutte le fasi della pipeline di rendering del testo, dall'archiviazione di singoli glifi, alla composizione di glifi in sequenze, all'applicazione di effetti, all'applicazione dell'algoritmo di fusione di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] all'output finale visualizzato. Per altre informazioni sull'accelerazione hardware, vedere [Livelli di rendering della grafica](graphics-rendering-tiers.md).  
  
 ![Diagramma della pipeline di rendering del testo](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Il testo animato, mediante carattere o glifo, sfrutta inoltre completamente la funzionalità hardware grafica abilitata da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], con il risultato di ottenere un'animazione del testo uniforme.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Funzionalità tipografiche avanzate  
 Il formato del tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] è un'estensione del formato [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]. Il formato del tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] è stato sviluppato congiuntamente da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] e Adobe e offre un vasto assortimento di funzionalità tipografiche avanzate. Il <xref:System.Windows.Documents.Typography> oggetto espone molte delle funzionalità avanzate di [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] tipi di carattere, ad esempio alternative stilistiche e glifi ornati. [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] contiene un set di tipi di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] di esempio con funzionalità avanzate, ad esempio i tipi di carattere Pericles e Pescadero. Per altre informazioni, vedere [Esempio di pacchetto di tipi di carattere OpenType](sample-opentype-font-pack.md).  
  
 Il tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles contiene glifi aggiuntivi che offrono alternative stilistiche al set di glifi standard. Il testo seguente mostra glifi con stile alternativo.  
  
 ![Testo con glifi con stile alternativo OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "testo con glifi con stile alternativo OpenType")  
  
 I glifi ornati sono glifi decorativi che usano ornamenti elaborati spesso associati alla calligrafia. Il testo seguente mostra glifi standard e ornati per il tipo di carattere Pescadero.  
  
 ![Testo con glifi standard e ornati OpenType](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "testo con glifi standard e ornati OpenType")  
  
 Per informazioni dettagliate sulle funzionalità di [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], vedere [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md).  
  
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
  
- Separata <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, e <xref:System.Windows.FontStyle> tipi per la definizione di un <xref:System.Windows.Media.FontFamily>. Offre maggiore flessibilità rispetto alla programmazione [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], in cui si usano combinazioni booleane di corsivo e grassetto per definire una famiglia di caratteri.  
  
- Direzione di scrittura (orizzontale o verticale) gestita indipendentemente dal nome del carattere.  
  
- Collegamento e fallback dei tipi di carattere in un file [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] portabile, con tecnologia dei tipi di carattere compositi. I tipi di carattere compositi consentono la costruzione di una gamma completa di tipi di carattere multilingua. Offrono inoltre un meccanismo che evita la visualizzazione di glifi mancanti. Per altre informazioni, vedere la sezione Note nel <xref:System.Windows.Media.FontFamily> classe.  
  
- Tipi di carattere internazionali compilati da tipi di carattere compositi, mediante un gruppo di tipi di carattere di una singola lingua. In questo modo, si risparmiano risorse durante lo sviluppo dei tipi di carattere per più lingue.  
  
- Tipi di carattere compositi incorporati in un documento, per offrire maggiore portabilità dei documenti. Per altre informazioni, vedere la sezione Note nel <xref:System.Windows.Media.FontFamily> classe.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Nuove API (Application Programming Interface) di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre varie [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] di testo che gli sviluppatori possono usare per l'inserimento di testo nelle applicazioni. Le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] sono raggruppate in tre categorie:  
  
- **Layout e interfaccia utente**. Controlli di testo comuni per [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
- **Disegno di testo leggero**. Consente di disegnare testo direttamente sugli oggetti.  
  
- **Formattazione del testo avanzata**. Consente di implementare un motore di testo personalizzato.  
  
### <a name="layout-and-user-interface"></a>Layout e interfaccia utente  
 Livello più alto di funzionalità, il testo [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] offrono più comuni [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] controlli, ad esempio <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>. Questi controlli offrono gli elementi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di base all'interno di un'applicazione e un modo semplice per presentare il testo e interagire con esso. I controlli quali <xref:System.Windows.Controls.RichTextBox> e <xref:System.Windows.Controls.PasswordBox> Abilita più avanzata o specializzata di gestione del testo. E le classi quali <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, e <xref:System.Windows.Documents.TextPointer> abilitare utile manipolazione del testo. Questi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli forniscono proprietà quali <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, e <xref:System.Windows.Controls.Control.FontStyle%2A>, che consentono di controllare il tipo di carattere utilizzato per il rendering del testo.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Uso di effetti bitmap, trasformazioni ed effetti di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di usare il testo in modi visivamente interessanti grazie a funzionalità come effetti bitmap, trasformazioni ed effetti di testo. L'esempio seguente illustra un tipico effetto di ombreggiatura applicato al testo.  
  
 ![Ombreggiatura del testo con Softness &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
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
  
 Oggetto <xref:System.Windows.Media.TextEffect> è un oggetto di supporto che consente di trattare il testo come uno o più gruppi di caratteri nella stringa di testo. L'esempio seguente mostra la rotazione di un singolo carattere. Ogni carattere viene ruotato in modo indipendente a intervalli di 1 secondo.  
  
 ![Schermata di effetto rotazione del testo](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>Uso di documenti dinamici  
 Oltre alla comune [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (controlli), [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un controllo di layout per la presentazione del testo, ovvero il <xref:System.Windows.Documents.FlowDocument> elemento. Il <xref:System.Windows.Documents.FlowDocument> elemento, in combinazione con la <xref:System.Windows.Controls.DocumentViewer> elemento, fornisce un controllo per grandi quantità di testo con requisiti di layout variabili. Controlli layout offrono accesso alla tipografia avanzata tramite il <xref:System.Windows.Documents.Typography> oggetto e le proprietà relative ai caratteri degli altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli.  
  
 L'esempio seguente mostra il testo contenuto ospitato in un <xref:System.Windows.Controls.FlowDocumentReader>, assicurando una ricerca, navigazione, paginazione e ridimensionamento il supporto del contenuto.  
  
 ![Screenshot che mostra i tipi di carattere OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Per altre informazioni, vedere [Documenti in WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Disegno di testo leggero  
 È possibile disegnare testo direttamente al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli oggetti utilizzando il <xref:System.Windows.Media.DrawingContext.DrawText%2A> metodo del <xref:System.Windows.Media.DrawingContext> oggetto. Per usare questo metodo, si crea un <xref:System.Windows.Media.FormattedText> oggetto. Questo oggetto consente di creare testo su più righe, in cui ogni carattere può essere formattato singolarmente. La funzionalità del <xref:System.Windows.Media.FormattedText> oggetto contiene la maggior parte delle funzionalità dei flag DrawText nell'API di Windows. Inoltre, il <xref:System.Windows.Media.FormattedText> oggetto contiene funzionalità quali il supporto di puntini di sospensione, in cui i puntini di sospensione viene visualizzata quando il testo supera i limiti. L'esempio seguente illustra un testo a cui sono stati applicati diversi formati, inclusa una sfumatura lineare sulla seconda e la terza parola.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 È possibile convertire il testo formattato in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo dall'aspetto accattivante. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Testo con pennello immagine applicato per tracciare ed evidenziare](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Per altre informazioni sul <xref:System.Windows.Media.FormattedText> oggetti, vedere [disegno di testo formattato](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Al massimo livello avanzato del testo [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre la possibilità di creare layout di testo personalizzato usando la <xref:System.Windows.Media.TextFormatting.TextFormatter> oggetto e altri tipi all'interno di <xref:System.Windows.Media.TextFormatting> dello spazio dei nomi. Il <xref:System.Windows.Media.TextFormatting.TextFormatter> e classi associate consentono di implementare il layout di testo personalizzato che supporta la definizione di formati di carattere, stili di paragrafo, regole di interruzione di riga e altre funzionalità di layout per il testo internazionale. Sono pochi i casi in cui occorre eseguire l'override dell'implementazione predefinita del supporto di layout di testo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se tuttavia occorre creare un controllo o un'applicazione di modifica del testo, potrebbe essere necessaria un'implementazione diversa da quella predefinita di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 A differenza di un testo tradizionali [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], il <xref:System.Windows.Media.TextFormatting.TextFormatter> interagisce con un client di layout di testo tramite un set di metodi di callback. È necessario che il client fornisca questi metodi in un'implementazione del <xref:System.Windows.Media.TextFormatting.TextSource> classe. Il diagramma seguente illustra l'interazione di layout di testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramma del client del layout di testo e TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Per informazioni dettagliate sulla creazione di layout di testo personalizzati, vedere [Formattazione del testo avanzata](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Panoramica su ClearType](cleartype-overview.md)
- [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md)
- [Disegno di testo formattato](drawing-formatted-text.md)
- [Formattazione del testo avanzata](advanced-text-formatting.md)
- [per](optimizing-performance-text.md)
- [Microsoft Typography](https://docs.microsoft.com/typography/)
