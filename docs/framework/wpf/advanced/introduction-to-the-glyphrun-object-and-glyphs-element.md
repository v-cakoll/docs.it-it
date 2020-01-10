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
ms.openlocfilehash: 9af07d48877fee0e94f8e5fa2556c4361795df6a
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740365"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Introduzione all'oggetto GlyphRun e all'elemento Glyphs
In questo argomento vengono descritti l'oggetto <xref:System.Windows.Media.GlyphRun> e l'elemento <xref:System.Windows.Documents.Glyphs>.  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Introduzione a GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre supporto avanzato per il testo, incluso il markup a livello di glifo, con accesso diretto ai <xref:System.Windows.Documents.Glyphs> per i clienti che desiderano intercettare e mantenere il testo dopo la formattazione. Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.  
  
1. Visualizzazione di documenti a formato fisso.  
  
2. Scenari di stampa.  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] come linguaggio della stampante.  
  
    - Microsoft XPS Document Writer.  
  
    - Driver della stampante precedenti, output delle applicazioni Win32 nel formato fisso.  
  
    - Formato dello spooling di stampa.  
  
3. Rappresentazione di documenti a formato fisso, inclusi i client per le versioni precedenti di Windows e altri dispositivi di elaborazione.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun> sono progettati per scenari di presentazione e stampa di documenti a formato fisso. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce diversi elementi per il layout generale e scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], ad esempio <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.TextBlock>. Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Oggetto GlyphRun  
 L'oggetto <xref:System.Windows.Media.GlyphRun> rappresenta una sequenza di glifi da una singola faccia di un singolo tipo di carattere a una singola dimensione e con un unico stile di rendering.  
  
 <xref:System.Windows.Media.GlyphRun> include sia i dettagli del tipo di carattere, ad esempio le posizioni del glifo <xref:System.Windows.Documents.Glyphs.Indices%2A> che le singole icone. Include anche i punti di codice Unicode originali da cui è stata generata l'esecuzione, le informazioni sul mapping dell'offset del buffer da carattere a glifo e i flag per carattere e per glifo.  
  
 <xref:System.Windows.Media.GlyphRun> dispone di un <xref:System.Windows.FrameworkElement>di alto livello corrispondente, <xref:System.Windows.Documents.Glyphs>. <xref:System.Windows.Documents.Glyphs> possibile utilizzare nell'albero degli elementi e in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup per rappresentare <xref:System.Windows.Media.GlyphRun> output.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Elemento Glyphs  
 L'elemento <xref:System.Windows.Documents.Glyphs> rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Per descrivere l'elemento <xref:System.Windows.Documents.Glyphs>, viene utilizzata la sintassi di markup seguente.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Le definizioni di proprietà seguenti corrispondono ai primi quattro attributi del markup di esempio.  
  
|Gli|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Specifica un identificatore di risorsa: il nome file, l'URI (Uniform Resource Identifier) Web o il riferimento a una risorsa nell'applicazione. exe o nel contenitore.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Specifica le dimensioni del carattere nelle unità della superficie di disegno (l'impostazione predefinita è 0,96 pollici).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Specifica i flag per gli stili grassetto e corsivo.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Specifica il livello di layout bidirezionale. I valori pari e lo zero implicano un layout da sinistra a destra, mentre i valori dispari implicano un layout da destra a sinistra.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Proprietà Indices  
 La proprietà <xref:System.Windows.Documents.Glyphs.Indices%2A> è una stringa di specifiche di glifi. Quando una sequenza di glifi forma un cluster singolo, la specifica del primo glifo nel cluster viene preceduta da una specifica del numero di glifi e di punti di codice combinati per formare il cluster. La proprietà <xref:System.Windows.Documents.Glyphs.Indices%2A> raccoglie in una stringa le proprietà seguenti.  
  
- Indici del glifo  
  
- Distanze di avanzamento del glifo  
  
- Combinazione dei vettori di connessione dei glifi  
  
- Mapping del cluster tra i punti di codice e i glifi  
  
- Flag del glifo  
  
 Ogni specifica del glifo presenta la forma seguente:  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Metrica del glifo  
 Ogni glifo definisce le metriche che specificano la modalità di allineamento con altre <xref:System.Windows.Documents.Glyphs>. Nell'immagine seguente vengono definite le varie qualità tipografiche di due diversi caratteri glifi.  
  
 ![Diagramma delle misurazioni del glifo](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Markup dei glifi  
 Nell'esempio di codice seguente viene illustrato come utilizzare varie proprietà dell'elemento <xref:System.Windows.Documents.Glyphs> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Testo](optimizing-performance-text.md)
