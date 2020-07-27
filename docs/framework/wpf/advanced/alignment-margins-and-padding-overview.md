---
title: Panoramica su allineamento, margini e spaziatura interna
description: Informazioni su HorizontalAlignment, Margin, Padding e VerticalAlignment, che controllano la posizione degli elementi figlio nelle applicazioni Windows Presentation Foundation.
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
ms.openlocfilehash: 832325086c85a7b044876e825d93e0b680a0b99c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165892"
---
# <a name="alignment-margins-and-padding-overview"></a>Panoramica su allineamento, margini e spaziatura interna
La <xref:System.Windows.FrameworkElement> classe espone diverse proprietà che vengono usate per posizionare con precisione gli elementi figlio. In questo argomento vengono illustrate quattro delle proprietà più importanti: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> , <xref:System.Windows.FrameworkElement.Margin%2A> , <xref:System.Windows.Controls.Border.Padding%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> . È fondamentale comprendere gli effetti di queste proprietà, perché forniscono la base per controllare la posizione degli elementi nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>Introduzione al posizionamento degli elementi  
 È possibile posizionare gli elementi in molti modi con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Tuttavia, il raggiungimento del layout ideale va oltre la semplice scelta dell' <xref:System.Windows.Controls.Panel> elemento corretto. Per un controllo accurato del posizionamento è necessario conoscere le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.Margin%2A> proprietà,, <xref:System.Windows.Controls.Border.Padding%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> .  
  
 La figura seguente illustra uno scenario di layout in cui vengono usate diverse proprietà di posizionamento.  
  
 ![Esempio di proprietà di posizionamento WPF](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 A prima vista, gli <xref:System.Windows.Controls.Button> elementi in questa illustrazione potrebbero sembrare posizionati in modo casuale. Le posizioni sono in realtà controllate con precisione usando una combinazione di margini, allineamento e spaziatura interna.  
  
 L'esempio seguente descrive come creare il layout nella figura precedente. Un <xref:System.Windows.Controls.Border> elemento incapsula un elemento padre <xref:System.Windows.Controls.StackPanel> con un <xref:System.Windows.Controls.Border.Padding%2A> valore di 15 pixel indipendenti dal dispositivo. Questo account per la <xref:System.Windows.Media.Brushes.LightBlue%2A> banda stretta che racchiude l'elemento figlio <xref:System.Windows.Controls.StackPanel> . Gli elementi figlio di <xref:System.Windows.Controls.StackPanel> vengono utilizzati per illustrare ognuna delle varie proprietà di posizionamento descritte in dettaglio in questo argomento. <xref:System.Windows.Controls.Button>Vengono usati tre elementi per illustrare le <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà e.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Il diagramma seguente mostra una visualizzazione dettagliata delle varie proprietà di posizionamento usate nell'esempio precedente. Le sezioni successive di questo argomento descrivono in maggior dettaglio come usare ogni proprietà di posizionamento.  
  
 ![Posizionamento delle proprietà con la chiamata allo schermo&#45;out](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>Informazioni sulle proprietà di allineamento  
 Le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà e descrivono come posizionare un elemento figlio all'interno dello spazio di layout allocato di un elemento padre. Usando insieme queste proprietà, è possibile posizionare con precisione gli elementi figlio. Gli elementi figlio di un oggetto possono ad esempio <xref:System.Windows.Controls.DockPanel> specificare quattro diversi allineamenti orizzontali, ovvero, <xref:System.Windows.HorizontalAlignment.Left> o oppure <xref:System.Windows.HorizontalAlignment.Right> <xref:System.Windows.HorizontalAlignment.Center> su <xref:System.Windows.HorizontalAlignment.Stretch> per riempire lo spazio disponibile. Per il posizionamento verticale sono disponibili valori analoghi.  
  
> [!NOTE]
> Le proprietà impostate in modo esplicito <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> su un elemento hanno la precedenza sul <xref:System.Windows.HorizontalAlignment.Stretch> valore della proprietà. Il tentativo di impostare <xref:System.Windows.FrameworkElement.Height%2A> , <xref:System.Windows.FrameworkElement.Width%2A> e un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore dei `Stretch` risultati nella `Stretch` richiesta viene ignorato.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>Proprietà HorizontalAlignment  
 La <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Proprietà dichiara le caratteristiche di allineamento orizzontale da applicare agli elementi figlio. Nella tabella seguente vengono illustrati i valori possibili della <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Proprietà.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Gli elementi figlio sono allineati a sinistra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Gli elementi figlio sono allineati a destra dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. <xref:System.Windows.FrameworkElement.Width%2A>I valori e espliciti <xref:System.Windows.FrameworkElement.Height%2A> hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà agli <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti del posizionamento di ogni <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore sono visibili nella figura.  
  
 ![Esempio di HorizontalAlignment](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>Proprietà VerticalAlignment  
 La <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà descrive le caratteristiche di allineamento verticale da applicare agli elementi figlio. Nella tabella seguente vengono illustrati tutti i valori possibili per la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Proprietà.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Gli elementi figlio sono allineati in alto nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Center>|Gli elementi figlio sono allineati al centro dello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Gli elementi figlio sono allineati in basso nello spazio di layout allocato dell'elemento padre.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (impostazione predefinita)|Gli elementi figlio vengono estesi fino a riempire lo spazio di layout allocato dell'elemento padre. <xref:System.Windows.FrameworkElement.Width%2A>I valori e espliciti <xref:System.Windows.FrameworkElement.Height%2A> hanno la precedenza.|  
  
 Nell'esempio seguente viene illustrato come applicare la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà agli <xref:System.Windows.Controls.Button> elementi. Vengono visualizzati tutti i valori di attributo per illustrare i diversi comportamenti di rendering. Ai fini di questo esempio, <xref:System.Windows.Controls.Grid> viene utilizzato un elemento con linee della griglia visibile come elemento padre, per illustrare meglio il comportamento del layout di ogni valore della proprietà.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Il risultato del codice precedente è simile a quello riportato nell'immagine seguente. Gli effetti del posizionamento di ogni <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> valore sono visibili nella figura.  
  
 ![Esempio di proprietà VerticalAlignment](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>Informazioni sulla proprietà Margin  
 La <xref:System.Windows.FrameworkElement.Margin%2A> proprietà descrive la distanza tra un elemento e i relativi elementi figlio o peer. <xref:System.Windows.FrameworkElement.Margin%2A>i valori possono essere uniformi usando una sintassi simile a `Margin="20"` . Con questa sintassi, <xref:System.Windows.FrameworkElement.Margin%2A> all'elemento viene applicata un'uniforme di 20 pixel indipendenti dal dispositivo. <xref:System.Windows.FrameworkElement.Margin%2A>i valori possono anche assumere il formato di quattro valori distinti, ognuno dei quali descrive un margine distinto da applicare a sinistra, in alto, a destra e in basso (in questo ordine), ad esempio `Margin="0,10,5,25"` . L'uso corretto della <xref:System.Windows.FrameworkElement.Margin%2A> proprietà consente un controllo molto preciso della posizione di rendering di un elemento e della posizione di rendering degli elementi adiacenti e degli elementi figlio.  
  
> [!NOTE]
> Un margine diverso da zero applica uno spazio all'esterno degli elementi <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> .  
  
 Nell'esempio seguente viene illustrato come applicare margini uniformi intorno a un gruppo di <xref:System.Windows.Controls.Button> elementi. Gli <xref:System.Windows.Controls.Button> elementi sono spaziati uniformemente con un buffer di margine di dieci pixel in ogni direzione.  
  
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
 La spaziatura interna è simile alla <xref:System.Windows.FrameworkElement.Margin%2A> maggior parte degli aspetti. La proprietà Padding viene esposta solo in alcune classi, principalmente per praticità:,, <xref:System.Windows.Documents.Block> <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Control> e <xref:System.Windows.Controls.TextBlock> sono esempi di classi che espongono una proprietà Padding. La <xref:System.Windows.Controls.Border.Padding%2A> proprietà consente di ingrandire le dimensioni effettive di un elemento figlio in base al <xref:System.Windows.Thickness> valore specificato.  
  
 Nell'esempio seguente viene illustrato come applicare <xref:System.Windows.Controls.Border.Padding%2A> a un <xref:System.Windows.Controls.Border> elemento padre.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Uso di allineamento, margini e spaziatura interna in un'applicazione  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> , <xref:System.Windows.Controls.Border.Padding%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> forniscono il controllo di posizionamento necessario per creare un oggetto complesso [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . È possibile usare gli effetti di ogni proprietà per modificare il posizionamento degli elementi figlio, ottenendo in questo modo flessibilità nella creazione di applicazioni ed esperienze utente dinamiche.  
  
 L'esempio seguente illustra ognuno dei concetti descritti in questo argomento. Basandosi sull'infrastruttura disponibile nel primo esempio di questo argomento, in questo esempio viene aggiunto un <xref:System.Windows.Controls.Grid> elemento come figlio di <xref:System.Windows.Controls.Border> nel primo esempio. <xref:System.Windows.Controls.Border.Padding%2A>viene applicato all'elemento padre <xref:System.Windows.Controls.Border> . <xref:System.Windows.Controls.Grid>Viene usato per partizionare lo spazio tra tre <xref:System.Windows.Controls.StackPanel> elementi figlio. <xref:System.Windows.Controls.Button>gli elementi vengono nuovamente utilizzati per visualizzare i vari effetti di <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> . <xref:System.Windows.Controls.TextBlock>gli elementi vengono aggiunti a ognuno <xref:System.Windows.Controls.ColumnDefinition> per definire meglio le varie proprietà applicate agli <xref:System.Windows.Controls.Button> elementi in ogni colonna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Dopo la compilazione, l'applicazione precedente genera un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di aspetto simile al seguente. Gli effetti dei vari valori delle proprietà sono evidenti nella spaziatura tra gli elementi e i valori di proprietà significativi per gli elementi di ogni colonna vengono visualizzati all'interno di <xref:System.Windows.Controls.TextBlock> elementi.  
  
 ![Alcune proprietà di posizionamento in un'applicazione](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>Passaggi successivi  
 Le proprietà di posizionamento definite dalla <xref:System.Windows.FrameworkElement> classe consentono un controllo accurato del posizionamento degli elementi all'interno delle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni. Quelle descritte qui sono dunque le diverse tecniche che permettono di posizionare in modo più efficace gli elementi usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Sono inoltre disponibili ulteriori risorse in cui il layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene descritto in modo più particolareggiato. Nell'argomento [Panoramica dei pannelli](../controls/panels-overview.md) sono disponibili informazioni più dettagliate sui vari <xref:System.Windows.Controls.Panel> elementi. L'argomento [procedura dettagliata: la prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md) introduce tecniche avanzate che usano elementi di layout per posizionare i componenti e associare le azioni alle origini dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Cenni preliminari sugli elementi Panel](../controls/panels-overview.md)
- [Layout](layout.md)
- [Esempio di raccolte di layout WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
