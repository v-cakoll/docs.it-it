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
ms.openlocfilehash: 177f42dfa1c1be2b12d7e9e5283cf57f14c0880c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548870"
---
# <a name="optimizing-performance-text"></a>Ottimizzazione delle prestazioni: testo
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include il supporto per la presentazione di contenuto di testo tramite l'uso di controlli avanzati della [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. In generale, è possibile suddividere il rendering del testo in tre livelli:  
  
1.  Utilizzo di <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun> direttamente gli oggetti.  
  
2.  Utilizzo di <xref:System.Windows.Media.FormattedText> oggetto.  
  
3.  Utilizzando i controlli di alto livello, ad esempio il <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> oggetti.  
  
 Questo argomento offre utili suggerimenti sulle prestazioni del rendering del testo.  
  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Rendering del testo a livello di glifo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il supporto di testo avanzato, incluso il markup a livello di glifo con accesso diretto a <xref:System.Windows.Documents.Glyphs> per i clienti che desiderano intercettare e rendere persistenti testo dopo la formattazione. Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.  
  
-   Visualizzazione di documenti a formato fisso.  
  
-   Scenari di stampa.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] come linguaggio della stampante.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Driver della stampante precedenti, output delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] in formato fisso.  
  
    -   Formato dello spooling di stampa.  
  
