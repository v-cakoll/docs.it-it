---
title: Introduzione all'oggetto GlyphRun e all'elemento Glyphs
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 5750177c03cf859ebb884c5774b7ded03fa60628
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Introduzione all'oggetto GlyphRun e all'elemento Glyphs
Questo argomento viene descritto il <xref:System.Windows.Media.GlyphRun> oggetto e il <xref:System.Windows.Documents.Glyphs> elemento.  
  
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Introduzione a GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il supporto di testo avanzato, incluso il markup a livello di glifo con accesso diretto a <xref:System.Windows.Documents.Glyphs> per i clienti che desiderano intercettare e rendere persistenti testo dopo la formattazione. Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.  
  
1.  Visualizzazione di documenti a formato fisso.  
  
2.  Scenari di stampa.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] come linguaggio della stampante.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Driver della stampante precedenti, output delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] in formato fisso.  
  
    -   Formato dello spooling di stampa.  
  
3.  Rappresentazione di documenti con formato fisso, inclusi i client di versioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e altri dispositivi di elaborazione.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun> sono progettati per la presentazione del documento a formato fisso e scenari di stampa. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vengono forniti diversi elementi per il layout generale e [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenari, ad esempio <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.TextBlock>. Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Oggetto GlyphRun  
 Il <xref:System.Windows.Media.GlyphRun> oggetto rappresenta una sequenza di glifi da una singola icona di un singolo tipo di carattere in una singola dimensione, con un unico stile di rendering.  
  
 <xref:System.Windows.Media.GlyphRun> include i dettagli relativi al tipo di carattere, ad esempio glifo <xref:System.Windows.Documents.Glyphs.Indices%2A> e posizioni dei singoli glifi. Include inoltre originale [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] l'esecuzione è stato generato da informazioni di mapping dell'offset del buffer al glifo di caratteri e i flag per ogni carattere e ogni glifo di punti di codice.  
  
 <xref:System.Windows.Media.GlyphRun> ha un alto livello corrispondente <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>. <xref:System.Windows.Documents.Glyphs> può essere utilizzato nell'albero degli elementi e nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup per rappresentare <xref:System.Windows.Media.GlyphRun> output.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Elemento Glyphs  
 Il <xref:System.Windows.Documents.Glyphs> elemento rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. La sintassi di codice seguente viene utilizzata per descrivere il <xref:System.Windows.Documents.Glyphs> elemento.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Le definizioni di proprietà seguenti corrispondono ai primi quattro attributi del markup di esempio.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Specifica un identificatore di risorsa: nome del file Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], o riferimento a una risorsa nell'applicazione .exe o nel contenitore.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Specifica le dimensioni del carattere nelle unità della superficie di disegno (l'impostazione predefinita è 0,96 pollici).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Specifica i flag per gli stili grassetto e corsivo.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Specifica il livello di layout bidirezionale. I valori pari e lo zero implicano un layout da sinistra a destra, mentre i valori dispari implicano un layout da destra a sinistra.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Proprietà Indices  
 Il <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà è una stringa di specifiche del glifo. Quando una sequenza di glifi forma un cluster singolo, la specifica del primo glifo nel cluster viene preceduta da una specifica del numero di glifi e di punti di codice combinati per formare il cluster. Il <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà raccoglie in una stringa le proprietà seguenti.  
  
-   Indici del glifo  
  
-   Distanze di avanzamento del glifo  
  
-   Combinazione dei vettori di connessione dei glifi  
  
-   Mapping del cluster tra i punti di codice e i glifi  
  
-   Flag del glifo  
  
 Ogni specifica del glifo presenta la forma seguente:  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Metrica del glifo  
 Ogni glifo definisce la metrica che specifica la modalità di allineamento con altri <xref:System.Windows.Documents.Glyphs>. Nell'immagine seguente vengono definite le varie qualità tipografiche di due diversi caratteri glifi.  
  
 ![Diagramma delle misure dei glifi](../../../../docs/framework/wpf/advanced/media/glyph-example.png "esempio_glifo")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Markup dei glifi  
 Esempio di codice seguente viene illustrato come utilizzare diverse proprietà del <xref:System.Windows.Documents.Glyphs> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
