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
ms.openlocfilehash: 70eff35db638c5bfbc9c164dc381e3f58e18957b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="alignment-margins-and-padding-overview"></a>Panoramica su allineamento, margini e spaziatura interna
La <xref:System.Windows.FrameworkElement> classe espone diverse proprietà che consentono di posizionare con precisione gli elementi figlio. Questo argomento vengono illustrate quattro delle proprietà più importante: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. È fondamentale comprendere gli effetti di queste proprietà, perché forniscono la base per controllare la posizione degli elementi nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>Introduzione al posizionamento degli elementi  
 È possibile posizionare gli elementi in molti modi con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Tuttavia, per ottenere il layout ideale diventa non è sufficiente scegliere destra <xref:System.Windows.Controls.Panel> elemento. Controllo accurato del posizionamento è necessario conoscere il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà.  
  
 La figura seguente illustra uno scenario di layout in cui vengono usate diverse proprietà di posizionamento.  
  
 ![Esempio di proprietà di posizionamento WPF](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 A prima vista, la <xref:System.Windows.Controls.Button> elementi in questa illustrazione vengano visualizzati da inserire in modo casuale. Le posizioni sono in realtà controllate con precisione usando una combinazione di margini, allineamento e spaziatura interna.  
  
 L'esempio seguente descrive come creare il layout nella figura precedente. Oggetto <xref:System.Windows.Controls.Border> elemento incapsula un elemento padre <xref:System.Windows.Controls.StackPanel>, con un <xref:System.Windows.Controls.Border.Padding%2A> valore 15 device independent pixel. Questo account per il "narrow" <xref:System.Windows.Media.Brushes.LightBlue%2A> banda che circonda l'elemento figlio <xref:System.Windows.Controls.StackPanel>. Gli elementi figlio del <xref:System.Windows.Controls.StackPanel> vengono utilizzate per illustrare ognuna delle varie proprietà di posizionamento sono descritte in dettaglio in questo argomento. Tre <xref:System.Windows.Controls.Button> gli elementi vengono utilizzati per illustrare le il <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Il diagramma seguente mostra una visualizzazione dettagliata delle varie proprietà di posizionamento usate nell'esempio precedente. Le sezioni successive di questo argomento descrivono in maggior dettaglio come usare ogni proprietà di posizionamento.  
  
 ![Positioning Properties with Screen Call&#45;outs](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>Informazioni sulle proprietà di allineamento  
 Il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> descrivono come un elemento figlio deve essere posizionato all'interno dello spazio allocato layout di un elemento padre. Usando insieme queste proprietà, è possibile posizionare con precisione gli elementi figlio. Ad esempio, gli elementi figlio di un <xref:System.Windows.Controls.DockPanel> possibile specificare quattro allineamenti orizzontali diversi: <xref:System.Windows.HorizontalAlignment.Left>, <xref:System.Windows.HorizontalAlignment.Right>, o <xref:System.Windows.HorizontalAlignment.Center>, o a <xref:System.Windows.HorizontalAlignment.Stretch> per riempire lo spazio disponibile. Per il posizionamento verticale sono disponibili valori analoghi.  
  
> [!NOTE]
>  In modo esplicito a set <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> hanno la precedenza sulle proprietà di un elemento di <xref:System.Windows.HorizontalAlignment.Stretch> valore della proprietà. Il tentativo di impostare <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>e un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore `Stretch` comporta il `Stretch` richiesta verrà ignorato.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>Proprietà HorizontalAlignment  
 Il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dichiara le caratteristiche di allineamento orizzontale da applicare a elementi figlio. La tabella seguente mostra i valori possibili del <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.  
  
|Member|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Gli elementi figlio sono allineati a sinistra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Gli elementi figlio sono allineati a destra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. Esplicita <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> valori hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti di posizionamento di ogni <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore sono visibili nell'illustrazione.  
  
 ![Esempio di HorizontalAlignment](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>Proprietà VerticalAlignment  
 Il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà descrive le caratteristiche di allineamento da applicare a elementi figlio. La tabella seguente mostra i valori possibili per il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà.  
  
|Member|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Gli elementi figlio sono allineati in alto nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Gli elementi figlio sono allineati in basso nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. Esplicita <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> valori hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering. Ai fini di questo esempio, un <xref:System.Windows.Controls.Grid> elemento con griglia visibile viene utilizzato come elemento padre, per illustrare il comportamento di layout di ogni valore della proprietà.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti di posizionamento di ogni <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> valore sono visibili nell'illustrazione.  
  
 ![Esempio di proprietà VerticalAlignment](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>Informazioni sulla proprietà Margin  
 Il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà descrive la distanza tra un elemento e il figlio o peer. <xref:System.Windows.FrameworkElement.Margin%2A> i valori possono essere uniformi, con sintassi analoga a `Margin="20"`. Con questa sintassi, un uniform <xref:System.Windows.FrameworkElement.Margin%2A> di 20 dispositivi independent pixel viene applicata all'elemento. <xref:System.Windows.FrameworkElement.Margin%2A> i valori possono anche assumere la forma di quattro valori distinct, ogni valore che descrive un margine distinto da applicare a sinistra, superiore, destro e inferiore (in tale ordine), ad esempio `Margin="0,10,5,25"`. Utilizzo corretto del <xref:System.Windows.FrameworkElement.Margin%2A> proprietà consente un controllo molto accurato della posizione di rendering di un elemento e la posizione di rendering adiacente e degli elementi figlio.  
  
> [!NOTE]
>  Un margine diverso da zero applica uno spazio all'esterno dell'elemento <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 Nell'esempio seguente viene illustrato come applicare margini uniformi intorno a un gruppo di <xref:System.Windows.Controls.Button> elementi. Il <xref:System.Windows.Controls.Button> elementi sono disposti a con un margine di 10 pixel in tutte le direzioni.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 In diverse situazioni un margine uniforme non è appropriato. In questi casi, è possibile applicare una spaziatura non uniforme. L'esempio seguente illustra come applicare una spaziatura dei margini non uniforme agli elementi figlio. I margini sono descritti in quest'ordine: sinistro, superiore, destro, inferiore.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>Informazioni sulla proprietà Padding  
 Spaziatura interna è simile a <xref:System.Windows.FrameworkElement.Margin%2A> per molti aspetti. La proprietà di riempimento viene esposta solo su alcune classi, principalmente per praticità: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, e <xref:System.Windows.Controls.TextBlock> sono esempi di classi che espongono una proprietà di riempimento. Il <xref:System.Windows.Controls.Border.Padding%2A> proprietà ne aumenta le dimensioni effettive di un elemento figlio specificato <xref:System.Windows.Thickness> valore.  
  
 Nell'esempio seguente viene illustrato come applicare <xref:System.Windows.Controls.Border.Padding%2A> a un elemento padre <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Uso di allineamento, margini e spaziatura interna in un'applicazione  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> forniscono il controllo sul posizionamento necessario per creare un oggetto complesso [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. È possibile usare gli effetti di ogni proprietà per modificare il posizionamento degli elementi figlio, ottenendo in questo modo flessibilità nella creazione di applicazioni ed esperienze utente dinamiche.  
  
 L'esempio seguente illustra ognuno dei concetti descritti in questo argomento. Sulla base dell'infrastruttura descritta nel primo esempio di questo argomento, in questo esempio viene aggiunto un <xref:System.Windows.Controls.Grid> come figlio dell'elemento di <xref:System.Windows.Controls.Border> nel primo esempio. <xref:System.Windows.Controls.Border.Padding%2A> viene applicata all'elemento padre <xref:System.Windows.Controls.Border> elemento. Il <xref:System.Windows.Controls.Grid> viene utilizzata per partizionare spazio tra tre <xref:System.Windows.Controls.StackPanel> elementi. <xref:System.Windows.Controls.Button> gli elementi vengono utilizzati per illustrare i vari effetti <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>. <xref:System.Windows.Controls.TextBlock> gli elementi vengono aggiunti a ogni <xref:System.Windows.Controls.ColumnDefinition> per definire meglio le varie proprietà applicate per il <xref:System.Windows.Controls.Button> elementi in ogni colonna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Dopo la compilazione, l'applicazione precedente genera un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di aspetto simile al seguente. Gli effetti dei vari valori delle proprietà sono evidenti nella spaziatura tra gli elementi e i valori delle proprietà significativi per gli elementi in ogni colonna vengono visualizzati all'interno di <xref:System.Windows.Controls.TextBlock> elementi.  
  
 ![Alcune proprietà di posizionamento in un'applicazione](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>Argomenti successivi  
 Proprietà definite per il posizionamento di <xref:System.Windows.FrameworkElement> classe consentono un controllo accurato del posizionamento degli elementi all'interno di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni. Quelle descritte qui sono dunque le diverse tecniche che permettono di posizionare in modo più efficace gli elementi usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Sono inoltre disponibili ulteriori risorse in cui il layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene descritto in modo più particolareggiato. Il [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md) argomento contiene ulteriori informazioni sui vari <xref:System.Windows.Controls.Panel> elementi. L'argomento [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) vengono presentate le tecniche avanzate che utilizzano gli elementi di layout per posizionare i componenti e le relative azioni di associare a origini dati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.Margin%2A>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Esempio di raccolte di layout WPF](http://go.microsoft.com/fwlink/?LinkID=160054)
