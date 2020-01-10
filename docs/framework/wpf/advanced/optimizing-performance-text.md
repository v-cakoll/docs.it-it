---
title: 'Ottimizzazione delle prestazioni: testo'
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
ms.openlocfilehash: 3e729458538353499f27f95ea2ca37fea1335238
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740347"
---
# <a name="optimizing-performance-text"></a>Ottimizzazione delle prestazioni: testo

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include il supporto per la presentazione di contenuto di testo tramite l'uso di controlli avanzati della [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. In generale, è possibile suddividere il rendering del testo in tre livelli:

1. Utilizzando direttamente gli oggetti <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun>.

2. Utilizzando l'oggetto <xref:System.Windows.Media.FormattedText>.

3. Uso di controlli di alto livello, ad esempio gli oggetti <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument>.

Questo argomento offre utili suggerimenti sulle prestazioni del rendering del testo.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Rendering del testo a livello di glifo

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre supporto avanzato per il testo, incluso il markup a livello di glifo, con accesso diretto ai <xref:System.Windows.Documents.Glyphs> per i clienti che desiderano intercettare e mantenere il testo dopo la formattazione. Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.

- Visualizzazione di documenti a formato fisso.

- Scenari di stampa.

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] come linguaggio della stampante.

  - Microsoft XPS Document Writer.

  - Driver della stampante precedenti, output delle applicazioni Win32 nel formato fisso.

  - Formato dello spooling di stampa.

- Rappresentazione di documenti a formato fisso, inclusi i client per le versioni precedenti di Windows e altri dispositivi di elaborazione.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun> sono progettati per scenari di presentazione e stampa di documenti a formato fisso. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce diversi elementi per il layout generale e scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], ad esempio <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.TextBlock>. Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](typography-in-wpf.md).

Negli esempi seguenti viene illustrato come definire le proprietà per un oggetto <xref:System.Windows.Documents.Glyphs> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. L'oggetto <xref:System.Windows.Documents.Glyphs> rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Negli esempi si presuppone che i tipi di carattere Arial, Courier New e Times New Roman siano installati nella cartella **C:\WINDOWS\Fonts** nel computer locale.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Uso di DrawGlyphRun

Se si dispone di un controllo personalizzato e si desidera eseguire il rendering dei glifi, utilizzare il metodo <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A>.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce anche servizi di livello inferiore per la formattazione di testo personalizzata tramite l'utilizzo dell'oggetto <xref:System.Windows.Media.FormattedText>. Il modo più efficiente per eseguire il rendering del testo in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consiste nel generare contenuto di testo a livello di glifo utilizzando <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun>. Tuttavia, il costo di questa efficienza è la perdita di una formattazione del testo RTF facile da usare, ovvero funzionalità predefinite dei controlli [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], ad esempio <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument>.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>Oggetto FormattedText

L'oggetto <xref:System.Windows.Media.FormattedText> consente di creare testo su più righe, in cui ogni carattere del testo può essere formattato singolarmente. Per altre informazioni, vedere [Disegno di testo formattato](drawing-formatted-text.md).

Per creare un testo formattato, chiamare il costruttore <xref:System.Windows.Media.FormattedText.%23ctor%2A> per creare un oggetto <xref:System.Windows.Media.FormattedText>. Dopo aver creato la stringa di testo formattato iniziale, è possibile applicare una gamma di stili di formattazione. Se l'applicazione desidera implementare il proprio layout, l'oggetto <xref:System.Windows.Media.FormattedText> è preferibile rispetto all'uso di un controllo, ad esempio <xref:System.Windows.Controls.TextBlock>. Per ulteriori informazioni sull'oggetto <xref:System.Windows.Media.FormattedText>, vedere [disegno di testo formattato](drawing-formatted-text.md) .

L'oggetto <xref:System.Windows.Media.FormattedText> fornisce funzionalità di formattazione del testo di basso livello. È possibile applicare vari stili di formattazione a uno o più caratteri. È ad esempio possibile chiamare entrambi i metodi <xref:System.Windows.Media.FormattedText.SetFontSize%2A> e <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> per modificare la formattazione dei primi cinque caratteri del testo.

Nell'esempio di codice seguente viene creato un oggetto <xref:System.Windows.Media.FormattedText> e ne viene eseguito il rendering.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>Controlli FlowDocument, TextBlock e Label

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per la creazione di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>Un elemento FlowDocument influisce sulle prestazioni più di un elemento TextBlock o Label

