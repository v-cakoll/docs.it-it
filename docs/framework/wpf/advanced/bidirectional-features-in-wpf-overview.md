---
title: Cenni preliminari sulle funzionalità bidirezionali di WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 19fb15a6310eba19792d7bd0744c2ae87f47c6fa
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740419"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Cenni preliminari sulle funzionalità bidirezionali di WPF

Diversamente da qualsiasi altra piattaforma di sviluppo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone di molte funzionalità che supportano lo sviluppo rapido di contenuti bidirezionali, ad esempio, i dati misti da sinistra a destra e da destra a sinistra nello stesso documento. Allo stesso tempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea un'esperienza ottimale per gli utenti che richiedono funzionalità bidirezionali, ad esempio gli utenti in lingua araba ed ebraica.

Le sezioni seguenti illustrano molte funzionalità bidirezionali con i relativi esempi in cui viene descritto come ottenere la migliore visualizzazione di contenuto bidirezionale. La maggior parte degli esempi usa XAML, sebbene sia possibile applicare facilmente i concetti C# a o al codice di Microsoft Visual Basic.

<a name="FlowDirection"></a>

## <a name="flowdirection"></a>FlowDirection

La proprietà di base che definisce la direzione del flusso del contenuto in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Questa proprietà può essere impostata su uno dei due valori di enumerazione, <xref:System.Windows.FlowDirection.LeftToRight> o <xref:System.Windows.FlowDirection.RightToLeft>. La proprietà è disponibile per tutti gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che ereditano da <xref:System.Windows.FrameworkElement>.

Negli esempi seguenti viene impostata la direzione del flusso di un elemento <xref:System.Windows.Controls.TextBox>.

**Direzione di flusso da sinistra a destra**

[!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]

**Direzione di flusso da destra a sinistra**

[!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]

La figura seguente illustra il rendering del codice precedente.

![Immagine che illustra le diverse direzioni di flusso.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)

Un elemento all'interno di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] albero erediterà l'<xref:System.Windows.FrameworkElement.FlowDirection%2A> dal relativo contenitore. Nell'esempio seguente, il <xref:System.Windows.Controls.TextBlock> si trova all'interno di un <xref:System.Windows.Controls.Grid>, che risiede in un <xref:System.Windows.Window>. L'impostazione del <xref:System.Windows.FrameworkElement.FlowDirection%2A> per il <xref:System.Windows.Window> implica la relativa impostazione anche per il <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.TextBlock>.

Nell'esempio seguente viene illustrata l'impostazione <xref:System.Windows.FrameworkElement.FlowDirection%2A>.

[!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]

Il <xref:System.Windows.Window> di primo livello ha un <xref:System.Windows.FlowDirection>di <xref:System.Windows.FlowDirection.RightToLeft>, quindi tutti gli elementi in esso contenuti ereditano anche lo stesso <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Affinché un elemento esegua l'override di un <xref:System.Windows.FrameworkElement.FlowDirection%2A> specificato, deve aggiungere una modifica della direzione esplicita, ad esempio la seconda <xref:System.Windows.Controls.TextBlock> nell'esempio precedente, che cambia in <xref:System.Windows.FlowDirection.LeftToRight>. Quando non viene definito alcun <xref:System.Windows.FrameworkElement.FlowDirection%2A>, viene applicata la <xref:System.Windows.FlowDirection.LeftToRight> predefinita.

Il grafico seguente mostra l'output dell'esempio precedente:

![Immagine che illustra la modifica della direzione del flusso esplicita.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)

<a name="FlowDocument"></a>

## <a name="flowdocument"></a>FlowDocument

Molte piattaforme di sviluppo, ad esempio HTML, Win32 e Java forniscono supporto speciale per lo sviluppo di contenuto bidirezionale. I linguaggi di markup, ad esempio HTML, assegnano ai writer di contenuti il markup necessario per visualizzare il testo in qualsiasi direzione, ad esempio il tag HTML 4,0, "dir", che accetta "RTL" o "ltr" come valori. Questo tag è simile alla proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A>, ma la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> funziona in modo più avanzato per il layout del contenuto testuale e può essere usata per contenuti diversi dal testo.

