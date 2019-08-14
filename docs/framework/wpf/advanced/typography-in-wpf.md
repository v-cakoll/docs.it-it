---
title: Funzionalità tipografiche di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 5f3560c899373b9835e2ead79590cf73777b2375
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972415"
---
# <a name="typography-in-wpf"></a>Funzionalità tipografiche di WPF
Questo argomento presenta le principali funzionalità tipografiche di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste includono qualità e prestazioni migliorate nel rendering del testo, supporto tipografico di [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], testo internazionale migliorato, supporto avanzato dei tipi di carattere e nuove API (Application Programming Interface) di testo.  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Qualità e prestazioni del testo migliorate  
 Il rendering [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del testo in viene eseguito utilizzando Microsoft ClearType, che migliora la chiarezza e la leggibilità del testo. ClearType è una tecnologia software sviluppata da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] che consente di migliorare la leggibilità del testo sugli schermi LCD (Liquid Crystal Display), ad esempio schermi portatili, schermi Pocket PC e monitor Flat Panel. ClearType utilizza il rendering dei subpixel, che consente di visualizzare il testo con una maggiore fedeltà alla propria forma reale allineando i caratteri in una parte frazionaria di un pixel. La risoluzione aggiuntiva aumenta la nitidezza dei piccoli dettagli nella visualizzazione del testo, rendendone più facile la lettura per periodi prolungati. Un altro miglioramento di ClearType [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in è l'anti-aliasing della direzione y, che smussa le parti superiori e inferiori delle curve superficiali nei caratteri di testo. Per ulteriori informazioni sulle funzionalità ClearType, vedere [Cenni preliminari su ClearType](cleartype-overview.md).  
  
 ![Testo con anti-aliasing della direzione y ClearType](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Testo con anti-aliasing della direzione y ClearType  
  
 È possibile applicare l'accelerazione hardware all'intera pipeline di rendering del testo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], purché il computer in uso soddisfi i requisiti hardware minimi richiesti. Se non è possibile eseguire il rendering tramite hardware, viene eseguito il rendering software. L'accelerazione hardware influisce su tutte le fasi della pipeline di rendering del testo, dall'archiviazione di singoli glifi, alla composizione di glifi in esecuzioni di glifi, all'applicazione di effetti all'applicazione dell'algoritmo di fusione ClearType all'output visualizzato finale. Per altre informazioni sull'accelerazione hardware, vedere [Livelli di rendering della grafica](graphics-rendering-tiers.md).  
  
 ![Diagramma della pipeline di rendering del testo](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Il testo animato, mediante carattere o glifo, sfrutta inoltre completamente la funzionalità hardware grafica abilitata da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], con il risultato di ottenere un'animazione del testo uniforme.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Funzionalità tipografiche avanzate  
 Il formato del tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] è un'estensione del formato [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]. Il formato del tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] è stato sviluppato congiuntamente da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] e Adobe e offre un vasto assortimento di funzionalità tipografiche avanzate. L' <xref:System.Windows.Documents.Typography> oggetto espone molte delle funzionalità avanzate dei tipi [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] di carattere, ad esempio alternative stilistiche e ornati. Il Windows SDK fornisce un set di tipi [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] di carattere di esempio progettati con funzionalità avanzate, ad esempio i tipi di carattere Pericle e Pescadero. Per altre informazioni, vedere [Esempio di pacchetto di tipi di carattere OpenType](sample-opentype-font-pack.md).  
  
 Il tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles contiene glifi aggiuntivi che offrono alternative stilistiche al set di glifi standard. Il testo seguente mostra glifi con stile alternativo.  
  
 ![Testo con glifi alternativi stilistici OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Testo con glifi alternativi stilistici OpenType")  
  
 I glifi ornati sono glifi decorativi che usano ornamenti elaborati spesso associati alla calligrafia. Il testo seguente mostra glifi standard e ornati per il tipo di carattere Pescadero.  
  
 ![Testo con glifi standard e ornati OpenType](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Testo con glifi standard e ornati OpenType")  
  
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
  
- Separare <xref:System.Windows.FontWeight>i <xref:System.Windows.FontStretch>tipi, <xref:System.Windows.FontStyle> e per la definizione <xref:System.Windows.Media.FontFamily>di un oggetto. Offre maggiore flessibilità rispetto alla programmazione [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], in cui si usano combinazioni booleane di corsivo e grassetto per definire una famiglia di caratteri.  
  
- Direzione di scrittura (orizzontale o verticale) gestita indipendentemente dal nome del carattere.  
  
- Collegamento e fallback dei tipi di carattere in un file [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] portabile, con tecnologia dei tipi di carattere compositi. I tipi di carattere compositi consentono la costruzione di una gamma completa di tipi di carattere multilingua. Offrono inoltre un meccanismo che evita la visualizzazione di glifi mancanti. Per ulteriori informazioni, vedere la sezione Osservazioni nella <xref:System.Windows.Media.FontFamily> classe.  
  
- Tipi di carattere internazionali compilati da tipi di carattere compositi, mediante un gruppo di tipi di carattere di una singola lingua. In questo modo, si risparmiano risorse durante lo sviluppo dei tipi di carattere per più lingue.  
  
- Tipi di carattere compositi incorporati in un documento, per offrire maggiore portabilità dei documenti. Per ulteriori informazioni, vedere la sezione Osservazioni nella <xref:System.Windows.Media.FontFamily> classe.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Nuove API (Application Programming Interface) di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in sono disponibili diverse API di testo che gli sviluppatori possono utilizzare per includere testo nelle applicazioni. Queste API sono raggruppate in tre categorie:  
  
- **Layout e interfaccia utente**. Controlli di testo comuni per l'interfaccia utente grafica (GUI).  
  
- **Disegno di testo leggero**. Consente di disegnare testo direttamente sugli oggetti.  
  
- **Formattazione del testo avanzata**. Consente di implementare un motore di testo personalizzato.  
  
### <a name="layout-and-user-interface"></a>Layout e interfaccia utente  
 Al livello più elevato di funzionalità, le API di testo forniscono [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] controlli comuni, <xref:System.Windows.Controls.Label>ad <xref:System.Windows.Controls.TextBlock>esempio, <xref:System.Windows.Controls.TextBox>e. Questi controlli offrono gli elementi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di base all'interno di un'applicazione e un modo semplice per presentare il testo e interagire con esso. I controlli come <xref:System.Windows.Controls.RichTextBox> e <xref:System.Windows.Controls.PasswordBox> consentono una gestione del testo più avanzata o specializzata. Le classi e, <xref:System.Windows.Documents.TextRange>ad <xref:System.Windows.Documents.TextSelection>esempio, <xref:System.Windows.Documents.TextPointer> e consentono una manipolazione del testo utile. Questi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli forniscono proprietà <xref:System.Windows.Controls.Control.FontFamily%2A>quali, <xref:System.Windows.Controls.Control.FontSize%2A>e <xref:System.Windows.Controls.Control.FontStyle%2A>, che consentono di controllare il tipo di carattere utilizzato per il rendering del testo.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Uso di effetti bitmap, trasformazioni ed effetti di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di usare il testo in modi visivamente interessanti grazie a funzionalità come effetti bitmap, trasformazioni ed effetti di testo. L'esempio seguente illustra un tipico effetto di ombreggiatura applicato al testo.  
  
 ![Ombreggiatura del testo con &#61; morbidezza 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
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
 Oltre ai controlli comuni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un controllo di layout per la presentazione del testo, <xref:System.Windows.Documents.FlowDocument> ovvero l'elemento. L' <xref:System.Windows.Documents.FlowDocument> elemento, insieme <xref:System.Windows.Controls.DocumentViewer> all'elemento, fornisce un controllo per grandi quantità di testo con requisiti di layout diversi. I controlli di layout consentono di accedere a tipografia avanzata tramite l'oggetto e le <xref:System.Windows.Documents.Typography> proprietà correlate al tipo di carattere di altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli.  
  
 Nell'esempio seguente viene illustrato il contenuto di testo <xref:System.Windows.Controls.FlowDocumentReader>ospitato in un oggetto, che fornisce supporto per la ricerca, la navigazione, l'impaginazione e il ridimensionamento del contenuto.  
  
 ![Screenshot che mostra i tipi di carattere OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Per altre informazioni, vedere [Documenti in WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Disegno di testo leggero  
 È possibile creare il testo direttamente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] negli oggetti usando il <xref:System.Windows.Media.DrawingContext.DrawText%2A> metodo dell' <xref:System.Windows.Media.DrawingContext> oggetto. Per usare questo metodo, è necessario creare <xref:System.Windows.Media.FormattedText> un oggetto. Questo oggetto consente di creare testo su più righe, in cui ogni carattere può essere formattato singolarmente. La funzionalità dell' <xref:System.Windows.Media.FormattedText> oggetto contiene la maggior parte delle funzionalità dei flag DrawText nell'API Windows. Inoltre, l'oggetto <xref:System.Windows.Media.FormattedText> contiene funzionalità come il supporto dei puntini di sospensione, in cui vengono visualizzati i puntini di sospensione quando il testo supera i limiti. L'esempio seguente illustra un testo a cui sono stati applicati diversi formati, inclusa una sfumatura lineare sulla seconda e la terza parola.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 È possibile convertire il testo formattato in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo visivamente interessante. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Testo con pennello immagine applicato al tratto ed evidenziato](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Per ulteriori informazioni sull' <xref:System.Windows.Media.FormattedText> oggetto, vedere disegno di [testo formattato](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Al livello più avanzato delle API di testo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre la possibilità di creare un layout di testo personalizzato usando l' <xref:System.Windows.Media.TextFormatting.TextFormatter> oggetto <xref:System.Windows.Media.TextFormatting> e altri tipi nello spazio dei nomi. Le <xref:System.Windows.Media.TextFormatting.TextFormatter> classi e associate consentono di implementare un layout di testo personalizzato che supporta la definizione di formati di carattere, stili di paragrafo, regole di interruzioni di riga e altre funzionalità di layout per il testo internazionale. Sono pochi i casi in cui occorre eseguire l'override dell'implementazione predefinita del supporto di layout di testo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se tuttavia occorre creare un controllo o un'applicazione di modifica del testo, potrebbe essere necessaria un'implementazione diversa da quella predefinita di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Diversamente da un'API di testo tradizionale, <xref:System.Windows.Media.TextFormatting.TextFormatter> il interagisce con un client di layout di testo tramite un set di metodi di callback. Richiede che il client fornisca questi metodi in un'implementazione della <xref:System.Windows.Media.TextFormatting.TextSource> classe. Nel diagramma seguente viene illustrata l'interazione del layout del testo tra l' <xref:System.Windows.Media.TextFormatting.TextFormatter>applicazione client e.  
  
 ![Diagramma del client del layout di testo e TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Per informazioni dettagliate sulla creazione di layout di testo personalizzati, vedere [Formattazione del testo avanzata](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Panoramica su ClearType](cleartype-overview.md)
- [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md)
- [Disegno di testo formattato](drawing-formatted-text.md)
- [Formattazione del testo avanzata](advanced-text-formatting.md)
- [Text](optimizing-performance-text.md)
- [Microsoft Typography](https://docs.microsoft.com/typography/)