In generale, l'elemento <xref:System.Windows.Controls.TextBlock> deve essere utilizzato quando è necessario il supporto di testo limitato, ad esempio una breve frase in una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> può essere utilizzato quando è richiesto un supporto di testo minimo. L'elemento <xref:System.Windows.Documents.FlowDocument> è un contenitore per i documenti riflussi che supportano la presentazione dettagliata del contenuto e, di conseguenza, ha un maggiore effetto sulle prestazioni rispetto all'uso dei controlli <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.Label>.

Per altre informazioni su <xref:System.Windows.Documents.FlowDocument>, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Evitare di usare TextBlock in FlowDocument

L'elemento <xref:System.Windows.Controls.TextBlock> deriva da <xref:System.Windows.UIElement>. L'elemento <xref:System.Windows.Documents.Run> deriva da <xref:System.Windows.Documents.TextElement>, che è meno costoso da usare rispetto a un oggetto derivato da <xref:System.Windows.UIElement>. Quando possibile, usare <xref:System.Windows.Documents.Run> anziché <xref:System.Windows.Controls.TextBlock> per visualizzare il contenuto di testo in un <xref:System.Windows.Documents.FlowDocument>.

L'esempio di markup seguente illustra due modi per impostare il contenuto di testo all'interno di un <xref:System.Windows.Documents.FlowDocument>:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Evitare di usare un oggetto Run per impostare proprietà di testo

In generale, l'uso di un <xref:System.Windows.Documents.Run> all'interno di una <xref:System.Windows.Controls.TextBlock> è più intenso rispetto all'uso di un oggetto <xref:System.Windows.Documents.Run> esplicito. Se si utilizza una <xref:System.Windows.Documents.Run> per impostare le proprietà del testo, impostare le proprietà direttamente nel <xref:System.Windows.Controls.TextBlock>.

Nell'esempio di markup seguente vengono illustrate queste due modalità di impostazione di una proprietà di testo, in questo caso la proprietà <xref:System.Windows.Controls.TextBlock.FontWeight%2A>:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

La tabella seguente mostra il costo della visualizzazione di 1000 <xref:System.Windows.Controls.TextBlock> oggetti con e senza una <xref:System.Windows.Documents.Run>esplicita.

|**Tipo di TextBlock**|**Tempo di creazione (ms)**|**Tempo di rendering (ms)**|
|------------------------|------------------------------|----------------------------|
|Proprietà di testo impostate con Run|146|540|
|Proprietà di testo impostate con TextBlock|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitare di eseguire il data binding alla proprietà Label.Content

Si immagini uno scenario in cui si dispone di un oggetto <xref:System.Windows.Controls.Label> aggiornato di frequente da un'origine <xref:System.String>. Quando data binding la proprietà <xref:System.Windows.Controls.ContentControl.Content%2A> dell'elemento <xref:System.Windows.Controls.Label> all'oggetto di origine <xref:System.String>, è possibile che si verifichi una riduzione delle prestazioni. Ogni volta che viene aggiornata la <xref:System.String> di origine, l'oggetto <xref:System.String> precedente viene eliminato e viene ricreato un nuovo <xref:System.String>, perché un oggetto <xref:System.String> non è modificabile e non può essere modificato. Questo, a sua volta, fa sì che il <xref:System.Windows.Controls.ContentPresenter> dell'oggetto <xref:System.Windows.Controls.Label> elimini il contenuto precedente e rigeneri il nuovo contenuto per visualizzare il nuovo <xref:System.String>.

La soluzione di questo problema è semplice. Se il <xref:System.Windows.Controls.Label> non è impostato su un valore <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> personalizzato, sostituire il <xref:System.Windows.Controls.Label> con una <xref:System.Windows.Controls.TextBlock> e associare i dati alla relativa proprietà <xref:System.Windows.Controls.TextBlock.Text%2A> nella stringa di origine.

