---
title: 'Ottimizzazione delle prestazioni: Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: 4835fb42a8976d94be223d8306d1eb16e330f8f5
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "68434017"
---
# <a name="optimizing-performance-text"></a>Ottimizzazione delle prestazioni: Text

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include il supporto per la presentazione di contenuto di testo tramite l'uso di controlli avanzati della [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. In generale, è possibile suddividere il rendering del testo in tre livelli:

1. Utilizzando direttamente <xref:System.Windows.Documents.Glyphs> gli <xref:System.Windows.Media.GlyphRun> oggetti e.

2. Utilizzando l' <xref:System.Windows.Media.FormattedText> oggetto.

3. Uso di controlli di alto livello, ad esempio <xref:System.Windows.Controls.TextBlock> gli <xref:System.Windows.Documents.FlowDocument> oggetti e.

Questo argomento offre utili suggerimenti sulle prestazioni del rendering del testo.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Rendering del testo a livello di glifo

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]fornisce supporto avanzato per il testo, incluso il markup a livello di <xref:System.Windows.Documents.Glyphs> glifo, con accesso diretto a per i clienti che desiderano intercettare e mantenere il testo dopo la formattazione. Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.

- Visualizzazione di documenti a formato fisso.

- Scenari di stampa.

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] come linguaggio della stampante.

  - [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].

  - Driver della stampante precedenti, output delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] in formato fisso.

  - Formato dello spooling di stampa.

- Rappresentazione di documenti con formato fisso, inclusi i client di versioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e altri dispositivi di elaborazione.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>e <xref:System.Windows.Media.GlyphRun> sono progettati per scenari di presentazione e stampa di documenti a formato fisso. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]in sono disponibili diversi elementi per layout [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] generale e scenari <xref:System.Windows.Controls.Label> quali <xref:System.Windows.Controls.TextBlock>e. Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](typography-in-wpf.md).

Negli esempi seguenti viene illustrato come definire le proprietà per <xref:System.Windows.Documents.Glyphs> un oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]in. L' <xref:System.Windows.Documents.Glyphs> oggetto rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]in. Negli esempi si presuppone che i tipi di carattere Arial, Courier New e Times New Roman siano installati nella cartella **C:\WINDOWS\Fonts** nel computer locale.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Uso di DrawGlyphRun

