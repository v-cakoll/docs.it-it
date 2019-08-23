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
ms.openlocfilehash: bf351b6df972dc992f214ddfe899bfa808d0cd53
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963642"
---
# <a name="alignment-margins-and-padding-overview"></a>Panoramica su allineamento, margini e spaziatura interna
La <xref:System.Windows.FrameworkElement> classe espone diverse proprietà che vengono usate per posizionare con precisione gli elementi figlio. In questo argomento vengono illustrate quattro delle proprietà più <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>importanti <xref:System.Windows.FrameworkElement.Margin%2A>: <xref:System.Windows.Controls.Border.Padding%2A>,, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>e. È fondamentale comprendere gli effetti di queste proprietà, perché forniscono la base per controllare la posizione degli elementi nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>Introduzione al posizionamento degli elementi  
 È possibile posizionare gli elementi in molti modi con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Tuttavia, il raggiungimento del layout ideale va oltre la <xref:System.Windows.Controls.Panel> semplice scelta dell'elemento corretto. Per un controllo accurato del posizionamento è necessario <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>conoscere <xref:System.Windows.FrameworkElement.Margin%2A>le <xref:System.Windows.Controls.Border.Padding%2A>proprietà, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , e.  
  
 La figura seguente illustra uno scenario di layout in cui vengono usate diverse proprietà di posizionamento.  
  
 ![Esempio di proprietà di posizionamento WPF](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 A prima vista, gli <xref:System.Windows.Controls.Button> elementi in questa illustrazione potrebbero sembrare posizionati in modo casuale. Le posizioni sono in realtà controllate con precisione usando una combinazione di margini, allineamento e spaziatura interna.  
  
 L'esempio seguente descrive come creare il layout nella figura precedente. Un <xref:System.Windows.Controls.Border> elemento incapsula un elemento padre <xref:System.Windows.Controls.StackPanel>con un <xref:System.Windows.Controls.Border.Padding%2A> valore di 15 pixel indipendenti dal dispositivo. Questo account per la banda <xref:System.Windows.Media.Brushes.LightBlue%2A> stretta che racchiude l'elemento figlio <xref:System.Windows.Controls.StackPanel>. Gli elementi figlio di <xref:System.Windows.Controls.StackPanel> vengono utilizzati per illustrare ognuna delle varie proprietà di posizionamento descritte in dettaglio in questo argomento. Vengono <xref:System.Windows.Controls.Button> usati tre elementi per illustrare le <xref:System.Windows.FrameworkElement.Margin%2A> proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Il diagramma seguente mostra una visualizzazione dettagliata delle varie proprietà di posizionamento usate nell'esempio precedente. Le sezioni successive di questo argomento descrivono in maggior dettaglio come usare ogni proprietà di posizionamento.  
  
 ![Positioning Properties with Screen Call&#45;outs](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>Informazioni sulle proprietà di allineamento  
 Le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> e descrivono come posizionare un elemento figlio all'interno dello spazio di layout allocato di un elemento padre. Usando insieme queste proprietà, è possibile posizionare con precisione gli elementi figlio. Gli elementi figlio <xref:System.Windows.Controls.DockPanel> di un oggetto possono ad esempio specificare quattro diversi allineamenti <xref:System.Windows.HorizontalAlignment.Left>orizzontali, <xref:System.Windows.HorizontalAlignment.Center> <xref:System.Windows.HorizontalAlignment.Right>ovvero, o <xref:System.Windows.HorizontalAlignment.Stretch> oppure su per riempire lo spazio disponibile. Per il posizionamento verticale sono disponibili valori analoghi.  
  
> [!NOTE]
> Le <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> proprietà impostate in modo esplicito su un elemento hanno la precedenza <xref:System.Windows.HorizontalAlignment.Stretch> sul valore della proprietà. Il <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> `Stretch` tentativo di impostare, e un valore dei risultati nella richiesta viene ignorato. `Stretch`  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>Proprietà HorizontalAlignment  
 La <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dichiara le caratteristiche di allineamento orizzontale da applicare agli elementi figlio. Nella tabella seguente vengono illustrati i valori possibili della <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.  
  
|Member|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Gli elementi figlio sono allineati a sinistra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Gli elementi figlio sono allineati a destra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Stretch>Predefinita|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. I <xref:System.Windows.FrameworkElement.Width%2A> valori <xref:System.Windows.FrameworkElement.Height%2A> e espliciti hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà agli <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti del posizionamento di <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> ogni valore sono visibili nella figura.  
  
 ![Esempio di HorizontalAlignment](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>Proprietà VerticalAlignment  
 La <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà descrive le caratteristiche di allineamento verticale da applicare agli elementi figlio. Nella tabella seguente vengono illustrati tutti i valori possibili per <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> la proprietà.  
  
|Member|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Gli elementi figlio sono allineati in alto nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Gli elementi figlio sono allineati in basso nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Stretch>Predefinita|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. I <xref:System.Windows.FrameworkElement.Width%2A> valori <xref:System.Windows.FrameworkElement.Height%2A> e espliciti hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà agli <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering. Ai fini di questo esempio, viene <xref:System.Windows.Controls.Grid> utilizzato un elemento con linee della griglia visibile come elemento padre, per illustrare meglio il comportamento del layout di ogni valore della proprietà.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti del posizionamento di <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> ogni valore sono visibili nella figura.  
  
 ![Esempio di proprietà VerticalAlignment](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>Informazioni sulla proprietà Margin  
 La <xref:System.Windows.FrameworkElement.Margin%2A> proprietà descrive la distanza tra un elemento e i relativi elementi figlio o peer. <xref:System.Windows.FrameworkElement.Margin%2A>i valori possono essere uniformi usando una `Margin="20"`sintassi simile a. Con questa sintassi, all'elemento <xref:System.Windows.FrameworkElement.Margin%2A> viene applicata un'uniforme di 20 pixel indipendenti dal dispositivo. <xref:System.Windows.FrameworkElement.Margin%2A>i valori possono anche assumere il formato di quattro valori distinti, ognuno dei quali descrive un margine distinto da applicare a sinistra, in alto, a destra e in basso (in questo ordine) `Margin="0,10,5,25"`, ad esempio. L' <xref:System.Windows.FrameworkElement.Margin%2A> uso corretto della proprietà consente un controllo molto preciso della posizione di rendering di un elemento e della posizione di rendering degli elementi adiacenti e degli elementi figlio.  
  
> [!NOTE]
> Un margine diverso da zero applica uno spazio all'esterno degli <xref:System.Windows.FrameworkElement.ActualWidth%2A> elementi <xref:System.Windows.FrameworkElement.ActualHeight%2A>e.  
  
 Nell'esempio seguente viene illustrato come applicare margini uniformi intorno a <xref:System.Windows.Controls.Button> un gruppo di elementi. Gli <xref:System.Windows.Controls.Button> elementi sono spaziati uniformemente con un buffer di margine di dieci pixel in ogni direzione.  
  
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
 La spaziatura interna <xref:System.Windows.FrameworkElement.Margin%2A> è simile alla maggior parte degli aspetti. La proprietà Padding viene esposta solo in alcune classi <xref:System.Windows.Documents.Block>, principalmente per praticità: <xref:System.Windows.Controls.Control>, <xref:System.Windows.Controls.Border>, e <xref:System.Windows.Controls.TextBlock> sono esempi di classi che espongono una proprietà Padding. La <xref:System.Windows.Controls.Border.Padding%2A> proprietà consente di ingrandire le dimensioni effettive di un elemento figlio <xref:System.Windows.Thickness> in base al valore specificato.  
  
 Nell'esempio seguente viene illustrato come applicare <xref:System.Windows.Controls.Border.Padding%2A> a un elemento <xref:System.Windows.Controls.Border> padre.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Uso di allineamento, margini e spaziatura interna in un'applicazione  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>,, e forniscono<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> il controllo di posizionamento necessario per creare un oggetto [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]complesso. <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A> È possibile usare gli effetti di ogni proprietà per modificare il posizionamento degli elementi figlio, ottenendo in questo modo flessibilità nella creazione di applicazioni ed esperienze utente dinamiche.  
  
 L'esempio seguente illustra ognuno dei concetti descritti in questo argomento. Basandosi sull'infrastruttura disponibile nel primo esempio di questo argomento, in questo esempio viene aggiunto <xref:System.Windows.Controls.Grid> un elemento come figlio <xref:System.Windows.Controls.Border> di nel primo esempio. <xref:System.Windows.Controls.Border.Padding%2A>viene applicato all'elemento padre <xref:System.Windows.Controls.Border> . Viene usato per partizionare lo spazio tra tre <xref:System.Windows.Controls.StackPanel> elementi figlio. <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Button>gli elementi vengono nuovamente utilizzati per visualizzare i vari effetti <xref:System.Windows.FrameworkElement.Margin%2A> di <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>e. <xref:System.Windows.Controls.TextBlock>gli elementi vengono aggiunti a <xref:System.Windows.Controls.ColumnDefinition> ognuno per definire meglio le varie proprietà applicate <xref:System.Windows.Controls.Button> agli elementi in ogni colonna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Dopo la compilazione, l'applicazione precedente genera un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di aspetto simile al seguente. Gli effetti dei vari valori delle proprietà sono evidenti nella spaziatura tra gli elementi e i valori di proprietà significativi per gli elementi di ogni <xref:System.Windows.Controls.TextBlock> colonna vengono visualizzati all'interno di elementi.  
  
 ![Alcune proprietà di posizionamento in un'applicazione](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>Argomenti successivi  
 Le proprietà di posizionamento definite <xref:System.Windows.FrameworkElement> dalla classe consentono un controllo accurato del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] posizionamento degli elementi all'interno delle applicazioni. Quelle descritte qui sono dunque le diverse tecniche che permettono di posizionare in modo più efficace gli elementi usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Sono inoltre disponibili ulteriori risorse in cui il layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene descritto in modo più particolareggiato. Nell'argomento [Panoramica dei pannelli](../controls/panels-overview.md) sono disponibili informazioni più dettagliate <xref:System.Windows.Controls.Panel> sui vari elementi. Argomento [della procedura dettagliata: La prima applicazione](../getting-started/walkthrough-my-first-wpf-desktop-application.md) desktop WPF introduce tecniche avanzate che usano elementi di layout per posizionare i componenti e associare le azioni alle origini dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Cenni preliminari sugli elementi Panel](../controls/panels-overview.md)
- [Layout](layout.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
