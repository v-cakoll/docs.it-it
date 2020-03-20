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
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="99977-102">Introduzione all'oggetto GlyphRun e all'elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="99977-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="99977-103">In questo argomento <xref:System.Windows.Media.GlyphRun> vengono <xref:System.Windows.Documents.Glyphs> descritti l'oggetto e l'elemento.</span><span class="sxs-lookup"><span data-stu-id="99977-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="99977-104">Introduzione a GlyphRun</span><span class="sxs-lookup"><span data-stu-id="99977-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="99977-105">fornisce supporto avanzato per il testo, <xref:System.Windows.Documents.Glyphs> incluso il markup a livello di glifo con accesso diretto a i clienti che desiderano intercettare e rendere persistente il testo dopo la formattazione.</span><span class="sxs-lookup"><span data-stu-id="99977-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="99977-106">Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="99977-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="99977-107">Visualizzazione di documenti a formato fisso.</span><span class="sxs-lookup"><span data-stu-id="99977-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="99977-108">Scenari di stampa.</span><span class="sxs-lookup"><span data-stu-id="99977-108">Print scenarios.</span></span>  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="99977-109">come linguaggio della stampante.</span><span class="sxs-lookup"><span data-stu-id="99977-109">as a device printer language.</span></span>  
  
    - <span data-ttu-id="99977-110">Microsoft XPS Document Writer.</span><span class="sxs-lookup"><span data-stu-id="99977-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="99977-111">Driver della stampante precedenti, output delle applicazioni Win32 nel formato fisso.</span><span class="sxs-lookup"><span data-stu-id="99977-111">Previous printer drivers, output from Win32 applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="99977-112">Formato dello spooling di stampa.</span><span class="sxs-lookup"><span data-stu-id="99977-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="99977-113">Rappresentazione dei documenti in formato fisso, inclusi i client per le versioni precedenti di Windows e altri dispositivi di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="99977-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99977-114"><xref:System.Windows.Documents.Glyphs>e <xref:System.Windows.Media.GlyphRun> sono progettati per la presentazione di documenti in formato fisso e scenari di stampa.</span><span class="sxs-lookup"><span data-stu-id="99977-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="99977-115">fornisce diversi elementi per [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] il <xref:System.Windows.Controls.Label> layout <xref:System.Windows.Controls.TextBlock>generale e scenari quali e .</span><span class="sxs-lookup"><span data-stu-id="99977-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="99977-116">Per ulteriori informazioni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sul layout e sugli scenari, vedere [la tipografia in WPF.](typography-in-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="99977-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a><span data-ttu-id="99977-117">Oggetto GlyphRun</span><span class="sxs-lookup"><span data-stu-id="99977-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="99977-118">L'oggetto <xref:System.Windows.Media.GlyphRun> rappresenta una sequenza di glifi da una singola faccia di un singolo tipo di carattere con una singola dimensione e con un singolo stile di rendering.</span><span class="sxs-lookup"><span data-stu-id="99977-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="99977-119"><xref:System.Windows.Media.GlyphRun>include entrambi i dettagli <xref:System.Windows.Documents.Glyphs.Indices%2A> del tipo di carattere, ad esempio le posizioni dei glifi e dei singoli glifi.</span><span class="sxs-lookup"><span data-stu-id="99977-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="99977-120">Include inoltre i punti di codice Unicode originali da cui è stata generata l'esecuzione, le informazioni di mapping dell'offset del buffer da carattere a glifo e i flag per carattere e per glifo.</span><span class="sxs-lookup"><span data-stu-id="99977-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="99977-121"><xref:System.Windows.Media.GlyphRun>dispone di un <xref:System.Windows.FrameworkElement>livello <xref:System.Windows.Documents.Glyphs>di alto livello corrispondente, .</span><span class="sxs-lookup"><span data-stu-id="99977-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="99977-122"><xref:System.Windows.Documents.Glyphs>può essere utilizzato nella struttura [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ad <xref:System.Windows.Media.GlyphRun> albero dell'elemento e nel markup per rappresentare l'output.</span><span class="sxs-lookup"><span data-stu-id="99977-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a><span data-ttu-id="99977-123">Elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="99977-123">The Glyphs Element</span></span>  
 <span data-ttu-id="99977-124">L'elemento <xref:System.Windows.Documents.Glyphs> rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99977-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="99977-125">La sintassi del markup <xref:System.Windows.Documents.Glyphs> seguente viene utilizzata per descrivere l'elemento.</span><span class="sxs-lookup"><span data-stu-id="99977-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="99977-126">Le definizioni di proprietà seguenti corrispondono ai primi quattro attributi del markup di esempio.</span><span class="sxs-lookup"><span data-stu-id="99977-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="99977-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="99977-127">Property</span></span>|<span data-ttu-id="99977-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99977-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="99977-129">Specifica un identificatore di risorsa: nome file, URI (Uniform Resource Identifier) Web o riferimento a risorse nel file exe o nel contenitore dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99977-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="99977-130">Specifica le dimensioni del carattere nelle unità della superficie di disegno (l'impostazione predefinita è 0,96 pollici).</span><span class="sxs-lookup"><span data-stu-id="99977-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="99977-131">Specifica i flag per gli stili grassetto e corsivo.</span><span class="sxs-lookup"><span data-stu-id="99977-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="99977-132">Specifica il livello di layout bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="99977-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="99977-133">I valori pari e lo zero implicano un layout da sinistra a destra, mentre i valori dispari implicano un layout da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="99977-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a><span data-ttu-id="99977-134">Proprietà Indices</span><span class="sxs-lookup"><span data-stu-id="99977-134">Indices property</span></span>  
 <span data-ttu-id="99977-135">La <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà è una stringa di specifiche del glifo.</span><span class="sxs-lookup"><span data-stu-id="99977-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="99977-136">Quando una sequenza di glifi forma un cluster singolo, la specifica del primo glifo nel cluster viene preceduta da una specifica del numero di glifi e di punti di codice combinati per formare il cluster.</span><span class="sxs-lookup"><span data-stu-id="99977-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="99977-137">La <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà raccoglie in una stringa le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="99977-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="99977-138">Indici del glifo</span><span class="sxs-lookup"><span data-stu-id="99977-138">Glyph indices</span></span>  
  
- <span data-ttu-id="99977-139">Distanze di avanzamento del glifo</span><span class="sxs-lookup"><span data-stu-id="99977-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="99977-140">Combinazione dei vettori di connessione dei glifi</span><span class="sxs-lookup"><span data-stu-id="99977-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="99977-141">Mapping del cluster tra i punti di codice e i glifi</span><span class="sxs-lookup"><span data-stu-id="99977-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="99977-142">Flag del glifo</span><span class="sxs-lookup"><span data-stu-id="99977-142">Glyph flags</span></span>  
  
 <span data-ttu-id="99977-143">Ogni specifica del glifo presenta la forma seguente:</span><span class="sxs-lookup"><span data-stu-id="99977-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a><span data-ttu-id="99977-144">Metrica del glifo</span><span class="sxs-lookup"><span data-stu-id="99977-144">Glyph Metrics</span></span>  
 <span data-ttu-id="99977-145">Ogni glifo definisce le metriche <xref:System.Windows.Documents.Glyphs>che specificano la modalità di allineamento con altri file .</span><span class="sxs-lookup"><span data-stu-id="99977-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="99977-146">Nell'immagine seguente vengono definite le varie qualità tipografiche di due diversi caratteri glifi.</span><span class="sxs-lookup"><span data-stu-id="99977-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="99977-147">![Diagramma delle misure dei glifi](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="99977-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a><span data-ttu-id="99977-148">Markup dei glifi</span><span class="sxs-lookup"><span data-stu-id="99977-148">Glyphs Markup</span></span>  
 <span data-ttu-id="99977-149">Nell'esempio di codice riportato di <xref:System.Windows.Documents.Glyphs> seguito [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]viene illustrato come utilizzare varie proprietà dell'elemento in .</span><span class="sxs-lookup"><span data-stu-id="99977-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="99977-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99977-150">See also</span></span>

- [<span data-ttu-id="99977-151">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="99977-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="99977-152">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="99977-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="99977-153">Testo</span><span class="sxs-lookup"><span data-stu-id="99977-153">Text</span></span>](optimizing-performance-text.md)
