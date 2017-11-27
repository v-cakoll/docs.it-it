---
title: "Cenni preliminari sulle funzionalità bidirezionali di WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 716774efdf62356c2e3253c588dabb51de74470c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="bidirectional-features-in-wpf-overview"></a>Cenni preliminari sulle funzionalità bidirezionali di WPF
A differenza di altre piattaforme di sviluppo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ha molte funzionalità che supportano lo sviluppo rapido di contenuto bidirezionale, ad esempio, misto dati da sinistra a destra e a destra per sinistra nello stesso documento. Allo stesso tempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea un'esperienza eccellente per gli utenti che richiedono funzionalità bidirezionali come l'arabo ed ebraico gli utenti.  
  
 Le sezioni seguenti illustrano molte funzionalità bidirezionali con i relativi esempi in cui viene descritto come ottenere la migliore visualizzazione di contenuto bidirezionale. La maggior parte degli esempi utilizza [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], anche se è possibile applicare facilmente i concetti di [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] o [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] codice.  
  

  
<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 La proprietà di base che definisce la direzione di flusso del contenuto in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Questa proprietà può essere impostata su uno dei due valori di enumerazione, <xref:System.Windows.FlowDirection.LeftToRight> o <xref:System.Windows.FlowDirection.RightToLeft>. La proprietà è disponibile a tutti i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli elementi che ereditano da <xref:System.Windows.FrameworkElement>.  
  
 Nell'esempio seguente impostano la direzione del flusso di un <xref:System.Windows.Controls.TextBox> elemento.  
  
 **Direzione di flusso da sinistra a destra**  
  
 [!code-xaml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Direzione di flusso da destra a sinistra**  
  
 [!code-xaml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 La figura seguente illustra il rendering del codice precedente.  
  
 **Figura che illustra FlowDirection**  
  
 ![Allineamento di TextBlock](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.PNG "LefttoRightRighttoLeft")  
  
 Un elemento all'interno di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] albero erediteranno il <xref:System.Windows.FrameworkElement.FlowDirection%2A> dal relativo contenitore. Nell'esempio seguente, il <xref:System.Windows.Controls.TextBlock> è all'interno di un <xref:System.Windows.Controls.Grid>, che risiede in un <xref:System.Windows.Window>. L'impostazione di <xref:System.Windows.FrameworkElement.FlowDirection%2A> per il <xref:System.Windows.Window> implica l'impostazione per il <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.TextBlock> anche.  
  
 Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xaml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 Il livello principale <xref:System.Windows.Window> ha un <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, pertanto anche tutti gli elementi in esso contenuti ereditano lo stesso <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Per un elemento eseguire l'override di un oggetto specificato <xref:System.Windows.FrameworkElement.FlowDirection%2A> deve aggiungere una modifica della direzione esplicita, ad esempio il secondo <xref:System.Windows.Controls.TextBlock> nell'esempio precedente in <xref:System.Windows.FlowDirection.LeftToRight>. Se non si <xref:System.Windows.FrameworkElement.FlowDirection%2A> è definito, il valore predefinito <xref:System.Windows.FlowDirection.LeftToRight> si applica.  
  
 L'immagine seguente mostra l'output dell'esempio precedente.  
  
 **Figura che illustra l'assegnazione esplicita di FlowDirection**  
  
 ![Illustrazione della direzione del flusso](../../../../docs/framework/wpf/advanced/media/flowdir.PNG "FlowDir")  
  
<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Molte piattaforme di sviluppo, ad esempio [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e Java forniscono uno speciale supporto per lo sviluppo di contenuto bidirezionale. Linguaggi di markup, ad esempio [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] offrono agli autori dei contenuti il markup necessario per visualizzare il testo in qualsiasi direzione richiesta, ad esempio il [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 tag, "dir" accetta "rtl" o "ltr" come valori. Questo tag è simile al <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà, ma la <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà funziona in modo più avanzato per il layout del contenuto testuale e può essere utilizzato per contenuti diversi dal testo.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Documents.FlowDocument> è un versatile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento che può contenere una combinazione di testo, tabelle, immagini e altri elementi. Gli esempi nelle sezioni seguenti usano questo elemento.  
  
 Aggiunta di testo a un <xref:System.Windows.Documents.FlowDocument> può essere eseguita in più modi. È un modo semplice per eseguire questa operazione tramite un <xref:System.Windows.Documents.Paragraph> che è un elemento a livello di blocco utilizzato per raggruppare il contenuto, ad esempio testo. Per aggiungere testo agli elementi di livello in linea, utilizzare gli esempi <xref:System.Windows.Documents.Span> e <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span>è un elemento di contenuto del flusso di livello inline utilizzato per raggruppare altri elementi inline, mentre un <xref:System.Windows.Documents.Run> è un flusso di livello inline contenuto elemento destinato a contenere una sequenza di testo non formattato. Oggetto <xref:System.Windows.Documents.Span> può contenere più <xref:System.Windows.Documents.Run> elementi.  
  
 Nel primo esempio di documento contiene un documento con un numero di rete condividono nomi; ad esempio `\\server1\folder\file.ext`. Indipendentemente dal fatto che questo collegamento di rete si trovi in un documento in arabo o in inglese, si vuole che venga sempre visualizzato nello stesso modo. La figura seguente illustra il collegamento in un arabo <xref:System.Windows.FlowDirection.RightToLeft> documento.  
  
 **Figura che illustra l'uso dell'elemento Span**  
  
 ![Documento con flusso da destra a sinistra](../../../../docs/framework/wpf/advanced/media/flowdocument.PNG "FlowDocument")  
  
 Poiché il testo è <xref:System.Windows.FlowDirection.RightToLeft>, speciale tutti i caratteri, ad esempio il "\\", separare il testo in un ordine da destra a sinistra. Di conseguenza il collegamento non viene visualizzato nell'ordine corretto, pertanto, per risolvere il problema, il testo deve essere incorporato per mantenere un apposito <xref:System.Windows.Documents.Run> flusso <xref:System.Windows.FlowDirection.LeftToRight>. Anziché un apposito <xref:System.Windows.Documents.Run> per ogni lingua, un modo migliore per risolvere il problema consiste nell'incorporare il testo in lingua inglese utilizzato meno frequentemente in un arabo più grande <xref:System.Windows.Documents.Span>.  
  
 La figura seguente illustra questa soluzione.  
  
 **Figura che illustra l'uso dell'elemento Run incorporato in un elemento Span**  
  
 ![Screenshot di XamlPad](../../../../docs/framework/wpf/advanced/media/runspan.PNG "RunSpan")  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Documents.Run> e <xref:System.Windows.Documents.Span> elementi nei documenti.  
  
 [!code-xaml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Elementi Span  
 Il <xref:System.Windows.Documents.Span> elemento funziona come un separatore di limiti tra i testi con diverse direzioni di flusso.  Anche <xref:System.Windows.Documents.Span> elementi con la stessa direzione di flusso sono considerati diversi ambiti bidirezionali, pertanto il <xref:System.Windows.Documents.Span> gli elementi vengono ordinati nel contenitore <xref:System.Windows.FlowDirection>, solo il contenuto all'interno di <xref:System.Windows.Documents.Span> elemento segue la <xref:System.Windows.FlowDirection> del <xref:System.Windows.Documents.Span>.  
  
 L'immagine seguente mostra la direzione del flusso di diversi <xref:System.Windows.Controls.TextBlock> elementi.  
  
 **Figura che illustra FlowDirection in vari elemento TextBlock**  
  
 ![Blocchi di testo con direzioni di flusso diverse](../../../../docs/framework/wpf/advanced/media/span.PNG "Span")  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Documents.Span> e <xref:System.Windows.Documents.Run> elementi da produrre i risultati mostrati nell'immagine precedente.  
  
 [!code-xaml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 Nel <xref:System.Windows.Controls.TextBlock> elementi dell'esempio, il <xref:System.Windows.Documents.Span> elementi vengono disposti in base al <xref:System.Windows.FlowDirection> dei relativi elementi padre, ma il testo all'interno di ogni <xref:System.Windows.Documents.Span> elemento scorre in base alla propria <xref:System.Windows.FlowDirection>. Questa condizione può essere applicata all'alfabeto latino e arabo oppure a qualsiasi altra lingua.  
  
### <a name="adding-xmllang"></a>Aggiunta di xml:lang  
 La figura seguente illustra un altro esempio che utilizza numeri ed espressioni aritmetiche, ad esempio `"200.0+21.4=221.4"`. Si noti che solo il <xref:System.Windows.FlowDirection> è impostata.  
  
 **Figura che illustra come la visualizzazione di numero usando solo FlowDirection**  
  
 ![Numeri con flusso da destra a sinistra](../../../../docs/framework/wpf/advanced/media/langattribute.PNG "LangAttribute")  
  
 Gli utenti dell'applicazione verranno ricompensa dall'output, anche se il <xref:System.Windows.FlowDirection> i numeri non sono forma numeri arabi devono essere corretto.  
  
 Gli elementi XAML possono includere un [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] attributo (`xml:lang`) che definisce la lingua di ogni elemento. XAML supporta inoltre un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] principio di lingua in base al quale `xml:lang` applicati agli elementi padre nell'albero di valori vengono utilizzati dagli elementi figlio. Nell'esempio precedente, perché non è stata definita una lingua per il <xref:System.Windows.Documents.Run> elemento o primo livello gli elementi, il valore predefinito `xml:lang` è stato utilizzato, ovvero `en-US` per XAML. L'algoritmo di data shaping numero interno di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] seleziona i numeri nella lingua corrispondente, in questo caso l'inglese. Per rendere l'arabo correttamente rendering dei numeri `xml:lang` deve essere impostata.  
  
 Nella figura seguente viene illustrato l'esempio con `xml:lang` aggiunto.  
  
 **Figura che illustra l'uso dell'attributo xml:lang**  
  
 ![Numeri arabi con flusso da destra a sinistra](../../../../docs/framework/wpf/advanced/media/langattribute2.PNG "LangAttribute2")  
  
 L'esempio seguente aggiunge `xml:lang` all'applicazione.  
  
 [!code-xaml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Tenere presente che molte lingue hanno diversi `xml:lang` valori a seconda dell'area di destinazione, ad esempio, `"ar-SA"` e `"ar-EG"` rappresentano due varianti dell'arabo. Negli esempi precedenti viene illustrato che è necessario definire entrambi il `xml:lang` e <xref:System.Windows.FlowDirection> valori.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementi non di testo  
 <xref:System.Windows.FlowDirection>definisce non solo orientamento del testo in un elemento testuale, ma anche la direzione del flusso di quasi tutti gli altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento. Nell'immagine seguente viene illustrata una <xref:System.Windows.Controls.ToolBar> che utilizza un oggetto orizzontale <xref:System.Windows.Media.LinearGradientBrush> per disegnare lo sfondo.  
  
 **Immagine che mostra una barra degli strumenti con sfumatura da sinistra a destra**  
  
 ![Screenshot della sfumatura](../../../../docs/framework/wpf/advanced/media/gradient.PNG "Gradient")  
  
 Dopo aver impostato la <xref:System.Windows.FlowDirection> a <xref:System.Windows.FlowDirection.RightToLeft>, non solo il <xref:System.Windows.Controls.ToolBar> pulsanti vengono disposte da destra a sinistra, ma anche il <xref:System.Windows.Media.LinearGradientBrush> si allineano nuovamente gli offset in modo che scorrano da destra a sinistra.  
  
 La figura seguente illustra il riallineamento del <xref:System.Windows.Media.LinearGradientBrush>.  
  
 **Immagine che illustra una barra degli strumenti con una sfumatura da destra a sinistra**  
  
 ![Sfumatura con flusso da destra a sinistra](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.PNG "Gradient2_WPF")  
  
 Nell'esempio seguente disegna un <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>. (Per disegnarlo da sinistra a destra, rimuovere il <xref:System.Windows.FlowDirection> attributo la <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>Eccezioni di FlowDirection  
 Esistono alcuni casi in cui <xref:System.Windows.FlowDirection> non funzionino come previsto. In questa sezione vengono illustrate due di queste eccezioni.  
  
 **Immagine**  
  
 Un <xref:System.Windows.Controls.Image> rappresenta un controllo che visualizza un'immagine. In [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] e può essere utilizzato con un <xref:System.Windows.Controls.Image.Source%2A> proprietà che definisce il [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] del <xref:System.Windows.Controls.Image> da visualizzare.  
  
 A differenza degli altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi, un <xref:System.Windows.Controls.Image> non eredita il <xref:System.Windows.FlowDirection> dal contenitore. Tuttavia, se il <xref:System.Windows.FlowDirection> è impostato in modo esplicito su <xref:System.Windows.FlowDirection.RightToLeft>, un <xref:System.Windows.Controls.Image> viene visualizzato in senso orizzontale capovolto. Questa condizione viene implementata come una funzionalità utile per gli sviluppatori di contenuti bidirezionali, perché in alcuni casi il capovolgimento in senso orizzontale dell'immagine genera l'effetto desiderato.  
  
 La figura seguente illustra un capovolta <xref:System.Windows.Controls.Image>.  
  
 **Immagine che illustra un'immagine capovolta**  
  
 ![Screenshot di XamlPad](../../../../docs/framework/wpf/advanced/media/image.PNG "Image")  
  
 Nell'esempio seguente viene dimostrato che la <xref:System.Windows.Controls.Image> non riesce a ereditare il <xref:System.Windows.FlowDirection> dal <xref:System.Windows.Controls.StackPanel> che lo contiene. **Nota** è necessario disporre di un file denominato **ms_logo** nell'unità C:\ per eseguire questo esempio.  
  
 [!code-xaml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Nota** nei file di download è incluso un **ms_logo** file. Nel codice si presuppone che il file con estensione jpg non si trovi all'interno del progetto ma in un'altra posizione nell'unità C:\. È necessario copiare il file con estensione jpg dai file di progetto nell'unità C:\ oppure modificare il codice affinché la ricerca venga eseguita all'interno del progetto. A tale scopo, modificare `Source="file://c:/ms_logo.jpg"` a `Source="ms_logo.jpg"`.  
  
 **Percorsi**  
  
 Oltre a un <xref:System.Windows.Controls.Image>, un altro elemento interessante è <xref:System.Windows.Shapes.Path>. Path è un oggetto che consente di disegnare una serie di righe e curve collegate. Si comporta in modo simile a un <xref:System.Windows.Controls.Image> per quanto riguarda il <xref:System.Windows.FlowDirection>, ad esempio relativi <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> è un'immagine speculare orizzontale di relativo <xref:System.Windows.FlowDirection.LeftToRight> uno. Tuttavia, a differenza di un <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> eredita relativo <xref:System.Windows.FlowDirection> dal contenitore e uno non è necessario specificarlo in modo esplicito.  
  
 L'esempio seguente disegna una freccia semplice con 3 linee. La prima freccia eredita il <xref:System.Windows.FlowDirection.RightToLeft> direzione del flusso di <xref:System.Windows.Controls.StackPanel> in modo che i punti iniziale e finale sono misurati da una radice sul lato destro. La seconda freccia è esplicita <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> inoltre avviato sul lato destro. Tuttavia, la radice iniziale della terza freccia è collocata sul lato sinistro. Per ulteriori informazioni sul disegno, vedere <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xaml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 L'immagine seguente mostra l'output dell'esempio precedente.  
  
 **Immagine che illustra le frecce disegnate usando l'elemento Path**  
  
 ![Paths](../../../../docs/framework/wpf/advanced/media/paths.PNG "Paths")  
  
 Il <xref:System.Windows.Controls.Image> e <xref:System.Windows.Shapes.Path> sono riportati due esempi di come [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] utilizza <xref:System.Windows.FlowDirection>. Oltre a disporre gli [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi in una direzione specifica all'interno di un contenitore, <xref:System.Windows.FlowDirection> può essere utilizzato con gli elementi, ad esempio <xref:System.Windows.Controls.InkPresenter> che esegue il rendering dell'input penna su una superficie, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Ogni volta che è necessario un comportamento da destra a sinistro del contenuto che simula un comportamento da sinistra a destra, o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] disponibile tale funzionalità.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Sostituzione numerica  
 In passato, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] è supportata la sostituzione dei numeri, consentendo la rappresentazione di diverse forme relative alla lingua per le cifre stesso mantenendo l'archiviazione interna di queste cifre unificata le diverse impostazioni locali, ad esempio i numeri vengono memorizzati i noti valori esadecimali, 0x40, 0x41, ma visualizzati in base alla lingua selezionata.  
  
 Ciò è consentito alle applicazioni di elaborare valori numerici senza la necessità di convertirli da una lingua a un'altra, ad esempio un utente può aprire un [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] foglio di calcolo in un arabo localizzata [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e visualizzare i numeri in arabo, ma aprirli in versione europea di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e visualizzando la rappresentazione europea degli stessi numeri. Questa condizione è necessaria anche per altri simboli, quali i separatori virgola e il simbolo della percentuale, perché sono spesso associati a numeri nello stesso documento.  
  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stata mantenuta la stessa tradizione e aggiunto un ulteriore supporto a questa funzionalità che consente un maggiore controllo dell'utente sul momento e sulla modalità d'su della sostituzione. Sebbene questa funzionalità sia stata progettata per tutte le lingue, è particolarmente utile per i contenuti bidirezionali in cui la definizione delle cifre per una lingua specifica rappresenta solitamente una sfida per gli sviluppatori di applicazioni, a causa delle diverse impostazioni cultura con cui un'applicazione può essere eseguita.  
  
 La proprietà di base controllare la modalità sostituzione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è il <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà di dipendenza. La <xref:System.Windows.Media.NumberSubstitution> classe specifica la modalità dei numeri nel testo da visualizzare. Include tre proprietà pubbliche che ne definiscono il comportamento. Di seguito è riportato un riepilogo di tutte le proprietà.  
  
 **CultureSource:**  
  
 Questa proprietà specifica come vengono determinate le impostazioni cultura per i numeri. Accetta uno dei tre <xref:System.Windows.Media.NumberCultureSource> valori di enumerazione.  
  
-   Override: Numero delle impostazioni cultura sono quello di <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> proprietà.  
  
-   Text: le impostazioni cultura del numero sono quelle della sequenza di testo. Nel markup, il risultato sarà `xml:lang`, o il relativo alias `Language` proprietà (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Inoltre, è il valore predefinito per le classi che derivano da <xref:System.Windows.FrameworkContentElement>. Tali classi includono <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> e così via.  
  
-   User: le impostazioni cultura del numero sono quelle del thread corrente. Questa proprietà è l'impostazione predefinita per tutte le sottoclassi di <xref:System.Windows.FrameworkElement> , ad esempio <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> e <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 Il <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> proprietà viene utilizzata solo se il <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> è impostata su <xref:System.Windows.Media.NumberCultureSource.Override> e viene ignorato in caso contrario. Specifica le impostazioni cultura del numero. Il valore `null`, il valore predefinito, viene interpretato come en-US.  
  
 **Substitution**:  
  
 Questa proprietà specifica il tipo di sostituzione numerica da eseguire. Accetta uno dei seguenti <xref:System.Windows.Media.NumberSubstitutionMethod> valori di enumerazione.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: Il metodo di sostituzione è determinato in base alle impostazioni cultura del numero <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> proprietà. Questa è l'impostazione predefinita.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Se il numero delle impostazioni cultura sono una lingua araba o Farsi, specifica che le cifre dipendono dal contesto.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>: I numeri vengono sempre visualizzati come cifre europee.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: I numeri vengono sottoposti a rendering utilizzando le cifre nazionali per impostazioni cultura del numero, come specificato dalle impostazioni cultura <xref:System.Globalization.CultureInfo.NumberFormat%2A>.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: I numeri vengono visualizzati utilizzando le cifre tradizionali per impostazioni cultura del numero. Per la maggior parte delle impostazioni cultura, queste sono le stesse <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Tuttavia, <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> risultati cifre latine per alcune impostazioni cultura arabe, mentre questo valore in cifre arabe per tutte le lingue arabe.  
  
 Cosa significano questi valori per uno sviluppatore di contenuti bidirezionali? Nella maggior parte dei casi, lo sviluppatore deve solo definire <xref:System.Windows.FlowDirection> e la lingua del testo di ogni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento, ad esempio `Language="ar-SA"` e <xref:System.Windows.Media.NumberSubstitution> logica occupa la visualizzazione dei numeri in base alle corrette [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Nell'esempio seguente viene illustrato l'utilizzo di numeri in arabo e inglese in un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazione in esecuzione in una versione araba di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xaml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 La figura seguente illustra l'output dell'esempio precedente, se si esegue una versione araba di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 **Immagine che illustra i numeri arabi e inglesi visualizzati**  
  
 ![Screenshot di XamlPad con numeri](../../../../docs/framework/wpf/advanced/media/numbers.PNG "Numbers")  
  
 Il <xref:System.Windows.FlowDirection> era importante in questo caso, poiché l'impostazione di <xref:System.Windows.FlowDirection> a <xref:System.Windows.FlowDirection.LeftToRight> avrebbe prodotto cifre europee. Le sezioni seguenti descrivono come ottenere una visualizzazione unificata delle cifre in tutto il documento. Se l'esempio non viene eseguito nella versione araba di Windows, tutte le cifre vengono visualizzate come cifre europee.  
  
 **Definizione delle regole di sostituzione**  
  
 In un'applicazione reale, è necessario impostare l'oggetto Language a livello di codice. Ad esempio, si desidera impostare il `xml:lang` attributo deve corrispondere a quello utilizzato per il sistema [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], o modificare la lingua in base allo stato dell'applicazione.  
  
 Se si desidera apportare modifiche in base allo stato dell'applicazione, utilizzare altre funzionalità fornite da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Innanzitutto, impostare il componente di applicazione `NumberSubstitution.CultureSource="Text"`. Utilizzo di questa impostazione garantisce che le impostazioni non provengono dal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per elementi di testo "User" come valore predefinito, ad esempio <xref:System.Windows.Controls.TextBlock>.  
  
 Ad esempio:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 Nel corrispondente [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] il codice, impostare il `Language` proprietà, ad esempio, per `"ar-SA"`.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 Se è necessario impostare il `Language` proprietà per l'utente corrente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] lingua da utilizzare per il codice seguente.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A>rappresenta le impostazioni cultura correnti usate dal thread corrente in fase di esecuzione.  
  
 Il finale [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] esempio dovrebbe essere simile all'esempio seguente.  
  
 [!code-xaml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 Il finale [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] esempio dovrebbe essere simile al seguente.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 L'immagine seguente mostra l'aspetto della finestra per entrambi i linguaggi di programmazione.  
  
 **Immagine che visualizza i numeri arabi**  
  
 ![Numeri arabi](../../../../docs/framework/wpf/advanced/media/numbers2.PNG "Numbers2")  
  
 **Uso della proprietà Substitution**  
  
 La sostituzione numerica funziona in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dipende dalla lingua dell'elemento di testo e il relativo <xref:System.Windows.FlowDirection>. Se il <xref:System.Windows.FlowDirection> da sinistra a destra, quindi vengono eseguito il rendering delle cifre europee. Tuttavia è preceduto da un testo arabo, se è la lingua impostata su "ar" e <xref:System.Windows.FlowDirection> è <xref:System.Windows.FlowDirection.RightToLeft>, vengono eseguito il rendering delle cifre arabe.  
  
 In alcuni casi, tuttavia, è possibile creare un'applicazione unificata usando, ad esempio, le cifre europee per tutti gli utenti Oppure cifre arabe nelle <xref:System.Windows.Documents.Table> celle con una versione specifica <xref:System.Windows.Style>. Un modo semplice per ottenere che utilizza il <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà.  
  
 Nell'esempio seguente, il primo <xref:System.Windows.Controls.TextBlock> non dispone di <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> proprietà impostata, pertanto l'algoritmo consente di visualizzare le cifre arabe come previsto. Tuttavia nel secondo <xref:System.Windows.Controls.TextBlock>, la sostituzione viene impostata su European si esegue l'override della sostituzione predefinita per i numeri arabi e vengono visualizzate le cifre europee.  
  
 [!code-xaml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
