---
title: Cenni preliminari sulle funzionalità bidirezionali di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 4c3a39c1d1252951b0847638809c9e1e6be2a21e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856186"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Cenni preliminari sulle funzionalità bidirezionali di WPF

Diversamente da qualsiasi altra piattaforma di sviluppo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , dispone di molte funzionalità che supportano lo sviluppo rapido di contenuto bidirezionale, ad esempio, i dati combinati da sinistra a destra e da destra a sinistra nello stesso documento. Allo stesso tempo, crea [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'esperienza ottimale per gli utenti che richiedono funzionalità bidirezionali, ad esempio gli utenti in lingua araba ed ebraica.

Le sezioni seguenti illustrano molte funzionalità bidirezionali con i relativi esempi in cui viene descritto come ottenere la migliore visualizzazione di contenuto bidirezionale. La maggior parte degli esempi [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]utilizza, sebbene sia possibile applicare facilmente i concetti C# a o al codice di Microsoft Visual Basic.

<a name="FlowDirection"></a>

## <a name="flowdirection"></a>FlowDirection

La proprietà di base che definisce la direzione del flusso del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto in <xref:System.Windows.FrameworkElement.FlowDirection%2A>un'applicazione è. Questa proprietà può essere impostata su uno dei due valori di enumerazione <xref:System.Windows.FlowDirection.LeftToRight> , <xref:System.Windows.FlowDirection.RightToLeft>o. La proprietà è disponibile per tutti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli elementi che ereditano da. <xref:System.Windows.FrameworkElement>

Negli esempi seguenti viene impostata la direzione del flusso <xref:System.Windows.Controls.TextBox> di un elemento.

**Direzione di flusso da sinistra a destra**

[!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]

**Direzione di flusso da destra a sinistra**

[!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]

La figura seguente illustra il rendering del codice precedente.

![Immagine che illustra le diverse direzioni di flusso.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)

Un elemento all'interno [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] di un albero erediterà <xref:System.Windows.FrameworkElement.FlowDirection%2A> l'oggetto dal relativo contenitore. Nell'esempio seguente l'oggetto <xref:System.Windows.Controls.TextBlock> si trova all'interno di un <xref:System.Windows.Controls.Grid>oggetto, che risiede in <xref:System.Windows.Window>un oggetto. L'impostazione <xref:System.Windows.FrameworkElement.FlowDirection%2A> del per <xref:System.Windows.Window> implical'<xref:System.Windows.Controls.TextBlock> impostazione anche per e.<xref:System.Windows.Controls.Grid>

Nell'esempio seguente viene illustrata l'impostazione <xref:System.Windows.FrameworkElement.FlowDirection%2A>di.

[!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]

Il primo livello <xref:System.Windows.Window> ha un <xref:System.Windows.FlowDirection.RightToLeft>oggetto <xref:System.Windows.FlowDirection>, quindi tutti gli elementi in esso contenuti ereditano <xref:System.Windows.FrameworkElement.FlowDirection%2A>anche lo stesso. Affinché un elemento esegua l'override <xref:System.Windows.FrameworkElement.FlowDirection%2A> di un oggetto specificato, deve aggiungere una modifica della direzione <xref:System.Windows.Controls.TextBlock> esplicita, ad esempio la seconda <xref:System.Windows.FlowDirection.LeftToRight>nell'esempio precedente, che cambia in. Quando non <xref:System.Windows.FrameworkElement.FlowDirection%2A> viene definito alcun oggetto, <xref:System.Windows.FlowDirection.LeftToRight> viene applicato il valore predefinito.

Il grafico seguente mostra l'output dell'esempio precedente:

![Immagine che illustra la modifica della direzione del flusso esplicita.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)

<a name="FlowDocument"></a>

## <a name="flowdocument"></a>FlowDocument

Molte piattaforme di sviluppo, ad esempio [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] HTML e Java, offrono supporto speciale per lo sviluppo di contenuto bidirezionale. I linguaggi di markup, ad esempio HTML, assegnano ai writer di contenuti il markup necessario per visualizzare il testo in qualsiasi direzione, ad esempio il tag HTML 4,0, "dir", che accetta "RTL" o "ltr" come valori. Questo tag è simile alla proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> , ma la <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà funziona in modo più avanzato per il layout del contenuto testuale e può essere usata per contenuti diversi dal testo.

In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un <xref:System.Windows.Documents.FlowDocument> è un elemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] versatile che può ospitare una combinazione di testo, tabelle, immagini e altri elementi. Gli esempi nelle sezioni seguenti usano questo elemento.