In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], una <xref:System.Windows.Documents.FlowDocument> è un elemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] versatile che può ospitare una combinazione di testo, tabelle, immagini e altri elementi. Gli esempi nelle sezioni seguenti usano questo elemento.

L'aggiunta di testo a un <xref:System.Windows.Documents.FlowDocument> può essere eseguita in un modo più approfondito. Un modo semplice per eseguire questa operazione consiste nell'utilizzare un <xref:System.Windows.Documents.Paragraph> che è un elemento a livello di blocco utilizzato per raggruppare contenuto come testo. Per aggiungere testo a elementi a livello di riga, gli esempi utilizzano <xref:System.Windows.Documents.Span> e <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span> è un elemento di contenuto del flusso di livello inline usato per raggruppare altri elementi inline, mentre una <xref:System.Windows.Documents.Run> è un elemento di contenuto del flusso di livello inline destinato a contenere un'esecuzione di testo non formattato. Un <xref:System.Windows.Documents.Span> può contenere più elementi <xref:System.Windows.Documents.Run>.

Il primo documento di esempio contiene un documento con un numero di nomi di condivisione di rete; ad esempio `\\server1\folder\file.ext`. Indipendentemente dal fatto che questo collegamento di rete si trovi in un documento in arabo o in inglese, si vuole che venga sempre visualizzato nello stesso modo. Il grafico seguente illustra l'uso dell'elemento span e Mostra il collegamento in un documento di <xref:System.Windows.FlowDirection.RightToLeft> arabo:

