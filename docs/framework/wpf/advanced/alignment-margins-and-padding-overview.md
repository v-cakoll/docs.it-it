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
ms.openlocfilehash: eef28a178f11ea23ac23183c9ec7eb06b7f18a29
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355408"
---
# <a name="alignment-margins-and-padding-overview"></a>Panoramica su allineamento, margini e spaziatura interna
Il <xref:System.Windows.FrameworkElement> classe espone diverse proprietà che vengono usate per posizionare con precisione gli elementi figlio. In questo argomento descrive quattro delle proprietà più importanti: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. È fondamentale comprendere gli effetti di queste proprietà, perché forniscono la base per controllare la posizione degli elementi nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>Introduzione al posizionamento degli elementi  
 È possibile posizionare gli elementi in molti modi con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Tuttavia, per ottenere il layout ideale va oltre semplicemente scelta del piano <xref:System.Windows.Controls.Panel> elemento. Un controllo accurato del posizionamento richiede una conoscenza del <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà.  
  
 La figura seguente illustra uno scenario di layout in cui vengono usate diverse proprietà di posizionamento.  
  
 ![Esempio di proprietà di posizionamento WPF](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 A prima vista, il <xref:System.Windows.Controls.Button> sembrano essere posizionati in modo casuale gli elementi in questa illustrazione. Le posizioni sono in realtà controllate con precisione usando una combinazione di margini, allineamento e spaziatura interna.  
  
 L'esempio seguente descrive come creare il layout nella figura precedente. Oggetto <xref:System.Windows.Controls.Border> elemento incapsula un elemento padre <xref:System.Windows.Controls.StackPanel>, con un <xref:System.Windows.Controls.Border.Padding%2A> pari a 15 DIP (device independent pixel). Questo tiene conto delle stretta <xref:System.Windows.Media.Brushes.LightBlue%2A> fuori banda che circonda l'elemento figlio <xref:System.Windows.Controls.StackPanel>. Gli elementi figlio del <xref:System.Windows.Controls.StackPanel> vengono utilizzate per illustrare ognuna delle varie proprietà di posizionamento che sono descritte in dettaglio in questo argomento. Tre <xref:System.Windows.Controls.Button> gli elementi vengono usati per illustrare entrambi il <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Il diagramma seguente mostra una visualizzazione dettagliata delle varie proprietà di posizionamento usate nell'esempio precedente. Le sezioni successive di questo argomento descrivono in maggior dettaglio come usare ogni proprietà di posizionamento.  
  
 ![Positioning Properties with Screen Call&#45;outs](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>Informazioni sulle proprietà di allineamento  
 Il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà descrivono come un elemento figlio deve essere posizionato all'interno dello spazio di layout allocato dell'elemento di un padre. Usando insieme queste proprietà, è possibile posizionare con precisione gli elementi figlio. Ad esempio, gli elementi figlio di un <xref:System.Windows.Controls.DockPanel> possono specificare quattro allineamenti orizzontali diversi: <xref:System.Windows.HorizontalAlignment.Left>, <xref:System.Windows.HorizontalAlignment.Right>, o <xref:System.Windows.HorizontalAlignment.Center>, o a <xref:System.Windows.HorizontalAlignment.Stretch> per riempire lo spazio disponibile. Per il posizionamento verticale sono disponibili valori analoghi.  
  
> [!NOTE]
>  Set in modo esplicito <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> delle proprietà su un elemento hanno la precedenza sul <xref:System.Windows.HorizontalAlignment.Stretch> valore della proprietà. Tentativo di impostare <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>e una <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> pari a `Stretch` comporta il `Stretch` richiesta verrà ignorato.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>Proprietà HorizontalAlignment  
 Il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dichiara le caratteristiche di allineamento orizzontale da applicare agli elementi figlio. Nella tabella seguente viene illustrato ognuno dei valori possibili del <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.  
  
|Member|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Gli elementi figlio sono allineati a sinistra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Gli elementi figlio sono allineati a destra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. Explicit <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> valori hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti del posizionamento della ognuno <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore sono visibili nell'illustrazione.  
  
 ![Esempio di HorizontalAlignment](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>Proprietà VerticalAlignment  
 Il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà descrive le caratteristiche di allineamento verticale da applicare agli elementi figlio. Nella tabella seguente viene illustrato ognuno dei valori possibili per il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà.  
  
|Member|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Gli elementi figlio sono allineati in alto nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Gli elementi figlio sono allineati in basso nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. Explicit <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> valori hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering. Ai fini di questo esempio, un <xref:System.Windows.Controls.Grid> elemento visibile linee della griglia viene usato come elemento padre, per illustrare meglio il comportamento di layout di ogni valore della proprietà.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti del posizionamento della ognuno <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> valore sono visibili nell'illustrazione.  
  
 ![Esempio di proprietà VerticalAlignment](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>Informazioni sulla proprietà Margin  
 Il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà descrive la distanza tra un elemento e il figlio o peer. <xref:System.Windows.FrameworkElement.Margin%2A> i valori possono essere uniformi, usando una sintassi come `Margin="20"`. Con questa sintassi, un valore uniforme <xref:System.Windows.FrameworkElement.Margin%2A> di 20 dispositivi independent pixel viene applicato all'elemento. <xref:System.Windows.FrameworkElement.Margin%2A> i valori possono anche assumere la forma di quattro valori distinti, ognuno che descrive un margine distinto da applicare a sinistra, superiore, destro e inferiore (in questo ordine), ad esempio `Margin="0,10,5,25"`. Uso appropriato del <xref:System.Windows.FrameworkElement.Margin%2A> proprietà consente un controllo molto accurato della posizione di rendering di un elemento e la posizione per il rendering dei relativi elementi adiacenti e figlio.  
  
> [!NOTE]
>  Un margine diverso da zero applica uno spazio all'esterno dell'elemento <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 Nell'esempio seguente viene illustrato come applicare margini uniformi intorno a un gruppo di <xref:System.Windows.Controls.Button> elementi. Il <xref:System.Windows.Controls.Button> gli elementi sono disposti con un buffer di margine di 10 pixel in tutte le direzioni.  
  
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
 Padding è simile a <xref:System.Windows.FrameworkElement.Margin%2A> per molti aspetti. La proprietà Padding è esposta solo su poche classi, principalmente per praticità: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, e <xref:System.Windows.Controls.TextBlock> sono esempi di classi che espongono una proprietà Padding. Il <xref:System.Windows.Controls.Border.Padding%2A> proprietà ne aumenta le dimensioni effettive di un elemento figlio specificato <xref:System.Windows.Thickness> valore.  
  
 Nell'esempio seguente viene illustrato come applicare <xref:System.Windows.Controls.Border.Padding%2A> a un elemento padre <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Uso di allineamento, margini e spaziatura interna in un'applicazione  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> forniscono il controllo sul posizionamento necessario per creare un oggetto complesso [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. È possibile usare gli effetti di ogni proprietà per modificare il posizionamento degli elementi figlio, ottenendo in questo modo flessibilità nella creazione di applicazioni ed esperienze utente dinamiche.  
  
 L'esempio seguente illustra ognuno dei concetti descritti in questo argomento. Sulla base dell'infrastruttura descritta nel primo esempio in questo argomento, questo esempio viene aggiunto un <xref:System.Windows.Controls.Grid> come figlio dell'elemento di <xref:System.Windows.Controls.Border> nel primo esempio. <xref:System.Windows.Controls.Border.Padding%2A> viene applicato all'elemento padre <xref:System.Windows.Controls.Border> elemento. Il <xref:System.Windows.Controls.Grid> viene usato per partizionare lo spazio tra tre figlio <xref:System.Windows.Controls.StackPanel> elementi. <xref:System.Windows.Controls.Button> gli elementi vengono usati anche in questo caso per mostrare i vari effetti delle <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>. <xref:System.Windows.Controls.TextBlock> gli elementi vengono aggiunti a ogni <xref:System.Windows.Controls.ColumnDefinition> per ottimizzare le varie proprietà applicate per la definizione di <xref:System.Windows.Controls.Button> elementi in ogni colonna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Dopo la compilazione, l'applicazione precedente genera un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di aspetto simile al seguente. Gli effetti dei vari valori delle proprietà sono evidenti nella spaziatura tra gli elementi e i valori di proprietà significativi per gli elementi in ogni colonna vengono visualizzati tra parentesi <xref:System.Windows.Controls.TextBlock> elementi.  
  
 ![Alcune proprietà di posizionamento in un'applicazione](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>Argomenti successivi  
 Proprietà di posizionamento definite per il <xref:System.Windows.FrameworkElement> classe consentono un controllo accurato del posizionamento degli elementi all'interno di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni. Quelle descritte qui sono dunque le diverse tecniche che permettono di posizionare in modo più efficace gli elementi usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Sono inoltre disponibili ulteriori risorse in cui il layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene descritto in modo più particolareggiato. Il [Panoramica di pannelli](../controls/panels-overview.md) argomento contiene più in dettaglio i vari <xref:System.Windows.Controls.Panel> elementi. L'argomento [procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md) vengono presentate tecniche avanzate che usano gli elementi di layout per posizionare i componenti e associare le relative azioni a origini dati.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Cenni preliminari sugli elementi Panel](../controls/panels-overview.md)
- [Layout](layout.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
