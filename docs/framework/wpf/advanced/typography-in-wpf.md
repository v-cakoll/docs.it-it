---
title: Funzionalità tipografiche di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 45f74a4dd2164f332314ad79a18eab49efb520d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549127"
---
# <a name="typography-in-wpf"></a>Funzionalità tipografiche di WPF
Questo argomento presenta le principali funzionalità tipografiche di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste includono qualità e prestazioni migliorate nel rendering del testo, supporto tipografico di [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], testo internazionale migliorato, supporto avanzato dei tipi di carattere e nuove API (Application Programming Interface) di testo.  
  

  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Qualità e prestazioni del testo migliorate  
 Il rendering del testo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene eseguito usando [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], che ne migliora la chiarezza e la leggibilità. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] è una tecnologia software sviluppata da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] che consente di migliorare la leggibilità del testo sui display LCD (Liquid Crystal Display), ad esempio gli schermi di computer portatili, Pocket PC e i monitor a schermo piatto. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] usa il rendering dei subpixel, che consente di visualizzare il testo con maggiore fedeltà alla forma effettiva grazie all'allineamento dei caratteri a una parte frazionaria di un pixel. La risoluzione aggiuntiva aumenta la nitidezza dei piccoli dettagli nella visualizzazione del testo, rendendone più facile la lettura per periodi prolungati. Un altro miglioramento di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è l'anti-aliasing con direzione y che smussa le parti superiori e inferiori delle curve poco pronunciate nei caratteri di testo. Per informazioni dettagliate sulle funzionalità di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], vedere [Cenni preliminari su ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 ![Testo con y ClearType&#45;direzione anti&#45;aliasing](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.gif "TypographyInWPF02")  
Testo con anti-aliasing della direzione y ClearType  
  
 È possibile applicare l'accelerazione hardware all'intera pipeline di rendering del testo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], purché il computer in uso soddisfi i requisiti hardware minimi richiesti. Se non è possibile eseguire il rendering tramite hardware, viene eseguito il rendering software. L'accelerazione hardware influisce su tutte le fasi della pipeline di rendering del testo, dall'archiviazione di singoli glifi, alla composizione di glifi in sequenze, all'applicazione di effetti, all'applicazione dell'algoritmo di fusione di [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] all'output finale visualizzato. Per altre informazioni sull'accelerazione hardware, vedere [Livelli di rendering della grafica](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 ![Diagramma della pipeline di rendering di testo](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
Diagramma della pipeline di rendering del testo  
  
 Il testo animato, mediante carattere o glifo, sfrutta inoltre completamente la funzionalità hardware grafica abilitata da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], con il risultato di ottenere un'animazione del testo uniforme.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Funzionalità tipografiche avanzate  
 Il formato del tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] è un'estensione del formato [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]. Il formato del tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] è stato sviluppato congiuntamente da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] e Adobe e offre un vasto assortimento di funzionalità tipografiche avanzate. Il <xref:System.Windows.Documents.Typography> oggetto espone molte delle funzionalità avanzate di [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] tipi di carattere, ad esempio alternative stilistiche e ornati. [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] contiene un set di tipi di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] di esempio con funzionalità avanzate, ad esempio i tipi di carattere Pericles e Pescadero. Per altre informazioni, vedere [Esempio di pacchetto di tipi di carattere OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Il tipo di carattere [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles contiene glifi aggiuntivi che offrono alternative stilistiche al set di glifi standard. Il testo seguente mostra glifi con stile alternativo.  
  
 ![Testo con glifi di stile alternativo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
Testo con glifi con stile alternativo OpenType  
  
 I glifi ornati sono glifi decorativi che usano ornamenti elaborati spesso associati alla calligrafia. Il testo seguente mostra glifi standard e ornati per il tipo di carattere Pescadero.  
  
 ![Testo con glifi standard e ornati OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
Testo con glifi standard e ornati OpenType  
  
 Per informazioni dettagliate sulle funzionalità di [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], vedere [Funzionalità dei tipi di carattere OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>Supporto del testo internazionale migliorato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un migliore supporto del testo internazionale grazie alle funzionalità seguenti:  
  
-   Interlinea automatica in tutti i sistemi di scrittura, tramite misurazione adattiva.  
  
-   Ampio supporto per il testo internazionale. Per altre informazioni, vedere [Globalizzazione per WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   Interruzione di riga, sillabazione e giustificazione in base alla lingua.  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>Supporto dei tipi di carattere migliorato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un migliore supporto dei tipi di carattere grazie alle funzionalità seguenti:  
  
-   Unicode per ogni testo. Il comportamento e la selezione del tipo di carattere non richiedono più set di caratteri o tabelle codici.  
  
-   Comportamento del tipo di carattere indipendente dalle impostazioni globali, ad esempio le impostazioni locali del sistema.  
  
-   Separata <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, e <xref:System.Windows.FontStyle> tipi per la definizione di un <xref:System.Windows.Media.FontFamily>. Offre maggiore flessibilità rispetto alla programmazione [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], in cui si usano combinazioni booleane di corsivo e grassetto per definire una famiglia di caratteri.  
  
-   Direzione di scrittura (orizzontale o verticale) gestita indipendentemente dal nome del carattere.  
  
-   Collegamento e fallback dei tipi di carattere in un file [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] portabile, con tecnologia dei tipi di carattere compositi. I tipi di carattere compositi consentono la costruzione di una gamma completa di tipi di carattere multilingua. Offrono inoltre un meccanismo che evita la visualizzazione di glifi mancanti. Per ulteriori informazioni, vedere la sezione osservazioni nel <xref:System.Windows.Media.FontFamily> classe.  
  
-   Tipi di carattere internazionali compilati da tipi di carattere compositi, mediante un gruppo di tipi di carattere di una singola lingua. In questo modo, si risparmiano risorse durante lo sviluppo dei tipi di carattere per più lingue.  
  
-   Tipi di carattere compositi incorporati in un documento, per offrire maggiore portabilità dei documenti. Per ulteriori informazioni, vedere la sezione osservazioni nel <xref:System.Windows.Media.FontFamily> classe.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Nuove API (Application Programming Interface) di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre varie [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] di testo che gli sviluppatori possono usare per l'inserimento di testo nelle applicazioni. Le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] sono raggruppate in tre categorie:  
  
-   **Layout e interfaccia utente**. Controlli di testo comuni per [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
-   **Disegno di testo leggero**. Consente di disegnare testo direttamente sugli oggetti.  
  
-   **Formattazione del testo avanzata**. Consente di implementare un motore di testo personalizzato.  
  
### <a name="layout-and-user-interface"></a>Layout e interfaccia utente  
 Il massimo livello di funzionalità, il testo [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] forniscono comuni [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] controlli, ad esempio <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>. Questi controlli offrono gli elementi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di base all'interno di un'applicazione e un modo semplice per presentare il testo e interagire con esso. I controlli come <xref:System.Windows.Controls.RichTextBox> e <xref:System.Windows.Controls.PasswordBox> abilitare più avanzata o specializzata di gestione del testo. Classi quali <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, e <xref:System.Windows.Documents.TextPointer> consentono la modifica del testo utile. Questi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli forniscono proprietà, ad esempio <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, e <xref:System.Windows.Controls.Control.FontStyle%2A>, che consentono di controllare il tipo di carattere utilizzato per il rendering del testo.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Uso di effetti bitmap, trasformazioni ed effetti di testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di usare il testo in modi visivamente interessanti grazie a funzionalità come effetti bitmap, trasformazioni ed effetti di testo. L'esempio seguente illustra un tipico effetto di ombreggiatura applicato al testo.  
  
 ![Ombreggiatura del testo con Softness &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Testo con ombreggiatura  
  
 L'esempio seguente illustra un effetto di ombreggiatura con rumore applicato al testo.  
  
 ![Ombreggiatura del testo con rumore](../../../../docs/framework/wpf/advanced/media/shadowtext04.jpg "ShadowText04")  
Testo con ombreggiatura e rumore  
  
 L'esempio seguente illustra un effetto di alone esterno applicato al testo.  
  
 ![Ombreggiatura del testo con OuterGlowBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext05.jpg "ShadowText05")  
Testo con effetto di alone esterno  
  
 L'esempio seguente illustra un effetto di sfocatura applicato al testo.  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Testo con effetto di sfocatura  
  
 Nell'esempio seguente la seconda riga del testo è ridimensionata del 150% lungo l'asse x, mentre la terza riga del testo è ridimensionata del 150% lungo l'asse y.  
  
 ![Testo ridimensionato con ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
Testo con ScaleTransform  
  
 Nell'esempio seguente il testo è inclinato lungo l'asse x.  
  
 ![Testo inclinato con SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
Testo con SkewTransform  
  
 Oggetto <xref:System.Windows.Media.TextEffect> è un oggetto di supporto che consente di trattare il testo come uno o più gruppi di caratteri nella stringa di testo. L'esempio seguente mostra la rotazione di un singolo carattere. Ogni carattere viene ruotato in modo indipendente a intervalli di 1 secondo.  
  
 ![Schermata di testo con effetto rotazione](../../../../docs/framework/wpf/advanced/media/texteffect01.jpg "TextEffect01")  
Esempio di animazione con effetto di rotazione del testo  
  
#### <a name="using-flow-documents"></a>Uso di documenti dinamici  
 Oltre alle comuni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un controllo di layout per la presentazione del testo, ovvero il <xref:System.Windows.Documents.FlowDocument> elemento. Il <xref:System.Windows.Documents.FlowDocument> elemento, in combinazione con il <xref:System.Windows.Controls.DocumentViewer> elemento, fornisce un controllo per grandi quantità di testo con diversi requisiti di layout. Controlli di layout offrono l'accesso alla tipografia avanzata tramite il <xref:System.Windows.Documents.Typography> oggetto e le proprietà relative ai caratteri di altre [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli.  
  
 Nell'esempio seguente viene mostrato il testo contenuto ospitato in un <xref:System.Windows.Controls.FlowDocumentReader>, assicurando una ricerca, la navigazione, la paginazione e il contenuto di supporto del ridimensionamento.  
  
 ![Che utilizza i tipi di carattere schermata di esempio](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF_03")  
Testo ospitato in un oggetto FlowDocumentReader  
  
 Per altre informazioni, vedere [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Disegno di testo leggero  
 È possibile creare direttamente al testo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti usando il <xref:System.Windows.Media.DrawingContext.DrawText%2A> metodo il <xref:System.Windows.Media.DrawingContext> oggetto. Per utilizzare questo metodo, si crea un <xref:System.Windows.Media.FormattedText> oggetto. Questo oggetto consente di creare testo su più righe, in cui ogni carattere può essere formattato singolarmente. La funzionalità del <xref:System.Windows.Media.FormattedText> oggetto contiene la maggior parte delle funzionalità dei flag DrawText nell'API Win32. Inoltre, il <xref:System.Windows.Media.FormattedText> oggetto contiene funzionalità quali il supporto di puntini di sospensione, in cui i puntini di sospensione viene visualizzata quando il testo supera i limiti. L'esempio seguente illustra un testo a cui sono stati applicati diversi formati, inclusa una sfumatura lineare sulla seconda e la terza parola.  
  
 ![Testo visualizzato usando l'oggetto FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext01.jpg "FormattedText01")  
Testo visualizzato usando l'oggetto FormattedText  
  
 È possibile convertire il testo formattato in <xref:System.Windows.Media.Geometry> oggetti, che consente di creare altri tipi di testo visivamente interessante. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Struttura di testo con pennello sfumato lineare  
  
 Gli esempi seguenti illustrano diverse modalità di creazione di effetti visivi interessanti tramite la modifica del tratto, del riempimento e dell'evidenziazione del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Esempio di impostazione di tratto e riempimento in colori diversi  
  
 ![Testo con tratto con immagine applicato alla traccia](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Esempio di un pennello immagine applicato al tratto  
  
 ![Testo con tratto con immagine applicato alla traccia](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Esempio di un pennello immagine applicato al tratto ed evidenziazione  
  
 Per ulteriori informazioni sul <xref:System.Windows.Media.FormattedText> , vedere [disegno testo in formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Più esperti del testo [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre la possibilità di creare layout di testo personalizzato utilizzando la <xref:System.Windows.Media.TextFormatting.TextFormatter> oggetto e altri tipi nel <xref:System.Windows.Media.TextFormatting> dello spazio dei nomi. Il <xref:System.Windows.Media.TextFormatting.TextFormatter> e classi associate consentono di implementare il layout di testo personalizzato che supporta la definizione di formati di carattere, gli stili di paragrafo, regole di interruzione di riga e altre funzionalità di layout per il testo internazionale. Sono pochi i casi in cui occorre eseguire l'override dell'implementazione predefinita del supporto di layout di testo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se tuttavia occorre creare un controllo o un'applicazione di modifica del testo, potrebbe essere necessaria un'implementazione diversa da quella predefinita di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 A differenza di una tradizionale [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> interagisce con un client di layout di testo tramite un set di metodi di callback. È necessario che il client fornire un'implementazione di questi metodi di <xref:System.Windows.Media.TextFormatting.TextSource> classe. Nel diagramma seguente viene illustrata l'interazione di layout di testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramma del client di layout di testo e TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interazione tra l'applicazione e TextFormatter  
  
 Per informazioni dettagliate sulla creazione di layout di testo personalizzati, vedere [Formattazione del testo avanzata](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.FormattedText>  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>  
 [Panoramica su ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)  
 [Funzionalità dei tipi di carattere OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [Disegno di testo formattato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [Formattazione del testo avanzata](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Microsoft Typography](http://www.microsoft.com/typography/default.mspx)