![Immagine che illustra l'uso dell'elemento span.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")

Poiché il testo è <xref:System.Windows.FlowDirection.RightToLeft>, tutti i caratteri speciali, ad esempio "\\", separano il testo in un ordine da destra a sinistra. Ciò comporta che il collegamento non venga visualizzato nell'ordine corretto, pertanto per risolvere il problema, è necessario incorporare il testo per mantenere un flusso di <xref:System.Windows.Documents.Run> separato <xref:System.Windows.FlowDirection.LeftToRight>. Invece di avere un <xref:System.Windows.Documents.Run> separato per ogni lingua, un modo migliore per risolvere il problema consiste nell'incorporare il testo in lingua inglese usato meno di frequente in una <xref:System.Windows.Documents.Span>araba più grande.

Nell'immagine seguente viene illustrato questo problema utilizzando l'elemento Run incorporato in un elemento span:

![Immagine che illustra l'elemento Run incorporato in un elemento span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)

Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Windows.Documents.Run> e <xref:System.Windows.Documents.Span> elementi nei documenti.

[!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]

<a name="SpanElements"></a>

## <a name="span-elements"></a>Elementi Span

L'elemento <xref:System.Windows.Documents.Span> funziona come separatore di limiti tra testi con direzioni di flusso diverse.  Anche <xref:System.Windows.Documents.Span> elementi con la stessa direzione del flusso sono considerati con ambiti bidirezionali diversi, il che significa che gli elementi <xref:System.Windows.Documents.Span> sono ordinati nel <xref:System.Windows.FlowDirection>del contenitore, solo il contenuto all'interno dell'elemento <xref:System.Windows.Documents.Span> segue il <xref:System.Windows.FlowDirection> del <xref:System.Windows.Documents.Span>.

Il grafico seguente mostra la direzione del flusso di diversi elementi <xref:System.Windows.Controls.TextBlock>.

![Immagine che illustra i blocchi di testo con direzioni di flusso diverse.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)

Nell'esempio seguente viene illustrato come utilizzare gli elementi <xref:System.Windows.Documents.Span> e <xref:System.Windows.Documents.Run> per produrre i risultati mostrati nel grafico precedente.

[!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]

Negli elementi <xref:System.Windows.Controls.TextBlock> dell'esempio, gli elementi <xref:System.Windows.Documents.Span> sono disposti in base alla <xref:System.Windows.FlowDirection> degli elementi padre, ma il testo all'interno di ogni <xref:System.Windows.Documents.Span> elemento viene trasmesso in base alla propria <xref:System.Windows.FlowDirection>. Questa condizione può essere applicata all'alfabeto latino e arabo oppure a qualsiasi altra lingua.

### <a name="adding-xmllang"></a>Aggiunta di xml:lang

Nell'immagine seguente viene illustrato un altro esempio in cui vengono utilizzati numeri e espressioni aritmetiche, ad esempio `"200.0+21.4=221.4"`. Si noti che è impostata solo la <xref:System.Windows.FlowDirection>.

![Grafico che Visualizza i numeri utilizzando solo FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)

Gli utenti di questa applicazione rimarranno delusi dall'output, anche se la <xref:System.Windows.FlowDirection> è corretta, i numeri non sono deformati come numeri arabi.

Gli elementi XAML possono includere un attributo XML (`xml:lang`) che definisce la lingua di ogni elemento. XAML supporta inoltre un principio del linguaggio XML in base al quale i valori `xml:lang` applicati agli elementi padre nell'albero vengono utilizzati dagli elementi figlio. Nell'esempio precedente, dal momento che non è stata definita una lingua per l'elemento <xref:System.Windows.Documents.Run> o uno degli elementi di primo livello, è stato usato il `xml:lang` predefinito, `en-US` per XAML. L'algoritmo di shaping dei numeri interni di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] seleziona i numeri nella lingua corrispondente, in questo caso l'inglese. Per rendere il rendering dei numeri arabi correttamente `xml:lang` necessario impostare.

Il grafico seguente mostra l'esempio con `xml:lang` aggiunto.

![Immagine che illustra i numeri arabi che scorrono da destra a sinistra.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)

Nell'esempio seguente viene aggiunto `xml:lang` all'applicazione.

[!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]

Tenere presente che molti linguaggi hanno valori `xml:lang` diversi a seconda dell'area di destinazione, ad esempio `"ar-SA"` e `"ar-EG"` rappresentano due varianti di arabo. Negli esempi precedenti viene illustrato che è necessario definire i valori `xml:lang` e <xref:System.Windows.FlowDirection>.

<a name="FlowDirectionNontext"></a>

## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementi non di testo

<xref:System.Windows.FlowDirection> definisce non solo il modo in cui il testo fluisce in un elemento testuale, ma anche la direzione di flusso di quasi tutti gli altri elementi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Nell'immagine seguente viene illustrato un <xref:System.Windows.Controls.ToolBar> che utilizza una <xref:System.Windows.Media.LinearGradientBrush> orizzontale per creare lo sfondo con una sfumatura da sinistra a destra.

![Grafico che mostra una barra degli strumenti con una sfumatura da sinistra a destra.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)

Dopo aver impostato il <xref:System.Windows.FlowDirection> su <xref:System.Windows.FlowDirection.RightToLeft>, non solo i pulsanti <xref:System.Windows.Controls.ToolBar> vengono disposti da destra a sinistra, ma anche il <xref:System.Windows.Media.LinearGradientBrush> riallinea gli offset per il flusso da destra a sinistra.

Il grafico seguente illustra il riallineamento del <xref:System.Windows.Media.LinearGradientBrush>.

![Immagine che mostra una barra degli strumenti con una sfumatura da destra a sinistra.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)

Nell'esempio seguente viene disegnato un <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.Controls.ToolBar>. Per estrarlo da sinistra a destra, rimuovere l'attributo <xref:System.Windows.FlowDirection> nella <xref:System.Windows.Controls.ToolBar>.

[!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]

<a name="FlowDirectionExceptions"></a>

### <a name="flowdirection-exceptions"></a>Eccezioni di FlowDirection

Esistono alcuni casi in cui <xref:System.Windows.FlowDirection> non si comporta come previsto. In questa sezione vengono illustrate due di queste eccezioni.

**Immagine**

Un <xref:System.Windows.Controls.Image> rappresenta un controllo che visualizza un'immagine. In XAML può essere usato con una proprietà <xref:System.Windows.Controls.Image.Source%2A> che definisce l'URI (Uniform Resource Identifier) dell'<xref:System.Windows.Controls.Image> da visualizzare.

A differenza di altri elementi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], un <xref:System.Windows.Controls.Image> non eredita il <xref:System.Windows.FlowDirection> dal contenitore. Tuttavia, se il <xref:System.Windows.FlowDirection> viene impostato in modo esplicito su <xref:System.Windows.FlowDirection.RightToLeft>, viene visualizzato un <xref:System.Windows.Controls.Image> capovolto orizzontalmente. Questa condizione viene implementata come una funzionalità utile per gli sviluppatori di contenuti bidirezionali, perché in alcuni casi il capovolgimento in senso orizzontale dell'immagine genera l'effetto desiderato.