Se si dispone di un controllo personalizzato e si desidera eseguire il rendering dei glifi <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> , utilizzare il metodo.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce anche servizi di livello inferiore per la formattazione di testo personalizzata tramite l'utilizzo <xref:System.Windows.Media.FormattedText> dell'oggetto. Il modo più efficiente per eseguire il rendering [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] del testo in è la generazione di contenuto di testo <xref:System.Windows.Documents.Glyphs> a <xref:System.Windows.Media.GlyphRun>livello di glifo utilizzando e. Tuttavia, il costo di questa efficienza è la perdita di una formattazione del testo RTF facile da usare, ovvero funzionalità predefinite dei [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controlli, <xref:System.Windows.Controls.TextBlock> ad esempio e <xref:System.Windows.Documents.FlowDocument>.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>Oggetto FormattedText

L' <xref:System.Windows.Media.FormattedText> oggetto consente di creare testo su più righe, in cui ogni carattere del testo può essere formattato singolarmente. Per altre informazioni, vedere [Disegno di testo formattato](drawing-formatted-text.md).

Per creare un testo formattato, <xref:System.Windows.Media.FormattedText.%23ctor%2A> chiamare il costruttore per <xref:System.Windows.Media.FormattedText> creare un oggetto. Dopo aver creato la stringa di testo formattato iniziale, è possibile applicare una gamma di stili di formattazione. Se l'applicazione desidera implementare un layout specifico, l'oggetto è <xref:System.Windows.Media.FormattedText> migliore rispetto all'utilizzo di un controllo, <xref:System.Windows.Controls.TextBlock>ad esempio. Per ulteriori informazioni sull' <xref:System.Windows.Media.FormattedText> oggetto, vedere disegno di [testo formattato](drawing-formatted-text.md) .

L' <xref:System.Windows.Media.FormattedText> oggetto fornisce funzionalità di formattazione del testo di basso livello. È possibile applicare vari stili di formattazione a uno o più caratteri. Ad esempio, è possibile chiamare entrambi i <xref:System.Windows.Media.FormattedText.SetFontSize%2A> metodi <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> e per modificare la formattazione dei primi cinque caratteri del testo.

Nell'esempio di codice seguente viene <xref:System.Windows.Media.FormattedText> creato un oggetto e ne viene eseguito il rendering.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>Controlli FlowDocument, TextBlock e Label

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per la creazione di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>Un elemento FlowDocument influisce sulle prestazioni più di un elemento TextBlock o Label

In generale, l' <xref:System.Windows.Controls.TextBlock> elemento deve essere utilizzato quando è necessario il supporto di testo limitato, ad esempio una breve frase [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]in un. <xref:System.Windows.Controls.Label>può essere utilizzato quando è richiesto un supporto di testo minimo. L' <xref:System.Windows.Documents.FlowDocument> elemento è un contenitore per i documenti riflussi che supportano la presentazione dettagliata del contenuto e, di conseguenza, ha un maggiore effetto sulle prestazioni rispetto <xref:System.Windows.Controls.TextBlock> all' <xref:System.Windows.Controls.Label> uso dei controlli o.

Per altre informazioni su <xref:System.Windows.Documents.FlowDocument>, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Evitare di usare TextBlock in FlowDocument

L' <xref:System.Windows.Controls.TextBlock> elemento è derivato da <xref:System.Windows.UIElement>. L' <xref:System.Windows.Documents.Run> elemento è derivato da <xref:System.Windows.Documents.TextElement>, che è meno costoso da usare rispetto a un <xref:System.Windows.UIElement>oggetto derivato da. Quando possibile, usare <xref:System.Windows.Documents.Run> <xref:System.Windows.Controls.TextBlock> anziché per visualizzare il contenuto di testo in <xref:System.Windows.Documents.FlowDocument>un oggetto.

L'esempio di markup seguente illustra due modi per impostare il contenuto di testo <xref:System.Windows.Documents.FlowDocument>all'interno di un:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Evitare di usare un oggetto Run per impostare proprietà di testo

In generale, l'utilizzo <xref:System.Windows.Documents.Run> di un <xref:System.Windows.Controls.TextBlock> oggetto all'interno di un oggetto è più intenso <xref:System.Windows.Documents.Run> rispetto al mancato utilizzo di un oggetto esplicito. Se si usa un oggetto <xref:System.Windows.Documents.Run> per impostare le <xref:System.Windows.Controls.TextBlock> proprietà di testo, impostare le proprietà direttamente in.

L'esempio di markup seguente illustra questi due modi per impostare una proprietà di testo, in questo caso la <xref:System.Windows.Controls.TextBlock.FontWeight%2A> proprietà:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

La tabella seguente mostra il costo della visualizzazione di <xref:System.Windows.Controls.TextBlock> oggetti 1000 con e senza un <xref:System.Windows.Documents.Run>oggetto esplicito.

|**Tipo di TextBlock**|**Tempo di creazione (ms)**|**Tempo di rendering (ms)**|
|------------------------|------------------------------|----------------------------|
|Proprietà di testo impostate con Run|146|540|
|Proprietà di testo impostate con TextBlock|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitare di eseguire il data binding alla proprietà Label.Content

Si immagini uno scenario in cui è <xref:System.Windows.Controls.Label> presente un oggetto aggiornato di frequente da <xref:System.String> un'origine. Quando si data binding <xref:System.Windows.Controls.Label> la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà dell'elemento all' <xref:System.String> oggetto di origine, è possibile che si verifichi una riduzione delle prestazioni. Ogni volta che l' <xref:System.String> origine viene aggiornata, l' <xref:System.String> oggetto precedente viene eliminato e viene ricreato <xref:System.String> un nuovo, perché un <xref:System.String> oggetto non è modificabile e non può essere modificato. Questo, a sua volta, fa <xref:System.Windows.Controls.ContentPresenter> sì che <xref:System.Windows.Controls.Label> il dell'oggetto elimini il contenuto precedente e rigeneri il nuovo contenuto per visualizzare <xref:System.String>il nuovo.

La soluzione di questo problema è semplice. Se l' <xref:System.Windows.Controls.Label> oggetto non è impostato su un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> valore personalizzato, sostituire <xref:System.Windows.Controls.Label> con un <xref:System.Windows.Controls.TextBlock> e i dati associarne <xref:System.Windows.Controls.TextBlock.Text%2A> la proprietà alla stringa di origine.

|**Proprietà con data binding**|**Tempo di aggiornamento (ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Hyperlink

L' <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto del flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto del flusso.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinare collegamenti ipertestuali in un oggetto TextBlock

È possibile ottimizzare l'utilizzo di più <xref:System.Windows.Documents.Hyperlink> elementi raggruppando gli elementi all'interno dello stesso <xref:System.Windows.Controls.TextBlock>. In questo modo, è possibile ridurre al minimo il numero di oggetti creati nell'applicazione. È possibile, ad esempio, che si voglia visualizzare più collegamenti ipertestuali, come illustrato di seguito:

Home page MSN &#124; MSN

L'esempio di markup seguente mostra <xref:System.Windows.Controls.TextBlock> più elementi usati per visualizzare i collegamenti ipertestuali:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

L'esempio di markup seguente mostra un modo più efficiente per visualizzare i collegamenti ipertestuali, questa volta usando un singolo <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Visualizzazione delle sottolineature nei collegamenti ipertestuali solo in caso di eventi MouseEnter

Un <xref:System.Windows.TextDecoration> oggetto è un ornamento visivo che è possibile aggiungere al testo; tuttavia, può essere un'attività che richiede un elevato utilizzo delle prestazioni. Se si fa uso estensivo <xref:System.Windows.Documents.Hyperlink> di elementi, provare a visualizzare una sottolineatura solo quando si attiva un evento <xref:System.Windows.ContentElement.MouseEnter> , ad esempio l'evento. Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md).

Nell'immagine seguente viene illustrato il modo in cui l'evento MouseEnter attiva il collegamento ipertestuale sottolineato:

![Collegamenti ipertestuali con TextDecoration](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

L'esempio di markup seguente mostra <xref:System.Windows.Documents.Hyperlink> un oggetto definito con e senza sottolineatura:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

La tabella seguente mostra il costo delle prestazioni della visualizzazione <xref:System.Windows.Documents.Hyperlink> di 1000 elementi con e senza una sottolineatura.

|**Collegamento ipertestuale**|**Tempo di creazione (ms)**|**Tempo di rendering (ms)**|
|-------------------|------------------------------|----------------------------|
|Con sottolineatura|289|1130|
|Senza sottolineatura|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Funzionalità di formattazione del testo

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce servizi di formattazione RTF come le sillabazioni automatiche. Questi servizi possono influire sulle prestazioni dell'applicazione e devono essere usati solo se strettamente necessario.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evitare l'uso non necessario della sillabazione

La sillabazione automatica trova i punti di interruzione del segno meno per le righe di testo e consente posizioni <xref:System.Windows.Controls.TextBlock> di <xref:System.Windows.Documents.FlowDocument> interruzione aggiuntive per le linee negli oggetti e. Per impostazione predefinita, la funzionalità di sillabazione automatica è disattivata in questi oggetti. È possibile attivare questa funzionalità impostando la proprietà IsHyphenationEnabled dell'oggetto su `true`. Tuttavia, l'abilitazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] questa funzionalità comporta l'avvio dell'interoperabilità Component Object Model (com), che può influisce sulle prestazioni dell'applicazione. È consigliabile quindi usare la sillabazione automatica solo se necessario.

### <a name="use-figures-carefully"></a>Usare con attenzione gli elementi Figure

Un <xref:System.Windows.Documents.Figure> elemento rappresenta una parte di contenuto del flusso che può essere posizionata in modo assoluto all'interno di una pagina di contenuto. In alcuni casi, un <xref:System.Windows.Documents.Figure> può causare la riformattazione automatica di un'intera pagina se la posizione è in conflitto con il contenuto già definito. È possibile ridurre al minimo la possibilità di riformattazione non necessaria tramite il <xref:System.Windows.Documents.Figure> raggruppamento degli elementi uno accanto all'altro oppure dichiarando tali elementi nella parte superiore del contenuto in uno scenario di dimensioni di pagina fisse.

### <a name="optimal-paragraph"></a>Paragrafo ottimale

La funzionalità di paragrafo ottimale dell' <xref:System.Windows.Documents.FlowDocument> oggetto definisce i paragrafi in modo che gli spazi vuoti vengano distribuiti nel modo più uniforme possibile. Per impostazione predefinita, la funzionalità di paragrafo ottimale è disattivata. È possibile abilitare questa funzionalità impostando la <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> proprietà dell'oggetto su. `true` L'attivazione di questa funzionalità, tuttavia, influisce sulle prestazioni dell'applicazione. È consigliabile quindi usare la funzionalità di paragrafo ottimale solo se necessario.

## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