-   Rappresentazione di documenti con formato fisso, inclusi i client di versioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e altri dispositivi di elaborazione.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun> sono progettati per la presentazione del documento a formato fisso e scenari di stampa. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vengono forniti diversi elementi per il layout generale e [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenari, ad esempio <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.TextBlock>. Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Negli esempi seguenti viene illustrano come definire le proprietà per un <xref:System.Windows.Documents.Glyphs> oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Il <xref:System.Windows.Documents.Glyphs> oggetto rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Negli esempi si presuppone che i tipi di carattere Arial, Courier New e Times New Roman siano installati nella cartella **C:\WINDOWS\Fonts** nel computer locale.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>Uso di DrawGlyphRun  
 Se si dispone di un controllo personalizzato e si desidera eseguire il rendering delle icone, utilizzare il <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> metodo.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono inoltre disponibili servizi di basso livello per la formattazione personalizzata mediante l'utilizzo del <xref:System.Windows.Media.FormattedText> oggetto. Il modo più efficiente il rendering del testo in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è tramite la generazione di contenuto di testo a livello di glifo tramite <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun>. Tuttavia, il costo di questa efficienza è la perdita di facile utilizzo in formato RTF funzionalità incorporate di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controlli, ad esempio <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>Oggetto FormattedText  
 Il <xref:System.Windows.Media.FormattedText> oggetto consente di disegnare testo su più righe in cui ogni carattere del testo può essere formattato singolarmente. Per altre informazioni, vedere [Disegno di testo formattato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Per creare il testo formattato, chiamare il <xref:System.Windows.Media.FormattedText.%23ctor%2A> costruttore per creare un <xref:System.Windows.Media.FormattedText> oggetto. Dopo aver creato la stringa di testo formattato iniziale, è possibile applicare una gamma di stili di formattazione. Se l'applicazione desidera implementare un layout personalizzato, quindi il <xref:System.Windows.Media.FormattedText> oggetto è preferibile rispetto all'utilizzo di un controllo, ad esempio <xref:System.Windows.Controls.TextBlock>. Per ulteriori informazioni sul <xref:System.Windows.Media.FormattedText> , vedere [disegno testo in formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 Il <xref:System.Windows.Media.FormattedText> oggetto fornisce funzionalità di formattazione del testo di basso livello. È possibile applicare vari stili di formattazione a uno o più caratteri. Ad esempio, è possibile chiamare entrambi il <xref:System.Windows.Media.FormattedText.SetFontSize%2A> e <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> metodi per modificare la formattazione dei primi cinque caratteri nel testo.  
  
 L'esempio di codice seguente crea un <xref:System.Windows.Media.FormattedText> dell'oggetto e ne esegue il rendering.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>Controlli FlowDocument, TextBlock e Label  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per la creazione di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>Un elemento FlowDocument influisce sulle prestazioni più di un elemento TextBlock o Label  
 In generale, il <xref:System.Windows.Controls.TextBlock> elemento deve essere utilizzato quando il supporto limitato del testo è richiesto, ad esempio una frase breve in un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> può essere utilizzato quando è richiesto il supporto minimo del testo. Il <xref:System.Windows.Documents.FlowDocument> elemento è un contenitore per i documenti rinnovabile che supportano la presentazione dettagliata del contenuto e di conseguenza, ha un impatto sulle prestazioni maggiore rispetto all'utilizzo di <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.Label> controlli.  
  
 Per ulteriori informazioni su <xref:System.Windows.Documents.FlowDocument>, vedere [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Evitare di usare TextBlock in FlowDocument  
 Il <xref:System.Windows.Controls.TextBlock> elemento derivato da <xref:System.Windows.UIElement>. Il <xref:System.Windows.Documents.Run> elemento derivato da <xref:System.Windows.Documents.TextElement>, che è meno dispendioso di impiego rispetto a un <xref:System.Windows.UIElement>-oggetto derivato. Quando possibile, utilizzare <xref:System.Windows.Documents.Run> anziché <xref:System.Windows.Controls.TextBlock> per visualizzare il contenuto di testo in un <xref:System.Windows.Documents.FlowDocument>.  
  
 L'esempio di codice seguente illustra due modalità di impostazione del contenuto di testo all'interno di un <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xaml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Evitare di usare un oggetto Run per impostare proprietà di testo  
 In generale, utilizzando un <xref:System.Windows.Documents.Run> all'interno di un <xref:System.Windows.Controls.TextBlock> è prestazioni più elevato rispetto al mancato utilizzo esplicita <xref:System.Windows.Documents.Run> oggetto affatto. Se si utilizza un <xref:System.Windows.Documents.Run> per impostare le proprietà di testo, impostare tali proprietà direttamente nel <xref:System.Windows.Controls.TextBlock> invece.  
  
 L'esempio di codice seguente illustra queste due modalità di impostazione di una proprietà di testo, in questo caso, il <xref:System.Windows.Controls.TextBlock.FontWeight%2A> proprietà:  
  
 [!code-xaml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 La tabella seguente mostra il costo della visualizzazione 1000 <xref:System.Windows.Controls.TextBlock> oggetti con e senza esplicita <xref:System.Windows.Documents.Run>.  
  
|**Tipo di TextBlock**|**Tempo di creazione (ms)**|**Tempo di rendering (ms)**|  
|------------------------|------------------------------|----------------------------|  
|Proprietà di testo impostate con Run|146|540|  
|Proprietà di testo impostate con TextBlock|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitare di eseguire il data binding alla proprietà Label.Content  
 Si consideri uno scenario in cui è necessario un <xref:System.Windows.Controls.Label> oggetto che è stato aggiornato di frequente da un <xref:System.String> origine. Quando l'associazione dati di <xref:System.Windows.Controls.Label> dell'elemento <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà per il <xref:System.String> oggetto di origine, si potrebbe influire negativamente sulle prestazioni. Ogni volta che l'origine <xref:System.String> viene aggiornato, il vecchio <xref:System.String> oggetto viene ignorato e un nuovo <xref:System.String> viene ricreata, perché un <xref:System.String> oggetto non è modificabile, non può essere modificata. Questo causa a sua volta, il <xref:System.Windows.Controls.ContentPresenter> del <xref:System.Windows.Controls.Label> eliminato il contenuto precedente e rigenerare il nuovo contenuto per visualizzare il nuovo oggetto <xref:System.String>.  
  
 La soluzione di questo problema è semplice. Se il <xref:System.Windows.Controls.Label> non è impostata su un oggetto personalizzato <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> valore, sostituire il <xref:System.Windows.Controls.Label> con un <xref:System.Windows.Controls.TextBlock> l'associazione dati e relativo <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà alla stringa di origine.  
  
|**Proprietà con data binding**|**Tempo di aggiornamento (ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Hyperlink  
 Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto di flusso.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinare collegamenti ipertestuali in un oggetto TextBlock  
 È possibile ottimizzare l'utilizzo di più <xref:System.Windows.Documents.Hyperlink> elementi mediante il raggruppamento insieme all'interno dello stesso <xref:System.Windows.Controls.TextBlock>. In questo modo, è possibile ridurre al minimo il numero di oggetti creati nell'applicazione. È possibile, ad esempio, che si voglia visualizzare più collegamenti ipertestuali, come illustrato di seguito:  
  
 Home page MSN &#124; MSN  
  
 L'esempio di codice seguente illustra più <xref:System.Windows.Controls.TextBlock> elementi utilizzati per visualizzare i collegamenti ipertestuali:  
  
 [!code-xaml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 Nell'esempio di codice seguente viene illustrato un modo più efficiente per visualizzare i collegamenti ipertestuali, utilizzando una singola <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xaml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Visualizzazione delle sottolineature nei collegamenti ipertestuali solo in caso di eventi MouseEnter  
 Oggetto <xref:System.Windows.TextDecoration> oggetto è rappresenta ornamenti visivi che è possibile aggiungere testo, tuttavia, può essere prestazioni elevate per creare un'istanza. Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, provare a visualizzare un carattere di sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento. Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Collegamenti ipertestuali con TextDecoration](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Visualizzazione di collegamenti ipertestuali in caso di evento MouseEnter  
  
 Nell'esempio di codice seguente viene illustrato un <xref:System.Windows.Documents.Hyperlink> definito con e senza un carattere di sottolineatura:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Nella tabella seguente viene illustrato l'impatto sulle prestazioni della visualizzazione di 1000 <xref:System.Windows.Documents.Hyperlink> elementi con o senza un carattere di sottolineatura.  
  
|**Collegamento ipertestuale**|**Tempo di creazione (ms)**|**Tempo di rendering (ms)**|  
|-------------------|------------------------------|----------------------------|  
|Con sottolineatura|289|1130|  
|Senza sottolineatura|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Funzionalità di formattazione del testo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce servizi di formattazione RTF come le sillabazioni automatiche. Questi servizi possono influire sulle prestazioni dell'applicazione e devono essere usati solo se strettamente necessario.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evitare l'uso non necessario della sillabazione  
 Consente di individuare i punti di interruzione trattino per le righe di testo sillabazione e consente di posizioni di interruzione aggiuntiva per le righe in <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> oggetti. Per impostazione predefinita, la funzionalità di sillabazione automatica è disattivata in questi oggetti. È possibile attivare questa funzionalità impostando la proprietà IsHyphenationEnabled dell'oggetto su `true`. Con l'attivazione di questa funzionalità in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tuttavia, viene avviata anche l'interoperabilità [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], operazione che può influire sulle prestazioni dell'applicazione. È consigliabile quindi usare la sillabazione automatica solo se necessario.  
  
### <a name="use-figures-carefully"></a>Usare con attenzione gli elementi Figure  
 Oggetto <xref:System.Windows.Documents.Figure> elemento rappresenta una parte del contenuto del flusso che può essere posizionata all'interno di una pagina di contenuto. In alcuni casi, un <xref:System.Windows.Documents.Figure> può causare un'intera pagina riformattato automaticamente se la posizione in conflitto con il contenuto che è già stato disposto. È possibile ridurre al minimo la possibilità di riformattazione non necessaria entrambi raggruppamento <xref:System.Windows.Documents.Figure> elementi accanto a altro oppure dichiarandoli accanto all'inizio del contenuto in uno scenario di dimensioni di pagina fisse.  
  
### <a name="optimal-paragraph"></a>Paragrafo ottimale  
 La funzionalità di paragrafo ottimale del <xref:System.Windows.Documents.FlowDocument> oggetto dispone i paragrafi in modo che spazi vuoti siano distribuiti nel modo più uniforme possibile. Per impostazione predefinita, la funzionalità di paragrafo ottimale è disattivata. È possibile abilitare questa funzionalità impostando l'oggetto <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> proprietà `true`. L'attivazione di questa funzionalità, tuttavia, influisce sulle prestazioni dell'applicazione. È consigliabile quindi usare la funzionalità di paragrafo ottimale solo se necessario.  
  
## <a name="see-also"></a>Vedere anche  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
