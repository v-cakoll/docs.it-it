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
ms.openlocfilehash: 32e8ab7104b8ea2f985395065868ed154ca1e378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181957"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Introduzione all'oggetto GlyphRun e all'elemento Glyphs
In questo argomento <xref:System.Windows.Media.GlyphRun> vengono <xref:System.Windows.Documents.Glyphs> descritti l'oggetto e l'elemento.  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a>Introduzione a GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]fornisce supporto avanzato per il testo, <xref:System.Windows.Documents.Glyphs> incluso il markup a livello di glifo con accesso diretto a i clienti che desiderano intercettare e rendere persistente il testo dopo la formattazione. Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.  
  
1. Visualizzazione di documenti a formato fisso.  
  
2. Scenari di stampa.  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] come linguaggio della stampante.  
  
    - Microsoft XPS Document Writer.  
  
    - Driver della stampante precedenti, output delle applicazioni Win32 nel formato fisso.  
  
    - Formato dello spooling di stampa.  
  
3. Rappresentazione dei documenti in formato fisso, inclusi i client per le versioni precedenti di Windows e altri dispositivi di elaborazione.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>e <xref:System.Windows.Media.GlyphRun> sono progettati per la presentazione di documenti in formato fisso e scenari di stampa. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]fornisce diversi elementi per [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] il <xref:System.Windows.Controls.Label> layout <xref:System.Windows.Controls.TextBlock>generale e scenari quali e . Per ulteriori informazioni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sul layout e sugli scenari, vedere [la tipografia in WPF.](typography-in-wpf.md)  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a>Oggetto GlyphRun  
 L'oggetto <xref:System.Windows.Media.GlyphRun> rappresenta una sequenza di glifi da una singola faccia di un singolo tipo di carattere con una singola dimensione e con un singolo stile di rendering.  
  
 <xref:System.Windows.Media.GlyphRun>include entrambi i dettagli <xref:System.Windows.Documents.Glyphs.Indices%2A> del tipo di carattere, ad esempio le posizioni dei glifi e dei singoli glifi. Include inoltre i punti di codice Unicode originali da cui è stata generata l'esecuzione, le informazioni di mapping dell'offset del buffer da carattere a glifo e i flag per carattere e per glifo.  
  
 <xref:System.Windows.Media.GlyphRun>dispone di un <xref:System.Windows.FrameworkElement>livello <xref:System.Windows.Documents.Glyphs>di alto livello corrispondente, . <xref:System.Windows.Documents.Glyphs>può essere utilizzato nella struttura [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ad <xref:System.Windows.Media.GlyphRun> albero dell'elemento e nel markup per rappresentare l'output.  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a>Elemento Glyphs  
 L'elemento <xref:System.Windows.Documents.Glyphs> rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. La sintassi del markup <xref:System.Windows.Documents.Glyphs> seguente viene utilizzata per descrivere l'elemento.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Le definizioni di proprietà seguenti corrispondono ai primi quattro attributi del markup di esempio.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Specifica un identificatore di risorsa: nome file, URI (Uniform Resource Identifier) Web o riferimento a risorse nel file exe o nel contenitore dell'applicazione.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Specifica le dimensioni del carattere nelle unità della superficie di disegno (l'impostazione predefinita è 0,96 pollici).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Specifica i flag per gli stili grassetto e corsivo.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Specifica il livello di layout bidirezionale. I valori pari e lo zero implicano un layout da sinistra a destra, mentre i valori dispari implicano un layout da destra a sinistra.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a>Proprietà Indices  
 La <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà è una stringa di specifiche del glifo. Quando una sequenza di glifi forma un cluster singolo, la specifica del primo glifo nel cluster viene preceduta da una specifica del numero di glifi e di punti di codice combinati per formare il cluster. La <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà raccoglie in una stringa le proprietà seguenti.  
  
- Indici del glifo  
  
- Distanze di avanzamento del glifo  
  
- Combinazione dei vettori di connessione dei glifi  
  
- Mapping del cluster tra i punti di codice e i glifi  
  
- Flag del glifo  
  
 Ogni specifica del glifo presenta la forma seguente:  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a>Metrica del glifo  
 Ogni glifo definisce le metriche <xref:System.Windows.Documents.Glyphs>che specificano la modalità di allineamento con altri file . Nell'immagine seguente vengono definite le varie qualità tipografiche di due diversi caratteri glifi.  
  
 ![Diagramma delle misure dei glifi](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a>Markup dei glifi  
 Nell'esempio di codice riportato di <xref:System.Windows.Documents.Glyphs> seguito [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]viene illustrato come utilizzare varie proprietà dell'elemento in .  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Testo](optimizing-performance-text.md)
