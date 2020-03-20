---
title: Panoramica su allineamento, margini e spaziatura interna
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: bec2d9cd224febb650e2de67bb7406365d075963
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145475"
---
# <a name="alignment-margins-and-padding-overview"></a>Panoramica su allineamento, margini e spaziatura interna
La <xref:System.Windows.FrameworkElement> classe espone diverse proprietà utilizzate per posizionare con precisione gli elementi figlio. In questo argomento vengono illustrate <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>quattro <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>delle <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>proprietà più importanti: , , e . È fondamentale comprendere gli effetti di queste proprietà, perché forniscono la base per controllare la posizione degli elementi nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>Introduzione al posizionamento degli elementi  
 È possibile posizionare gli elementi in molti modi con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Tuttavia, ottenere un layout ideale <xref:System.Windows.Controls.Panel> va oltre la semplice scelta dell'elemento giusto. Per un controllo preciso del <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>posizionamento <xref:System.Windows.Controls.Border.Padding%2A>è <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> necessario comprendere le proprietà , <xref:System.Windows.FrameworkElement.Margin%2A>, e .  
  
 La figura seguente illustra uno scenario di layout in cui vengono usate diverse proprietà di posizionamento.  
  
 ![Esempio di proprietà di posizionamento WPF](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 A prima vista, gli <xref:System.Windows.Controls.Button> elementi in questa illustrazione possono sembrare posizionati in modo casuale. Le posizioni sono in realtà controllate con precisione usando una combinazione di margini, allineamento e spaziatura interna.  
  
 L'esempio seguente descrive come creare il layout nella figura precedente. Un <xref:System.Windows.Controls.Border> elemento incapsula <xref:System.Windows.Controls.StackPanel>un <xref:System.Windows.Controls.Border.Padding%2A> elemento padre , con un valore di 15 pixel indipendenti dal dispositivo. Questo spiega la <xref:System.Windows.Media.Brushes.LightBlue%2A> banda stretta che <xref:System.Windows.Controls.StackPanel>circonda il bambino . Gli elementi <xref:System.Windows.Controls.StackPanel> figlio di vengono utilizzati per illustrare ognuna delle varie proprietà di posizionamento descritte in dettaglio in questo argomento. Tre <xref:System.Windows.Controls.Button> elementi vengono utilizzati <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> per illustrare le proprietà e .  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Il diagramma seguente mostra una visualizzazione dettagliata delle varie proprietà di posizionamento usate nell'esempio precedente. Le sezioni successive di questo argomento descrivono in maggior dettaglio come usare ogni proprietà di posizionamento.  
  
 ![Proprietà di posizionamento con&#45;di chiamata allo schermo](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>Informazioni sulle proprietà di allineamento  
 Le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà e descrivono il posizionamento di un elemento figlio all'interno dello spazio di layout allocato di un elemento padre. Usando insieme queste proprietà, è possibile posizionare con precisione gli elementi figlio. Ad esempio, gli <xref:System.Windows.Controls.DockPanel> elementi figlio di un <xref:System.Windows.HorizontalAlignment.Left>oggetto <xref:System.Windows.HorizontalAlignment.Right>possono <xref:System.Windows.HorizontalAlignment.Center>specificare <xref:System.Windows.HorizontalAlignment.Stretch> quattro diversi tracciati orizzontali: , , o , o per riempire lo spazio disponibile. Per il posizionamento verticale sono disponibili valori analoghi.  
  
> [!NOTE]
> Le proprietà <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> e impostate in modo <xref:System.Windows.HorizontalAlignment.Stretch> esplicito su un elemento hanno la precedenza sul valore della proprietà. Il tentativo <xref:System.Windows.FrameworkElement.Height%2A>di <xref:System.Windows.FrameworkElement.Width%2A>impostare <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> , `Stretch` e `Stretch` il valore di risultati in cui la richiesta viene ignorata.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>Proprietà HorizontalAlignment  
 La <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dichiara le caratteristiche di allineamento orizzontale da applicare agli elementi figlio. Nella tabella seguente vengono illustrati tutti <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> i valori possibili della proprietà.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Gli elementi figlio sono allineati a sinistra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Gli elementi figlio sono allineati a destra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. Explicit <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> e i valori hanno la precedenza.|  
  
 Nell'esempio seguente viene <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> illustrato <xref:System.Windows.Controls.Button> come applicare la proprietà agli elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti di <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> posizionamento di ogni valore sono visibili nell'illustrazione.  
  
 ![Esempio di HorizontalAlignment](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>Proprietà VerticalAlignment  
 La <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà descrive le caratteristiche di allineamento verticale da applicare agli elementi figlio. Nella tabella seguente vengono illustrati tutti <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> i valori possibili per la proprietà.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Gli elementi figlio sono allineati in alto nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Gli elementi figlio sono allineati in basso nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. Explicit <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> e i valori hanno la precedenza.|  
  
 Nell'esempio seguente viene <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> illustrato <xref:System.Windows.Controls.Button> come applicare la proprietà agli elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering. Ai fini di questo <xref:System.Windows.Controls.Grid> esempio, un elemento con linee della griglia visibili viene utilizzato come elemento padre, per illustrare meglio il comportamento di layout di ogni valore della proprietà.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti di <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> posizionamento di ogni valore sono visibili nell'illustrazione.  
  
 ![Esempio di proprietà VerticalAlignment](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>Informazioni sulla proprietà Margin  
 La <xref:System.Windows.FrameworkElement.Margin%2A> proprietà descrive la distanza tra un elemento e il relativo elemento figlio o peer. <xref:System.Windows.FrameworkElement.Margin%2A>i valori possono essere uniformi, utilizzando una sintassi come `Margin="20"`. Con questa sintassi, all'elemento verrebbe applicata un'uniforme <xref:System.Windows.FrameworkElement.Margin%2A> di 20 pixel indipendenti dal dispositivo. <xref:System.Windows.FrameworkElement.Margin%2A>I valori possono anche assumere la forma di quattro valori distinti, ognuno dei quali descrive un margine `Margin="0,10,5,25"`distinto da applicare a sinistra, in alto, a destra e in basso (in questo ordine), ad esempio . L'uso <xref:System.Windows.FrameworkElement.Margin%2A> corretto della proprietà consente un controllo molto preciso della posizione di rendering di un elemento e della posizione di rendering degli elementi adiacenti e degli elementi figlio.  
  
> [!NOTE]
> Un margine diverso da zero applica <xref:System.Windows.FrameworkElement.ActualWidth%2A> spazio <xref:System.Windows.FrameworkElement.ActualHeight%2A>al di fuori dell'elemento e .  
  
 Nell'esempio seguente viene illustrato come applicare <xref:System.Windows.Controls.Button> margini uniformi intorno a un gruppo di elementi. Gli <xref:System.Windows.Controls.Button> elementi sono distanziati uniformemente con un buffer di margine di dieci pixel in ogni direzione.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 In diverse situazioni un margine uniforme non è appropriato. In questi casi, è possibile applicare una spaziatura non uniforme. L'esempio seguente illustra come applicare una spaziatura dei margini non uniforme agli elementi figlio. I margini sono descritti in quest'ordine: sinistro, superiore, destro, inferiore.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>
## <a name="understanding-the-padding-property"></a>Informazioni sulla proprietà Padding  
 L'imbottitura è simile alla <xref:System.Windows.FrameworkElement.Margin%2A> maggior parte degli aspetti. Il Padding proprietà viene esposta solo su alcune classi, <xref:System.Windows.Controls.Control>principalmente <xref:System.Windows.Controls.TextBlock> per comodità: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, e sono esempi di classi che espongono una proprietà Padding . La <xref:System.Windows.Controls.Border.Padding%2A> proprietà ingrandisce le dimensioni effettive <xref:System.Windows.Thickness> di un elemento figlio in base al valore specificato.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Border.Padding%2A> illustrato <xref:System.Windows.Controls.Border> come applicare a un elemento padre.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Uso di allineamento, margini e spaziatura interna in un'applicazione  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , e fornire il controllo [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]di posizionamento necessario per creare un complesso . È possibile usare gli effetti di ogni proprietà per modificare il posizionamento degli elementi figlio, ottenendo in questo modo flessibilità nella creazione di applicazioni ed esperienze utente dinamiche.  
  
 L'esempio seguente illustra ognuno dei concetti descritti in questo argomento. Basandosi sull'infrastruttura disponibile nel primo esempio di <xref:System.Windows.Controls.Grid> questo argomento, <xref:System.Windows.Controls.Border> in questo esempio viene aggiunto un elemento come elemento figlio dell'elemento nel primo esempio. <xref:System.Windows.Controls.Border.Padding%2A>viene applicato all'elemento padre. <xref:System.Windows.Controls.Border> L'oggetto <xref:System.Windows.Controls.Grid> viene utilizzato per <xref:System.Windows.Controls.StackPanel> partizionare lo spazio tra tre elementi figlio. <xref:System.Windows.Controls.Button>elementi vengono nuovamente utilizzati per <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>mostrare i vari effetti di e . <xref:System.Windows.Controls.TextBlock>gli elementi vengono <xref:System.Windows.Controls.ColumnDefinition> aggiunti a ciascuno per <xref:System.Windows.Controls.Button> definire meglio le varie proprietà applicate agli elementi in ogni colonna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Dopo la compilazione, l'applicazione precedente genera un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di aspetto simile al seguente. Gli effetti dei vari valori di proprietà sono evidenti nella spaziatura tra gli <xref:System.Windows.Controls.TextBlock> elementi e i valori di proprietà significativi per gli elementi in ogni colonna vengono visualizzati all'interno degli elementi.  
  
 ![Alcune proprietà di posizionamento in un'applicazione](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>Passaggi successivi  
 Il posizionamento delle <xref:System.Windows.FrameworkElement> proprietà definite dalla classe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente un controllo preciso del posizionamento degli elementi all'interno delle applicazioni. Quelle descritte qui sono dunque le diverse tecniche che permettono di posizionare in modo più efficace gli elementi usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Sono inoltre disponibili ulteriori risorse in cui il layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene descritto in modo più particolareggiato. L'argomento [Cenni estesi](../controls/panels-overview.md) contiene <xref:System.Windows.Controls.Panel> ulteriori dettagli sui vari elementi. L'argomento [Procedura dettagliata: la prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md) introduce tecniche avanzate che usano elementi di layout per posizionare i componenti e associare le relative azioni alle origini dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Cenni preliminari sugli elementi Panel](../controls/panels-overview.md)
- [Layout](layout.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