|**Proprietà con data binding**|**Tempo di aggiornamento (ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Collegamento ipertestuale

L'oggetto <xref:System.Windows.Documents.Hyperlink> è un elemento di contenuto del flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto del flusso.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinare collegamenti ipertestuali in un oggetto TextBlock

È possibile ottimizzare l'utilizzo di più elementi <xref:System.Windows.Documents.Hyperlink> raggruppando questi elementi all'interno della stessa <xref:System.Windows.Controls.TextBlock>. In questo modo, è possibile ridurre al minimo il numero di oggetti creati nell'applicazione. È possibile, ad esempio, che si voglia visualizzare più collegamenti ipertestuali, come illustrato di seguito:

Home page MSN &#124; MSN

L'esempio di markup seguente mostra più elementi <xref:System.Windows.Controls.TextBlock> utilizzati per visualizzare i collegamenti ipertestuali:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

L'esempio di markup seguente mostra un modo più efficiente per visualizzare i collegamenti ipertestuali, questa volta usando una singola <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Visualizzazione delle sottolineature nei collegamenti ipertestuali solo in caso di eventi MouseEnter

Un oggetto <xref:System.Windows.TextDecoration> è un ornamento visivo che è possibile aggiungere al testo; Tuttavia, può essere un'attività che richiede un utilizzo intensivo delle prestazioni. Se si utilizza in modo esteso gli elementi di <xref:System.Windows.Documents.Hyperlink>, è consigliabile visualizzare una sottolineatura solo quando si attiva un evento, ad esempio l'evento <xref:System.Windows.ContentElement.MouseEnter>. Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md).

Nell'immagine seguente viene illustrato il modo in cui l'evento MouseEnter attiva il collegamento ipertestuale sottolineato:

![Collegamenti ipertestuali con TextDecoration](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

Nell'esempio di markup seguente viene illustrato un <xref:System.Windows.Documents.Hyperlink> definito con e senza sottolineatura:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

La tabella seguente mostra il costo in termini di prestazioni della visualizzazione degli elementi di 1000 <xref:System.Windows.Documents.Hyperlink> con e senza una sottolineatura.

|**Collegamento ipertestuale**|**Tempo di creazione (ms)**|**Tempo di rendering (ms)**|
|-------------------|------------------------------|----------------------------|
|Con sottolineatura|289|1130|
|Senza sottolineatura|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Funzionalità di formattazione del testo

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce servizi di formattazione RTF come le sillabazioni automatiche. Questi servizi possono influire sulle prestazioni dell'applicazione e devono essere usati solo se strettamente necessario.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evitare l'uso non necessario della sillabazione

La sillabazione automatica trova i punti di interruzione del segno meno per le righe di testo e consente posizioni di interruzione aggiuntive per le linee in <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> oggetti. Per impostazione predefinita, la funzionalità di sillabazione automatica è disattivata in questi oggetti. È possibile attivare questa funzionalità impostando la proprietà IsHyphenationEnabled dell'oggetto su `true`. Tuttavia, l'abilitazione di questa funzionalità comporta l'avvio dell'interoperabilità di Component Object Model (COM) da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che può influisce sulle prestazioni dell'applicazione. È consigliabile quindi usare la sillabazione automatica solo se necessario.

### <a name="use-figures-carefully"></a>Usare con attenzione gli elementi Figure

Un elemento <xref:System.Windows.Documents.Figure> rappresenta una parte di contenuto dinamico che può essere posizionata in modo assoluto all'interno di una pagina di contenuto. In alcuni casi, una <xref:System.Windows.Documents.Figure> può causare la riformattazione automatica di un'intera pagina se la posizione è in conflitto con il contenuto già definito. È possibile ridurre al minimo la possibilità di riformattazione non necessaria raggruppando gli elementi <xref:System.Windows.Documents.Figure> uno accanto all'altro o dichiarando tali elementi nella parte superiore del contenuto in uno scenario di dimensioni di pagina fisse.

### <a name="optimal-paragraph"></a>Paragrafo ottimale

La funzionalità di paragrafo ottimale dell'oggetto <xref:System.Windows.Documents.FlowDocument> dispone i paragrafi, in modo che gli spazi vuoti vengano distribuiti nel modo più uniforme possibile. Per impostazione predefinita, la funzionalità di paragrafo ottimale è disattivata. È possibile abilitare questa funzionalità impostando la proprietà <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> dell'oggetto su `true`. L'attivazione di questa funzionalità, tuttavia, influisce sulle prestazioni dell'applicazione. È consigliabile quindi usare la funzionalità di paragrafo ottimale solo se necessario.

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