Il grafico seguente mostra una <xref:System.Windows.Controls.Image>capovolta.

![Immagine che illustra un'immagine capovolta.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)

Nell'esempio seguente viene illustrato che il <xref:System.Windows.Controls.Image> non riesce a ereditare il <xref:System.Windows.FlowDirection> dal <xref:System.Windows.Controls.StackPanel> che lo contiene.

> [!NOTE]
> È necessario disporre di un file denominato **ms_logo. jpg** nella C:\ per eseguire questo esempio.

[!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]

> [!NOTE]
> Incluso nei file di download è un file **ms_logo. jpg** . Nel codice si presuppone che il file con estensione jpg non si trovi all'interno del progetto ma in un'altra posizione nell'unità C:\. È necessario copiare il file con estensione jpg dai file di progetto nell'unità C:\ oppure modificare il codice affinché la ricerca venga eseguita all'interno del progetto. A tale scopo, modificare `Source="file://c:/ms_logo.jpg"` `Source="ms_logo.jpg"`.

**Percorsi**

Oltre a una <xref:System.Windows.Controls.Image>, un altro elemento interessante è <xref:System.Windows.Shapes.Path>. Path è un oggetto che consente di disegnare una serie di righe e curve collegate. Si comporta in modo simile a un <xref:System.Windows.Controls.Image> relativo <xref:System.Windows.FlowDirection>; ad esempio, il <xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection> è un mirror orizzontale della relativa <xref:System.Windows.FlowDirection.LeftToRight> uno. Tuttavia, a differenza di un <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> eredita il <xref:System.Windows.FlowDirection> dal contenitore e non è necessario specificarlo in modo esplicito.

L'esempio seguente disegna una freccia semplice con 3 linee. La prima freccia eredita la direzione del flusso <xref:System.Windows.FlowDirection.RightToLeft> dal <xref:System.Windows.Controls.StackPanel> in modo che i punti di inizio e di fine vengano misurati dalla radice sul lato destro. La seconda freccia con un <xref:System.Windows.FlowDirection.RightToLeft>esplicito <xref:System.Windows.FlowDirection> inizia anche sul lato destro. Tuttavia, la radice iniziale della terza freccia è collocata sul lato sinistro. Per ulteriori informazioni sul disegno, vedere <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.GeometryGroup>.

[!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]

Il grafico seguente mostra l'output dell'esempio precedente con le frecce disegnate usando l'elemento `Path`:

![Immagine che illustra le frecce disegnate usando l'elemento Path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)

I <xref:System.Windows.Controls.Image> e <xref:System.Windows.Shapes.Path> sono due esempi di come [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] USA <xref:System.Windows.FlowDirection>. Oltre a definire [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi in una direzione specifica all'interno di un contenitore, è possibile utilizzare <xref:System.Windows.FlowDirection> con elementi quali <xref:System.Windows.Controls.InkPresenter> che esegue il rendering di input penna su una superficie, <xref:System.Windows.Media.LinearGradientBrush><xref:System.Windows.Media.RadialGradientBrush>. Ogni volta che è necessario un comportamento da destra a sinistra per il contenuto che simula un comportamento da sinistra a destra o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce tale funzionalità.

<a name="NumberSubstitution"></a>

## <a name="number-substitution"></a>Sostituzione numerica

In passato, Windows supportava la sostituzione dei numeri consentendo la rappresentazione di forme culturali diverse per le stesse cifre mantenendo l'archiviazione interna di queste cifre unificate tra impostazioni locali diverse, ad esempio i numeri vengono archiviati nel relativo valori esadecimali ben noti, 0x40, 0x41, ma visualizzati in base alla lingua selezionata.

In questo modo le applicazioni possono elaborare valori numerici senza la necessità di convertirli da una lingua a un'altra. ad esempio, un utente può aprire un foglio di calcolo di Microsoft Excel in una finestra araba localizzata e visualizzare i numeri con la forma araba, ma aprirlo in un Versione europea di Windows e vedere rappresentazione europea degli stessi numeri. Questa condizione è necessaria anche per altri simboli, quali i separatori virgola e il simbolo della percentuale, perché sono spesso associati a numeri nello stesso documento.

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stata mantenuta la stessa tradizione e aggiunto un ulteriore supporto a questa funzionalità che consente un maggiore controllo dell'utente sul momento e sulla modalità d'su della sostituzione. Sebbene questa funzionalità sia stata progettata per tutte le lingue, è particolarmente utile per i contenuti bidirezionali in cui la definizione delle cifre per una lingua specifica rappresenta solitamente una sfida per gli sviluppatori di applicazioni, a causa delle diverse impostazioni cultura con cui un'applicazione può essere eseguita.

La proprietà di base che controlla il funzionamento della sostituzione dei numeri in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è la proprietà di dipendenza <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>. La classe <xref:System.Windows.Media.NumberSubstitution> specifica il modo in cui devono essere visualizzati i numeri nel testo. Include tre proprietà pubbliche che ne definiscono il comportamento. Di seguito è riportato un riepilogo di ognuna delle proprietà:

**CultureSource:**

Questa proprietà specifica come vengono determinate le impostazioni cultura per i numeri. Accetta uno dei tre valori di enumerazione <xref:System.Windows.Media.NumberCultureSource>.

- Override: le impostazioni cultura del numero sono quelle della proprietà <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>.

- Text: le impostazioni cultura del numero sono quelle della sequenza di testo. Nel markup, questo sarebbe `xml:lang`o la relativa proprietà alias `Language` (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Inoltre, è l'impostazione predefinita per le classi che derivano da <xref:System.Windows.FrameworkContentElement>. Tali classi includono <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> e così via.

- User: le impostazioni cultura del numero sono quelle del thread corrente. Questa proprietà è l'impostazione predefinita per tutte le sottoclassi di <xref:System.Windows.FrameworkElement>, ad esempio <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> e <xref:System.Windows.Controls.TextBlock>.

**CultureOverride**:

La proprietà <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> viene utilizzata solo se la proprietà <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> è impostata su <xref:System.Windows.Media.NumberCultureSource.Override> e in caso contrario viene ignorata. Specifica le impostazioni cultura del numero. Il valore `null`, il valore predefinito, viene interpretato come en-US.

**Substitution**:

Questa proprietà specifica il tipo di sostituzione numerica da eseguire. Accetta uno dei valori di enumerazione <xref:System.Windows.Media.NumberSubstitutionMethod> seguenti:

- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: il metodo di sostituzione viene determinato in base alla proprietà <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> delle impostazioni cultura del numero. Questo è il valore predefinito.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: se le impostazioni cultura del numero sono una lingua araba o persiana, specifica che le cifre dipendono dal contesto.

- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: i numeri vengono sempre sottoposti a rendering come cifre europee.

- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: il rendering dei numeri viene eseguito usando le cifre nazionali per le impostazioni cultura del numero, come specificato dalle <xref:System.Globalization.CultureInfo.NumberFormat%2A>delle impostazioni cultura.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: il rendering dei numeri viene eseguito usando le cifre tradizionali per le impostazioni cultura del numero. Per la maggior parte delle impostazioni cultura, equivale a <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Tuttavia, <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> restituisce cifre latine per alcune impostazioni cultura arabe, mentre questo valore genera cifre arabe per tutte le impostazioni cultura arabe.

Cosa significano questi valori per uno sviluppatore di contenuti bidirezionali? Nella maggior parte dei casi, lo sviluppatore potrebbe avere la necessità di definire <xref:System.Windows.FlowDirection> e la lingua di ogni elemento di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] testuale, ad esempio `Language="ar-SA"` e la logica di <xref:System.Windows.Media.NumberSubstitution> si occupi di visualizzare i numeri in base alla [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]corretta. Nell'esempio seguente viene illustrato l'utilizzo di numeri arabi e inglesi in un'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] eseguita in una versione araba di Windows.

[!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]

Il grafico seguente mostra l'output dell'esempio precedente se si esegue una versione araba di Windows con i numeri arabi e inglesi visualizzati:

![Immagine che mostra i numeri arabi e inglesi.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)

Il <xref:System.Windows.FlowDirection> era importante in questo caso, perché l'impostazione della <xref:System.Windows.FlowDirection> su <xref:System.Windows.FlowDirection.LeftToRight> avrebbe dovuto restituire cifre europee. Le sezioni seguenti descrivono come ottenere una visualizzazione unificata delle cifre in tutto il documento. Se l'esempio non viene eseguito nella versione araba di Windows, tutte le cifre vengono visualizzate come cifre europee.

**Definizione delle regole di sostituzione**

In un'applicazione reale, è necessario impostare l'oggetto Language a livello di codice. Si desidera, ad esempio, impostare l'attributo `xml:lang` in modo che corrisponda a quello utilizzato dal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]del sistema oppure modificare la lingua in base allo stato dell'applicazione.

Se si desidera apportare modifiche in base allo stato dell'applicazione, utilizzare altre funzionalità fornite da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

Per prima cosa, impostare la `NumberSubstitution.CultureSource="Text"`del componente dell'applicazione. L'uso di questa impostazione garantisce che le impostazioni non provengano dal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per gli elementi di testo con "User" come impostazione predefinita, ad esempio <xref:System.Windows.Controls.TextBlock>.

Ad esempio:

```xaml
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

Nel codice corrispondente C# , impostare la proprietà `Language`, ad esempio, su `"ar-SA"`.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Se è necessario impostare la proprietà `Language` sulla lingua dell'interfaccia utente dell'utente corrente, usare il codice seguente.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> rappresenta le impostazioni cultura correnti utilizzate dal thread corrente in fase di esecuzione.

L'esempio XAML finale dovrebbe essere simile all'esempio seguente.

[!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]

L'esempio C# finale dovrebbe essere simile al seguente.

[!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]

Il grafico seguente mostra l'aspetto della finestra per entrambi i linguaggi di programmazione, visualizzando i numeri arabi:

![Immagine che Visualizza i numeri arabi.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)

**Uso della proprietà Substitution**

Il modo in cui la sostituzione dei numeri funziona in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dipende sia dal linguaggio dell'elemento di testo che dal relativo <xref:System.Windows.FlowDirection>. Se il <xref:System.Windows.FlowDirection> è da sinistra a destra, viene eseguito il rendering delle cifre europee. Tuttavia, se è preceduto da testo arabo o la lingua è impostata su "AR" e la <xref:System.Windows.FlowDirection> è <xref:System.Windows.FlowDirection.RightToLeft>, viene eseguito il rendering delle cifre arabe.

In alcuni casi, tuttavia, è possibile creare un'applicazione unificata usando, ad esempio, le cifre europee per tutti gli utenti O le cifre arabe in <xref:System.Windows.Documents.Table> celle con un <xref:System.Windows.Style>specifico. Un modo semplice per eseguire questa operazione consiste nell'usare la proprietà <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.

Nell'esempio seguente, per la prima <xref:System.Windows.Controls.TextBlock> non è impostata la proprietà <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>, quindi l'algoritmo Visualizza le cifre arabe come previsto. Tuttavia, nel secondo <xref:System.Windows.Controls.TextBlock>, la sostituzione è impostata su European override della sostituzione predefinita per i numeri arabi e vengono visualizzate le cifre europee.

[!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