L'aggiunta di testo <xref:System.Windows.Documents.FlowDocument> a un oggetto può essere eseguita in modo più che unidirezionale. Un modo semplice per eseguire questa operazione è tramite <xref:System.Windows.Documents.Paragraph> un che è un elemento a livello di blocco usato per raggruppare contenuto come testo. Per aggiungere testo a elementi a livello di riga, gli esempi <xref:System.Windows.Documents.Span> utilizzano <xref:System.Windows.Documents.Run>e. <xref:System.Windows.Documents.Span>è un elemento di contenuto del flusso di livello inline usato per raggruppare altri elementi inline, <xref:System.Windows.Documents.Run> mentre un oggetto è un elemento di contenuto del flusso a livello in linea destinato a contenere un'esecuzione di testo non formattato. Un <xref:System.Windows.Documents.Span> oggetto può contenere <xref:System.Windows.Documents.Run> più elementi.

Il primo documento di esempio contiene un documento con un numero di nomi di condivisione di rete; ad esempio `\\server1\folder\file.ext`. Indipendentemente dal fatto che questo collegamento di rete si trovi in un documento in arabo o in inglese, si vuole che venga sempre visualizzato nello stesso modo. Il grafico seguente illustra l'uso dell'elemento span e Mostra il collegamento in un documento <xref:System.Windows.FlowDirection.RightToLeft> arabo:

