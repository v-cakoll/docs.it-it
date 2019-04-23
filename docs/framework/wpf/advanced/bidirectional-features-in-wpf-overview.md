---
title: Cenni preliminari sulle funzionalità bidirezionali di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 575598f48b3cfdf636be78a9de6e0c9a7fd9c208
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079825"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Cenni preliminari sulle funzionalità bidirezionali di WPF
A differenza di altre piattaforme di sviluppo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta molte funzionalità che supportano lo sviluppo rapido di contenuto bidirezionale, ad esempio, misto dati da sinistra a destra e a destra per sinistra nello stesso documento. Allo stesso tempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un'esperienza eccellente per gli utenti che richiedono funzionalità bidirezionali, ad esempio gli utenti di lingua araba o ebraica.  
  
 Le sezioni seguenti illustrano molte funzionalità bidirezionali con i relativi esempi in cui viene descritto come ottenere la migliore visualizzazione di contenuto bidirezionale. Usare la maggior parte degli esempi [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], anche se è possibile applicare facilmente i concetti che è C# o il codice Microsoft Visual Basic.  

<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 La proprietà di base che definisce la direzione di flusso del contenuto in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Questa proprietà può essere impostata su uno dei due valori di enumerazione <xref:System.Windows.FlowDirection.LeftToRight> o <xref:System.Windows.FlowDirection.RightToLeft>. La proprietà è disponibile per tutti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli elementi che ereditano da <xref:System.Windows.FrameworkElement>.  
  
 L'esempio seguente imposta la direzione del flusso di un <xref:System.Windows.Controls.TextBox> elemento.  
  
 **Direzione di flusso da sinistra a destra**  
  
 [!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Direzione di flusso da destra a sinistra**  
  
 [!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 La figura seguente illustra il rendering del codice precedente.  
    
 ![Figura che illustra le diverse direzioni di flusso.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)  
  
 Un elemento all'interno di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] albero erediterà il <xref:System.Windows.FrameworkElement.FlowDirection%2A> dal relativo contenitore. Nell'esempio seguente, il <xref:System.Windows.Controls.TextBlock> si trova all'interno una <xref:System.Windows.Controls.Grid>, che risiede in un <xref:System.Windows.Window>. Impostando il <xref:System.Windows.FrameworkElement.FlowDirection%2A> per il <xref:System.Windows.Window> implica la sua impostazione per il <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.TextBlock> anche.  
  
 Nell'esempio seguente viene illustrata l'impostazione <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Il livello superiore <xref:System.Windows.Window> ha un <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, in modo che tutti gli elementi in esso contenuti anche ereditano lo stesso <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Per un elemento eseguire l'override di un oggetto specificato <xref:System.Windows.FrameworkElement.FlowDirection%2A> è necessario aggiungere una modifica della direzione esplicita, ad esempio il secondo <xref:System.Windows.Controls.TextBlock> nell'esempio precedente in cui viene modificato in <xref:System.Windows.FlowDirection.LeftToRight>. Se non si specifica <xref:System.Windows.FrameworkElement.FlowDirection%2A> è definito, il valore predefinito <xref:System.Windows.FlowDirection.LeftToRight> si applica.  
  
 La figura seguente mostra l'output dell'esempio precedente:

 ![Figura che illustra la modifica di direzione esplicita del flusso.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)  

<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Molte piattaforme di sviluppo, ad esempio [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e Java offrono un supporto speciale per lo sviluppo di contenuto bidirezionale. Linguaggi di markup, ad esempio [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] offrono agli autori di contenuti il markup necessario per visualizzare il testo in qualsiasi direzione richiesta, ad esempio il [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 tag, "dir" che accetta come valori "rtl" o "ltr". Questo tag è simile al <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà, ma il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà funziona in modo più avanzato per il layout del contenuto testuale e può essere usata per contenuti diversi dal testo.  
  
 Nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], una <xref:System.Windows.Documents.FlowDocument> è un versatile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento che può contenere una combinazione di testo, tabelle, immagini e altri elementi. Gli esempi nelle sezioni seguenti usano questo elemento.  
  
 Aggiunta di testo a un <xref:System.Windows.Documents.FlowDocument> può essere eseguita in molti modi. Un modo semplice per farlo è tramite un <xref:System.Windows.Documents.Paragraph> che è un elemento a livello di blocco usato per raggruppare il contenuto, ad esempio testo. Per aggiungere testo agli elementi di livello inline gli esempi usano <xref:System.Windows.Documents.Span> e <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span> è un elemento di contenuto del flusso di livello inline utilizzato per raggruppare altri elementi inline, mentre un <xref:System.Windows.Documents.Run> è un flusso di livello inline del contenuto elemento destinato a contenere una sequenza di testo non formattato. Oggetto <xref:System.Windows.Documents.Span> può contenere più <xref:System.Windows.Documents.Run> elementi.  
  
 Il primo esempio di documento contiene un documento contenente un numero di rete condivisione nomi; ad esempio `\\server1\folder\file.ext`. Indipendentemente dal fatto che questo collegamento di rete si trovi in un documento in arabo o in inglese, si vuole che venga sempre visualizzato nello stesso modo. La figura seguente viene illustrato l'utilizzo dell'elemento Span e Mostra il collegamento in un alfabeto arabo <xref:System.Windows.FlowDirection.RightToLeft> documento:

 ![Figura che illustra l'uso dell'elemento Span. ](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")  
  
 Poiché il testo viene <xref:System.Windows.FlowDirection.RightToLeft>, tutti i particolari caratteri, ad esempio il "\\", separano il testo in un ordine da destra a sinistra. Di conseguenza il collegamento non viene visualizzato nell'ordine corretto, pertanto per risolvere il problema, il testo deve essere incorporato per mantenere un oggetto separato <xref:System.Windows.Documents.Run> trasmessi <xref:System.Windows.FlowDirection.LeftToRight>. Invece di un oggetto separato <xref:System.Windows.Documents.Run> per ogni lingua, un modo migliore per risolvere il problema consiste nell'incorporare il testo inglese usato meno frequentemente in un arabo più grande <xref:System.Windows.Documents.Span>.  
  
 La figura seguente illustra questa usando l'elemento Run incorporato in un elemento Span:

 ![Figura che illustra l'elemento Run incorporato in un elemento Span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)  
  
 Nell'esempio seguente viene illustrato l'utilizzo <xref:System.Windows.Documents.Run> e <xref:System.Windows.Documents.Span> elementi nei documenti.  
  
 [!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Elementi Span  
 Il <xref:System.Windows.Documents.Span> elemento funziona come un separatore di delimitazione tra testi con diverse direzioni di flusso.  Anche <xref:System.Windows.Documents.Span> elementi con la stessa direzione di flusso vengono considerati diversi ambiti bidirezionali che significa che il <xref:System.Windows.Documents.Span> gli elementi vengono ordinati del contenitore <xref:System.Windows.FlowDirection>, solo il contenuto all'interno di <xref:System.Windows.Documents.Span> elemento segue la <xref:System.Windows.FlowDirection> del <xref:System.Windows.Documents.Span>.  
  
 La figura seguente mostra la direzione del flusso di diversi <xref:System.Windows.Controls.TextBlock> elementi.  
    
 ![Figura che illustra i blocchi di testo con direzioni di flusso diverse.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Documents.Span> e <xref:System.Windows.Documents.Run> elementi da produrre i risultati mostrati nel grafico precedente.  
  
 [!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 Nel <xref:System.Windows.Controls.TextBlock> gli elementi nell'esempio, il <xref:System.Windows.Documents.Span> elementi vengono disposti in base al <xref:System.Windows.FlowDirection> di padri, ma il testo all'interno di ogni <xref:System.Windows.Documents.Span> elemento flussi in base alla propria <xref:System.Windows.FlowDirection>. Questa condizione può essere applicata all'alfabeto latino e arabo oppure a qualsiasi altra lingua.  
  
### <a name="adding-xmllang"></a>Aggiunta di xml:lang  
 La figura seguente illustra un altro esempio che usa numeri ed espressioni aritmetiche, ad esempio `"200.0+21.4=221.4"`. Si noti che solo il <xref:System.Windows.FlowDirection> è impostata.  
    
 ![Immagine che visualizza i numeri usando solo FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)  
  
 Gli utenti di questa applicazione rimarranno delusi dall'output, anche se il <xref:System.Windows.FlowDirection> corretto i numeri non a forma di come i numeri arabi devono essere modellati.  
  
 Gli elementi XAML possono includere un [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] attributo (`xml:lang`) che definisce la lingua di ogni elemento. XAML supporta anche un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] principio di lingua in base al quale `xml:lang` valori applicati agli elementi padre dell'albero vengono usati dagli elementi figlio. Nell'esempio precedente, perché non è stata definita una lingua per il <xref:System.Windows.Documents.Run> elementi, il valore predefinito a livello di elemento o uno qualsiasi dei superiore `xml:lang` è stato usato, ovvero `en-US` per XAML. L'algoritmo di data shaping numeri interno di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] seleziona i numeri nella lingua corrispondente, in questo caso l'inglese. Per rendere l'arabo correttamente rendering dei numeri `xml:lang` deve essere impostata.  
  
 La figura seguente mostra l'esempio con `xml:lang` aggiunto.  
    
 ![Figura che illustra i numeri arabi con flusso da destra a sinistra.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)  
  
 L'esempio seguente aggiunge `xml:lang` all'applicazione.  
  
 [!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Tenere presente che molte lingue hanno diversi `xml:lang` valori a seconda dell'area di destinazione, ad esempio, `"ar-SA"` e `"ar-EG"` rappresentano due varianti dell'arabo. Negli esempi precedenti viene illustrata la necessità di definire sia il `xml:lang` e <xref:System.Windows.FlowDirection> valori.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementi non di testo  
 <xref:System.Windows.FlowDirection> definisce non solo la modalità di scorrimento del testo in un elemento testuale, ma anche la direzione del flusso di quasi tutti gli altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento. Il grafico seguente mostra una <xref:System.Windows.Controls.ToolBar> che usa un oggetto orizzontale <xref:System.Windows.Media.LinearGradientBrush> per disegnare lo sfondo con una parentesi uncinata a sfumatura a destra.  

 ![Grafico che mostra una barra degli strumenti da sinistra a destra sfumatura.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)  
  
 Dopo aver impostato il <xref:System.Windows.FlowDirection> a <xref:System.Windows.FlowDirection.RightToLeft>, non solo le <xref:System.Windows.Controls.ToolBar> pulsanti sono disposti da destra a sinistra, ma anche il <xref:System.Windows.Media.LinearGradientBrush> riallinea gli offset in modo che scorrano da destra a sinistra.  
  
 La figura seguente mostra il riallineamento del <xref:System.Windows.Media.LinearGradientBrush>.  
    
 ![Figura che illustra una barra degli strumenti con un diritto di sfumatura a sinistra.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)  
  
 L'esempio seguente disegna un' <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>. (Per disegnarlo da sinistra a destra, rimuovere il <xref:System.Windows.FlowDirection> attributo la <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>Eccezioni di FlowDirection  
 Esistono alcuni casi in cui <xref:System.Windows.FlowDirection> non comportarsi come previsto. In questa sezione vengono illustrate due di queste eccezioni.  
  
 **Immagine**  
  
 Un <xref:System.Windows.Controls.Image> rappresenta un controllo che visualizza un'immagine. Nella [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] può essere utilizzato con un <xref:System.Windows.Controls.Image.Source%2A> proprietà che definisce il [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] del <xref:System.Windows.Controls.Image> da visualizzare.  
  
 A differenza di altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi, un <xref:System.Windows.Controls.Image> non eredita il <xref:System.Windows.FlowDirection> dal contenitore. Tuttavia, se il <xref:System.Windows.FlowDirection> è impostato in modo esplicito <xref:System.Windows.FlowDirection.RightToLeft>, un <xref:System.Windows.Controls.Image> viene visualizzato capovolto in senso orizzontale. Questa condizione viene implementata come una funzionalità utile per gli sviluppatori di contenuti bidirezionali, perché in alcuni casi il capovolgimento in senso orizzontale dell'immagine genera l'effetto desiderato.  
  
 La figura seguente mostra un capovolta <xref:System.Windows.Controls.Image>.  
    
 ![Figura che illustra un'immagine capovolta.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)  
  
 Nell'esempio seguente viene dimostrato che la <xref:System.Windows.Controls.Image> non riesce a ereditare la <xref:System.Windows.FlowDirection> dal <xref:System.Windows.Controls.StackPanel> che lo contiene. **Nota** è necessario disporre di un file denominato **ms_logo** nel c:\. unità per eseguire questo esempio.  
  
 [!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Nota** nei file di download è incluso un **ms_logo** file. Nel codice si presuppone che il file con estensione jpg non si trovi all'interno del progetto ma in un'altra posizione nell'unità C:\. È necessario copiare il file con estensione jpg dai file di progetto nell'unità C:\ oppure modificare il codice affinché la ricerca venga eseguita all'interno del progetto. A tale scopo, modificare `Source="file://c:/ms_logo.jpg"` a `Source="ms_logo.jpg"`.  
  
 **Percorsi**  
  
 Oltre a un <xref:System.Windows.Controls.Image>, un altro elemento interessante è <xref:System.Windows.Shapes.Path>. Path è un oggetto che consente di disegnare una serie di righe e curve collegate. Si comporta in modo analogo a un <xref:System.Windows.Controls.Image> relative a relativo <xref:System.Windows.FlowDirection>, ad esempio relativi <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> è un'immagine speculare orizzontale del relativo <xref:System.Windows.FlowDirection.LeftToRight> uno. Tuttavia, a differenza di un' <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> eredita relativo <xref:System.Windows.FlowDirection> dal contenitore e uno non è necessario specificarlo in modo esplicito.  
  
 L'esempio seguente disegna una freccia semplice con 3 linee. La prima freccia eredita la <xref:System.Windows.FlowDirection.RightToLeft> dalla direzione del flusso di <xref:System.Windows.Controls.StackPanel> in modo che i punti iniziali e finali vengano misurati da una radice posizionata sul lato destro. La seconda freccia è esplicita <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> inizia anche a destra. Tuttavia, la radice iniziale della terza freccia è collocata sul lato sinistro. Per altre informazioni sul disegno, vedere <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 La figura seguente mostra l'output dell'esempio precedente con le frecce disegnate usando il `Path` elemento:

 ![Figura che illustra le frecce disegnate usando l'elemento Path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)  
  
 Il <xref:System.Windows.Controls.Image> e <xref:System.Windows.Shapes.Path> sono riportati due esempi del modo in cui [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] utilizza <xref:System.Windows.FlowDirection>. Accanto a disposizione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi in una direzione specifica all'interno di un contenitore <xref:System.Windows.FlowDirection> può essere usato con gli elementi, ad esempio <xref:System.Windows.Controls.InkPresenter> che esegue il rendering dell'input penna su una superficie <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Ogni volta che è necessario un comportamento da destra a sinistra del contenuto che simuli un comportamento da sinistra a destra, o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] disponibile tale funzionalità.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Sostituzione numerica  
 In passato, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ha supportato la sostituzione dei numeri, consentendo la rappresentazione di diverse forme relative alla lingua per le stesse cifre e mantenendo l'archiviazione interna di queste cifre unificata le diverse impostazioni locali, ad esempio i numeri vengono archiviati i noti valori esadecimali, 0x40, 0x41, ma visualizzati in base alla lingua selezionata.  
  
 Ciò ha consentito alle applicazioni di elaborare valori numerici senza dover convertirli da una lingua a altra, ad esempio un utente può aprire una [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] foglio di calcolo in una localizzata in arabo [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e visualizzare i numeri in arabo, ma aprirli in versione europea di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] rappresentazione europea degli stessi numeri. Questa condizione è necessaria anche per altri simboli, quali i separatori virgola e il simbolo della percentuale, perché sono spesso associati a numeri nello stesso documento.  
  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stata mantenuta la stessa tradizione e aggiunto un ulteriore supporto a questa funzionalità che consente un maggiore controllo dell'utente sul momento e sulla modalità d'su della sostituzione. Sebbene questa funzionalità sia stata progettata per tutte le lingue, è particolarmente utile per i contenuti bidirezionali in cui la definizione delle cifre per una lingua specifica rappresenta solitamente una sfida per gli sviluppatori di applicazioni, a causa delle diverse impostazioni cultura con cui un'applicazione può essere eseguita.  
  
 La proprietà principale che controlla la sostituzione dei numeri come funziona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è il <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà di dipendenza. Il <xref:System.Windows.Media.NumberSubstitution> classe specifica come devono essere visualizzati numeri nel testo. Include tre proprietà pubbliche che ne definiscono il comportamento. Di seguito è riportato un riepilogo di tutte le proprietà.  
  
 **CultureSource:**  
  
 Questa proprietà specifica come vengono determinate le impostazioni cultura per i numeri. Accetta uno dei tre <xref:System.Windows.Media.NumberCultureSource> valori di enumerazione.  
  
-   prevalere: Sono costituito dalle impostazioni cultura del numero <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> proprietà.  
  
-   Testo: Impostazioni cultura del numero sono quelle della sequenza di testo. Nel markup, il risultato sarà `xml:lang`, o il relativo alias `Language` proprietà (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Inoltre, è il valore predefinito per le classi che derivano da <xref:System.Windows.FrameworkContentElement>. Tali classi includono <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> e così via.  
  
-   Utente: Impostazioni cultura del numero sono quelle del thread corrente. Questa proprietà è il valore predefinito per tutte le sottoclassi della <xref:System.Windows.FrameworkElement> , ad esempio <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> e <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 Il <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> proprietà viene utilizzata solo se il <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> è impostata su <xref:System.Windows.Media.NumberCultureSource.Override> e viene ignorato in caso contrario. Specifica le impostazioni cultura del numero. Valore `null`, il valore predefinito, viene interpretato come en-US.  
  
 **Substitution**:  
  
 Questa proprietà specifica il tipo di sostituzione numerica da eseguire. Accetta uno dei seguenti <xref:System.Windows.Media.NumberSubstitutionMethod> valori di enumerazione.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Il metodo di sostituzione viene determinato in base a impostazioni cultura del numero <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> proprietà. Questa è l'impostazione predefinita.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Se le impostazioni cultura del numero sono in arabo o in Farsi, specifica che le cifre dipendono dal contesto.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>: I numeri sono sempre sottoposti a rendering come cifre europee.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: I numeri vengono sottoposti a rendering utilizzando le cifre nazionali per le impostazioni cultura dei numeri, come specificato dalle impostazioni cultura <xref:System.Globalization.CultureInfo.NumberFormat%2A>.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Numeri vengono sottoposti a rendering utilizzando le cifre tradizionali per le impostazioni cultura dei numeri. Per la maggior parte delle impostazioni cultura, questo è lo stesso come <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Tuttavia, <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> comporta cifre latine per alcune impostazioni cultura arabe, mentre questo valore in cifre arabe per tutte le impostazioni cultura arabe.  
  
 Cosa significano questi valori per uno sviluppatore di contenuti bidirezionali? Nella maggior parte dei casi, lo sviluppatore deve solo definire <xref:System.Windows.FlowDirection> e la lingua della ognuno testuale [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento, ad esempio `Language="ar-SA"` e il <xref:System.Windows.Media.NumberSubstitution> per la logica esegue automaticamente la visualizzazione dei numeri in base alla corretta [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Nell'esempio seguente viene illustrato come utilizzare numeri arabi e inglesi in un' [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dell'applicazione in esecuzione in una versione araba di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 La figura seguente mostra l'output dell'esempio precedente, se si esegue una versione araba di Windows con i numeri arabi e inglesi visualizzati:

 ![Figura che illustra i numeri arabi e inglesi.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)  
  
 Il <xref:System.Windows.FlowDirection> era importante in questo caso, poiché l'impostazione di <xref:System.Windows.FlowDirection> a <xref:System.Windows.FlowDirection.LeftToRight> avrebbe prodotto cifre europee. Le sezioni seguenti descrivono come ottenere una visualizzazione unificata delle cifre in tutto il documento. Se l'esempio non viene eseguito nella versione araba di Windows, tutte le cifre vengono visualizzate come cifre europee.  
  
 **Definizione delle regole di sostituzione**  
  
 In un'applicazione reale, è necessario impostare l'oggetto Language a livello di codice. Ad esempio, si desidera impostare il `xml:lang` attributo è uguale a quello usato per il sistema [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], oppure modificare la lingua in base allo stato dell'applicazione.  
  
 Se si desidera apportare modifiche di base sullo stato dell'applicazione, usare altre funzionalità fornite da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 In primo luogo, impostare il componente di applicazione `NumberSubstitution.CultureSource="Text"`. Con questa impostazione assicura che le impostazioni non sono concessi dal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per gli elementi di testo con "Utente" come valore predefinito, ad esempio <xref:System.Windows.Controls.TextBlock>.  
  
Ad esempio:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

Nel corrispondente C# il codice, impostare la `Language` proprietà, ad esempio, per `"ar-SA"`.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Se è necessario impostare il `Language` proprietà alla lingua della UI dell'utente corrente, utilizzare il codice seguente.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> rappresenta le impostazioni cultura correnti utilizzata dal thread corrente in fase di esecuzione.  
  
 Il finale [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] esempio dovrebbe essere simile all'esempio seguente.  
  
 [!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Il finale C# esempio dovrebbe essere simile al seguente.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 La figura seguente mostra l'aspetto della finestra per entrambi linguaggio di programmazione, visualizzare i numeri arabi:
     
 ![Immagine che visualizza i numeri arabi.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)  
  
 **Uso della proprietà Substitution**  
  
 Funzionamento della sostituzione numerica in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dipende dalla lingua dell'elemento di testo e il relativo <xref:System.Windows.FlowDirection>. Se il <xref:System.Windows.FlowDirection> da sinistra a destra, quindi vengono visualizzate le cifre europee. Tuttavia se è preceduto da un testo arabo o la lingua è impostata su "ar" e il <xref:System.Windows.FlowDirection> è <xref:System.Windows.FlowDirection.RightToLeft>, vengono invece visualizzate le cifre arabe.  
  
 In alcuni casi, tuttavia, è possibile creare un'applicazione unificata usando, ad esempio, le cifre europee per tutti gli utenti Oppure cifre arabe nelle <xref:System.Windows.Documents.Table> celle con uno specifico <xref:System.Windows.Style>. Un modo semplice per eseguire operazioni che utilizza il <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà.  
  
 Nell'esempio seguente, il primo <xref:System.Windows.Controls.TextBlock> non dispone di <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà è impostata, pertanto l'algoritmo Visualizza le cifre arabe, come previsto. Tuttavia nel secondo <xref:System.Windows.Controls.TextBlock>, la sostituzione è impostata su European, si esegue l'override della sostituzione predefinita per i numeri arabi e vengono visualizzate le cifre europee.  
  
 [!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