![Immagine che illustra l'uso dell'elemento span.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")

Poiché il testo è <xref:System.Windows.FlowDirection.RightToLeft>, tutti i caratteri speciali, ad esempio "\\", separano il testo in un ordine da destra a sinistra. Ciò comporta che il collegamento non venga visualizzato nell'ordine corretto, pertanto per risolvere il problema, il testo deve essere incorporato per mantenere un <xref:System.Windows.Documents.Run> <xref:System.Windows.FlowDirection.LeftToRight>flusso separato. Anziché avere un separato <xref:System.Windows.Documents.Run> per ogni lingua, un modo migliore per risolvere il problema consiste nell'incorporare il testo in inglese usato meno di frequente in un arabo <xref:System.Windows.Documents.Span>più grande.

Nell'immagine seguente viene illustrato questo problema utilizzando l'elemento Run incorporato in un elemento span:

![Immagine che illustra l'elemento Run incorporato in un elemento span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)

Nell'esempio seguente viene illustrato <xref:System.Windows.Documents.Run> l' <xref:System.Windows.Documents.Span> utilizzo degli elementi e nei documenti.

[!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]

<a name="SpanElements"></a>

## <a name="span-elements"></a>Elementi Span

L' <xref:System.Windows.Documents.Span> elemento funziona come separatore di limiti tra testi con direzioni di flusso diverse.  Anche <xref:System.Windows.Documents.Span> gli elementi con la stessa direzione del flusso sono considerati con ambiti bidirezionali diversi <xref:System.Windows.FlowDirection>, il che significa <xref:System.Windows.Documents.Span> che gli elementi vengono ordinati nell'oggetto del contenitore, solo il contenuto <xref:System.Windows.Documents.Span> all'interno dell'elemento segue il <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span>di.

Il grafico seguente mostra la direzione del flusso di <xref:System.Windows.Controls.TextBlock> diversi elementi.

![Immagine che illustra i blocchi di testo con direzioni di flusso diverse.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)

Nell'esempio seguente viene illustrato come utilizzare gli <xref:System.Windows.Documents.Span> elementi <xref:System.Windows.Documents.Run> e per produrre i risultati mostrati nel grafico precedente.

[!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]

<xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span> Negli elementi dell'esempio, gli <xref:System.Windows.Documents.Span> elementi sono disposti in base alla proprietà degli elementi padre, ma il testo all'interno di ogni elemento fluisce in base al relativo oggetto. <xref:System.Windows.Controls.TextBlock> Questa condizione può essere applicata all'alfabeto latino e arabo oppure a qualsiasi altra lingua.

### <a name="adding-xmllang"></a>Aggiunta di xml:lang

Nell'immagine seguente viene illustrato un altro esempio in `"200.0+21.4=221.4"`cui vengono utilizzati numeri e espressioni aritmetiche, ad esempio. Si noti che è <xref:System.Windows.FlowDirection> impostato solo l'oggetto.

![Grafico che Visualizza i numeri utilizzando solo FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)

Gli utenti di questa applicazione saranno delusi dall'output, anche se <xref:System.Windows.FlowDirection> è corretto, i numeri non sono deformati come numeri arabi.

Gli elementi XAML possono includere [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] un attributo`xml:lang`() che definisce la lingua di ogni elemento. XAML supporta inoltre un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] principio del linguaggio `xml:lang` in base al quale i valori applicati agli elementi padre nell'albero vengono utilizzati dagli elementi figlio. Nell'esempio precedente, dal momento che non è stato definito un linguaggio <xref:System.Windows.Documents.Run> per l'elemento o uno dei relativi elementi di primo livello `xml:lang` , viene `en-US` usato il valore predefinito, ovvero per XAML. L'algoritmo di shaping dei numeri [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] interni di seleziona i numeri nella lingua corrispondente, in questo caso l'inglese. Per rendere corretto `xml:lang` il rendering dei numeri arabi, è necessario impostare.

Il grafico seguente mostra l'esempio con `xml:lang` added.

![Immagine che illustra i numeri arabi che scorrono da destra a sinistra.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)

Nell'esempio seguente viene `xml:lang` aggiunto all'applicazione.

[!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]

Tenere presente che molti linguaggi hanno valori `xml:lang` diversi a seconda dell'area di destinazione, ad esempio, `"ar-SA"` e `"ar-EG"` rappresentano due varianti di arabo. Negli esempi precedenti viene illustrato che è necessario definire i `xml:lang` valori e. <xref:System.Windows.FlowDirection>

<a name="FlowDirectionNontext"></a>

## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementi non di testo

<xref:System.Windows.FlowDirection>definisce non solo il modo in cui il testo fluisce in un elemento testuale, ma anche la direzione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di flusso di quasi tutti gli altri elementi. Il grafico seguente mostra un <xref:System.Windows.Controls.ToolBar> oggetto che usa un <xref:System.Windows.Media.LinearGradientBrush> oggetto orizzontale per creare lo sfondo con una sfumatura da sinistra a destra.

![Grafico che mostra una barra degli strumenti con una sfumatura da sinistra a destra.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)

Dopo aver impostato <xref:System.Windows.FlowDirection> su <xref:System.Windows.FlowDirection.RightToLeft>, non solo i <xref:System.Windows.Controls.ToolBar> pulsanti vengono disposti da destra a sinistra, ma anche il <xref:System.Windows.Media.LinearGradientBrush> riallinea gli offset da destra a sinistra.

Nell'immagine seguente viene illustrato il riallineamento del <xref:System.Windows.Media.LinearGradientBrush>.

![Immagine che mostra una barra degli strumenti con una sfumatura da destra a sinistra.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)

Nell'esempio seguente viene disegnato <xref:System.Windows.FlowDirection.RightToLeft>un oggetto. <xref:System.Windows.Controls.ToolBar> Per estrarlo da sinistra a destra, rimuovere l' <xref:System.Windows.FlowDirection> attributo <xref:System.Windows.Controls.ToolBar>in.

[!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]

<a name="FlowDirectionExceptions"></a>

### <a name="flowdirection-exceptions"></a>Eccezioni di FlowDirection

Esistono alcuni casi in cui <xref:System.Windows.FlowDirection> non si comporta come previsto. In questa sezione vengono illustrate due di queste eccezioni.

**Immagine**

Un <xref:System.Windows.Controls.Image> oggetto rappresenta un controllo che visualizza un'immagine. In [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] può essere utilizzato con una <xref:System.Windows.Controls.Image.Source%2A> proprietà <xref:System.Windows.Controls.Image> che definisce l'oggetto [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] di da visualizzare.

A differenza <xref:System.Windows.FlowDirection> di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] altri elementi, <xref:System.Windows.Controls.Image> un oggetto non eredita dal contenitore. Tuttavia, se l' <xref:System.Windows.FlowDirection> oggetto viene impostato in modo <xref:System.Windows.FlowDirection.RightToLeft>esplicito <xref:System.Windows.Controls.Image> su, viene visualizzato un oggetto capovolto orizzontalmente. Questa condizione viene implementata come una funzionalità utile per gli sviluppatori di contenuti bidirezionali, perché in alcuni casi il capovolgimento in senso orizzontale dell'immagine genera l'effetto desiderato.

Il grafico seguente mostra un capovolto <xref:System.Windows.Controls.Image>.

![Immagine che illustra un'immagine capovolta.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)

Nell'esempio seguente viene illustrato che <xref:System.Windows.Controls.Image> l'oggetto non è <xref:System.Windows.FlowDirection> in grado <xref:System.Windows.Controls.StackPanel> di ereditare dall'oggetto che lo contiene.

> [!NOTE]
> È necessario disporre di un file denominato **ms_logo. jpg** in C:\ per eseguire questo esempio.

[!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]

> [!NOTE]
> Incluso nei file di download è un file **ms_logo. jpg** . Nel codice si presuppone che il file con estensione jpg non si trovi all'interno del progetto ma in un'altra posizione nell'unità C:\. È necessario copiare il file con estensione jpg dai file di progetto nell'unità C:\ oppure modificare il codice affinché la ricerca venga eseguita all'interno del progetto. A tale scopo, `Source="file://c:/ms_logo.jpg"` modificare `Source="ms_logo.jpg"`in.

**Percorsi**

Oltre a un <xref:System.Windows.Controls.Image>, un altro elemento interessante è <xref:System.Windows.Shapes.Path>. Path è un oggetto che consente di disegnare una serie di righe e curve collegate. Si comporta in modo analogo a un <xref:System.Windows.Controls.Image> oggetto <xref:System.Windows.FlowDirection>, ad esempio <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> è un mirror orizzontale di <xref:System.Windows.FlowDirection.LeftToRight> quello corrispondente. Tuttavia, a differenza di <xref:System.Windows.Controls.Image>un <xref:System.Windows.Shapes.Path> oggetto, <xref:System.Windows.FlowDirection> eredita il relativo dal contenitore e non è necessario specificarlo in modo esplicito.

L'esempio seguente disegna una freccia semplice con 3 linee. La prima freccia eredita la <xref:System.Windows.FlowDirection.RightToLeft> direzione del flusso <xref:System.Windows.Controls.StackPanel> da in modo che i punti di inizio e di fine vengano misurati da una radice sul lato destro. La seconda freccia che ha un esplicito <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> inizia anche sul lato destro. Tuttavia, la radice iniziale della terza freccia è collocata sul lato sinistro. Per ulteriori informazioni sul disegno, <xref:System.Windows.Media.LineGeometry> vedere <xref:System.Windows.Media.GeometryGroup>e.

[!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]

Il grafico seguente mostra l'output dell'esempio precedente con le frecce disegnate usando `Path` l'elemento:

![Immagine che illustra le frecce disegnate usando l'elemento Path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)

E sono due esempi di come [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] utilizza <xref:System.Windows.FlowDirection>. <xref:System.Windows.Shapes.Path> <xref:System.Windows.Controls.Image> Oltre a definire [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] gli elementi in una direzione specifica all'interno di <xref:System.Windows.FlowDirection> un contenitore, può essere <xref:System.Windows.Controls.InkPresenter> utilizzato con elementi quali il rendering dell'input penna su <xref:System.Windows.Media.LinearGradientBrush>una <xref:System.Windows.Media.RadialGradientBrush>superficie,,. Ogni volta che è necessario un comportamento da destra a sinistra per il contenuto che simula un comportamento da sinistra a destra o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce tale funzionalità.

<a name="NumberSubstitution"></a>

## <a name="number-substitution"></a>Sostituzione numerica

In passato, Windows supportava la sostituzione dei numeri consentendo la rappresentazione di forme culturali diverse per le stesse cifre mantenendo l'archiviazione interna di queste cifre unificate tra impostazioni locali diverse, ad esempio i numeri vengono archiviati nel relativo valori esadecimali ben noti, 0x40, 0x41, ma visualizzati in base alla lingua selezionata.

In questo modo le applicazioni possono elaborare i valori numerici senza la necessità di convertirli da una lingua all'altra. ad esempio, un utente [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] può aprire un foglio di calcolo in una finestra araba localizzata e visualizzare i numeri con la forma araba, ma aprirlo in un Versione europea di Windows e vedere rappresentazione europea degli stessi numeri. Questa condizione è necessaria anche per altri simboli, quali i separatori virgola e il simbolo della percentuale, perché sono spesso associati a numeri nello stesso documento.

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stata mantenuta la stessa tradizione e aggiunto un ulteriore supporto a questa funzionalità che consente un maggiore controllo dell'utente sul momento e sulla modalità d'su della sostituzione. Sebbene questa funzionalità sia stata progettata per tutte le lingue, è particolarmente utile per i contenuti bidirezionali in cui la definizione delle cifre per una lingua specifica rappresenta solitamente una sfida per gli sviluppatori di applicazioni, a causa delle diverse impostazioni cultura con cui un'applicazione può essere eseguita.

La proprietà di base che controlla il funzionamento della [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sostituzione dei <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> numeri in è la proprietà di dipendenza. La <xref:System.Windows.Media.NumberSubstitution> classe specifica il modo in cui devono essere visualizzati i numeri nel testo. Include tre proprietà pubbliche che ne definiscono il comportamento. Di seguito è riportato un riepilogo di tutte le proprietà.

**CultureSource:**

Questa proprietà specifica come vengono determinate le impostazioni cultura per i numeri. Accetta uno dei tre <xref:System.Windows.Media.NumberCultureSource> valori di enumerazione.

- Override Le impostazioni cultura del numero <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> sono quelle della proprietà.

- testo Le impostazioni cultura del numero sono le impostazioni cultura della sequenza di testo. Nel `xml:lang`markup, si tratta di o della relativa proprietà alias `Language` (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Inoltre, è l'impostazione predefinita per le classi che derivano da <xref:System.Windows.FrameworkContentElement>. Tali classi includono <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType> <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, ecosìvia.<xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>

- Utente: Le impostazioni cultura del numero sono le impostazioni cultura del thread corrente. Questa proprietà è l'impostazione predefinita per tutte le sottoclassi <xref:System.Windows.FrameworkElement> di <xref:System.Windows.Controls.Page>, ad <xref:System.Windows.Window> esempio <xref:System.Windows.Controls.TextBlock>, e.

**CultureOverride**:

La <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> proprietà viene utilizzata solo se la <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> proprietà è impostata su <xref:System.Windows.Media.NumberCultureSource.Override> e viene ignorata in caso contrario. Specifica le impostazioni cultura del numero. `null`Il valore predefinito viene interpretato come en-US.

**Substitution**:

Questa proprietà specifica il tipo di sostituzione numerica da eseguire. Accetta uno dei seguenti <xref:System.Windows.Media.NumberSubstitutionMethod> valori di enumerazione:

- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Il metodo di <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> sostituzione viene determinato in base alla proprietà delle impostazioni cultura del numero. Questa è l'impostazione predefinita.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Se le impostazioni cultura del numero sono una lingua araba o persiana, specifica che le cifre dipendono dal contesto.

- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: I numeri vengono sempre sottoposti a rendering come cifre europee.

- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Il rendering dei numeri viene eseguito usando le cifre nazionali per le impostazioni cultura del numero, come <xref:System.Globalization.CultureInfo.NumberFormat%2A>specificato dalle impostazioni cultura.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Il rendering dei numeri viene eseguito usando le cifre tradizionali per le impostazioni cultura del numero. Per la maggior parte delle impostazioni cultura, equivale <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>a. Tuttavia, <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> restituisce cifre latine per alcune impostazioni cultura arabe, mentre questo valore genera cifre arabe per tutte le impostazioni cultura arabe.

Cosa significano questi valori per uno sviluppatore di contenuti bidirezionali? Nella maggior parte dei casi, lo sviluppatore potrebbe avere la <xref:System.Windows.FlowDirection> necessità di definire e la lingua [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di ogni elemento testuale `Language="ar-SA"` , ad <xref:System.Windows.Media.NumberSubstitution> esempio e la logica si occupa della visualizzazione dei numeri in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]base alla corretta. Nell'esempio seguente viene illustrato l'utilizzo di numeri arabi e [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] inglesi in un'applicazione in esecuzione in una versione araba di Windows.

[!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]

Il grafico seguente mostra l'output dell'esempio precedente se si esegue una versione araba di Windows con i numeri arabi e inglesi visualizzati:

![Immagine che mostra i numeri arabi e inglesi.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)

Era importante in questo caso, perché l' <xref:System.Windows.FlowDirection> impostazione di <xref:System.Windows.FlowDirection.LeftToRight> su invece avrebbe restituito cifre europee. <xref:System.Windows.FlowDirection> Le sezioni seguenti descrivono come ottenere una visualizzazione unificata delle cifre in tutto il documento. Se l'esempio non viene eseguito nella versione araba di Windows, tutte le cifre vengono visualizzate come cifre europee.

**Definizione delle regole di sostituzione**

In un'applicazione reale, è necessario impostare l'oggetto Language a livello di codice. Si desidera, ad esempio, impostare l' `xml:lang` attributo in modo che corrisponda a quello utilizzato dal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]sistema oppure modificare la lingua in base allo stato dell'applicazione.

Se si desidera apportare modifiche in base allo stato dell'applicazione, utilizzare altre funzionalità fornite da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

Per prima cosa, impostare l'oggetto `NumberSubstitution.CultureSource="Text"`del componente dell'applicazione. L'utilizzo di questa impostazione garantisce che le impostazioni non provengano [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da per gli elementi di testo con "User" come valore predefinito, <xref:System.Windows.Controls.TextBlock>ad esempio.

Ad esempio:

```xaml
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

Nel codice corrispondente C# , impostare la `Language` proprietà, ad esempio su `"ar-SA"`.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Se è necessario impostare la `Language` proprietà sulla lingua dell'interfaccia utente dell'utente corrente, usare il codice seguente.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>rappresenta le impostazioni cultura correnti utilizzate dal thread corrente in fase di esecuzione.

L'esempio [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] finale dovrebbe essere simile all'esempio seguente.

[!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]

L'esempio C# finale dovrebbe essere simile al seguente.

[!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]

Il grafico seguente mostra l'aspetto della finestra per entrambi i linguaggi di programmazione, visualizzando i numeri arabi:

![Immagine che Visualizza i numeri arabi.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)

**Uso della proprietà Substitution**

Il modo in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] cui funziona la sostituzione dei numeri dipende dal linguaggio dell'elemento di testo e dalla <xref:System.Windows.FlowDirection>relativa. Se l' <xref:System.Windows.FlowDirection> oggetto è da sinistra a destra, viene eseguito il rendering delle cifre europee. Tuttavia, se è preceduto da testo arabo o la lingua è impostata su "AR" e l'oggetto <xref:System.Windows.FlowDirection> è <xref:System.Windows.FlowDirection.RightToLeft>, viene invece eseguito il rendering delle cifre arabe.

In alcuni casi, tuttavia, è possibile creare un'applicazione unificata usando, ad esempio, le cifre europee per tutti gli utenti O le cifre arabe <xref:System.Windows.Documents.Table> in celle con un <xref:System.Windows.Style>oggetto specifico. Un modo semplice per eseguire questa operazione consiste nell' <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> usare la proprietà.

Nell'esempio seguente, il primo <xref:System.Windows.Controls.TextBlock> non dispone della <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà impostata, quindi l'algoritmo Visualizza le cifre arabe come previsto. Nel secondo <xref:System.Windows.Controls.TextBlock>caso, tuttavia, la sostituzione è impostata su European override della sostituzione predefinita per i numeri arabi e vengono visualizzate le cifre europee.

[!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
