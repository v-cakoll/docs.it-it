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
ms.openlocfilehash: 2f7bb3fb4f28b063c78dde9f9f354b38a5e707f3
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581896"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="1abeb-102">Introduzione all'oggetto GlyphRun e all'elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="1abeb-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="1abeb-103">In questo argomento vengono descritti l'oggetto <xref:System.Windows.Media.GlyphRun> e l'elemento <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="1abeb-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="1abeb-104">Introduzione a GlyphRun</span><span class="sxs-lookup"><span data-stu-id="1abeb-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="1abeb-105">offre supporto avanzato per il testo, incluso il markup a livello di glifo, con accesso diretto ai <xref:System.Windows.Documents.Glyphs> per i clienti che desiderano intercettare e mantenere il testo dopo la formattazione.</span><span class="sxs-lookup"><span data-stu-id="1abeb-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="1abeb-106">Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="1abeb-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="1abeb-107">Visualizzazione di documenti a formato fisso.</span><span class="sxs-lookup"><span data-stu-id="1abeb-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="1abeb-108">Scenari di stampa.</span><span class="sxs-lookup"><span data-stu-id="1abeb-108">Print scenarios.</span></span>  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="1abeb-109">come linguaggio della stampante.</span><span class="sxs-lookup"><span data-stu-id="1abeb-109">as a device printer language.</span></span>  
  
    - <span data-ttu-id="1abeb-110">Microsoft XPS Document Writer.</span><span class="sxs-lookup"><span data-stu-id="1abeb-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="1abeb-111">Driver della stampante precedenti, output delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] in formato fisso.</span><span class="sxs-lookup"><span data-stu-id="1abeb-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="1abeb-112">Formato dello spooling di stampa.</span><span class="sxs-lookup"><span data-stu-id="1abeb-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="1abeb-113">Rappresentazione di documenti a formato fisso, inclusi i client per le versioni precedenti di Windows e altri dispositivi di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1abeb-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1abeb-114"><xref:System.Windows.Documents.Glyphs> e <xref:System.Windows.Media.GlyphRun> sono progettati per scenari di presentazione e stampa di documenti a formato fisso.</span><span class="sxs-lookup"><span data-stu-id="1abeb-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="1abeb-115">fornisce diversi elementi per il layout generale e scenari di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], ad esempio <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="1abeb-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="1abeb-116">Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="1abeb-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="1abeb-117">Oggetto GlyphRun</span><span class="sxs-lookup"><span data-stu-id="1abeb-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="1abeb-118">L'oggetto <xref:System.Windows.Media.GlyphRun> rappresenta una sequenza di glifi da un singolo lato di un singolo tipo di carattere a una singola dimensione e con un unico stile di rendering.</span><span class="sxs-lookup"><span data-stu-id="1abeb-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="1abeb-119"><xref:System.Windows.Media.GlyphRun> include sia i dettagli del tipo di carattere, ad esempio le posizioni del glifo <xref:System.Windows.Documents.Glyphs.Indices%2A> che le singole icone.</span><span class="sxs-lookup"><span data-stu-id="1abeb-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="1abeb-120">Include anche i punti di codice Unicode originali da cui è stata generata l'esecuzione, le informazioni sul mapping dell'offset del buffer da carattere a glifo e i flag per carattere e per glifo.</span><span class="sxs-lookup"><span data-stu-id="1abeb-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="1abeb-121"><xref:System.Windows.Media.GlyphRun> ha un valore di alto livello <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="1abeb-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="1abeb-122"><xref:System.Windows.Documents.Glyphs> possibile utilizzare nell'albero degli elementi e in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup per rappresentare <xref:System.Windows.Media.GlyphRun> output.</span><span class="sxs-lookup"><span data-stu-id="1abeb-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="1abeb-123">Elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="1abeb-123">The Glyphs Element</span></span>  
 <span data-ttu-id="1abeb-124">L'elemento <xref:System.Windows.Documents.Glyphs> rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1abeb-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="1abeb-125">La sintassi di markup seguente viene utilizzata per descrivere l'elemento <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="1abeb-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="1abeb-126">Le definizioni di proprietà seguenti corrispondono ai primi quattro attributi del markup di esempio.</span><span class="sxs-lookup"><span data-stu-id="1abeb-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="1abeb-127">proprietà</span><span class="sxs-lookup"><span data-stu-id="1abeb-127">Property</span></span>|<span data-ttu-id="1abeb-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1abeb-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="1abeb-129">Specifica un identificatore di risorsa: il nome file, l'URI (Uniform Resource Identifier) Web o il riferimento a una risorsa nell'applicazione. exe o nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="1abeb-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="1abeb-130">Specifica le dimensioni del carattere nelle unità della superficie di disegno (l'impostazione predefinita è 0,96 pollici).</span><span class="sxs-lookup"><span data-stu-id="1abeb-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="1abeb-131">Specifica i flag per gli stili grassetto e corsivo.</span><span class="sxs-lookup"><span data-stu-id="1abeb-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="1abeb-132">Specifica il livello di layout bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="1abeb-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="1abeb-133">I valori pari e lo zero implicano un layout da sinistra a destra, mentre i valori dispari implicano un layout da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1abeb-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="1abeb-134">Proprietà Indices</span><span class="sxs-lookup"><span data-stu-id="1abeb-134">Indices property</span></span>  
 <span data-ttu-id="1abeb-135">La proprietà <xref:System.Windows.Documents.Glyphs.Indices%2A> è una stringa di specifiche di glifi.</span><span class="sxs-lookup"><span data-stu-id="1abeb-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="1abeb-136">Quando una sequenza di glifi forma un cluster singolo, la specifica del primo glifo nel cluster viene preceduta da una specifica del numero di glifi e di punti di codice combinati per formare il cluster.</span><span class="sxs-lookup"><span data-stu-id="1abeb-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="1abeb-137">La proprietà <xref:System.Windows.Documents.Glyphs.Indices%2A> raccoglie in una stringa le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="1abeb-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="1abeb-138">Indici del glifo</span><span class="sxs-lookup"><span data-stu-id="1abeb-138">Glyph indices</span></span>  
  
- <span data-ttu-id="1abeb-139">Distanze di avanzamento del glifo</span><span class="sxs-lookup"><span data-stu-id="1abeb-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="1abeb-140">Combinazione dei vettori di connessione dei glifi</span><span class="sxs-lookup"><span data-stu-id="1abeb-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="1abeb-141">Mapping del cluster tra i punti di codice e i glifi</span><span class="sxs-lookup"><span data-stu-id="1abeb-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="1abeb-142">Flag del glifo</span><span class="sxs-lookup"><span data-stu-id="1abeb-142">Glyph flags</span></span>  
  
 <span data-ttu-id="1abeb-143">Ogni specifica del glifo presenta la forma seguente:</span><span class="sxs-lookup"><span data-stu-id="1abeb-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="1abeb-144">Metrica del glifo</span><span class="sxs-lookup"><span data-stu-id="1abeb-144">Glyph Metrics</span></span>  
 <span data-ttu-id="1abeb-145">Ogni glifo definisce le metriche che specificano la modalità di allineamento con altri <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="1abeb-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="1abeb-146">Nell'immagine seguente vengono definite le varie qualità tipografiche di due diversi caratteri glifi.</span><span class="sxs-lookup"><span data-stu-id="1abeb-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="1abeb-147">![Diagramma delle misurazioni del glifo](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="1abeb-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="1abeb-148">Markup dei glifi</span><span class="sxs-lookup"><span data-stu-id="1abeb-148">Glyphs Markup</span></span>  
 <span data-ttu-id="1abeb-149">Nell'esempio di codice seguente viene illustrato come utilizzare varie proprietà dell'elemento <xref:System.Windows.Documents.Glyphs> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1abeb-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1abeb-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1abeb-150">See also</span></span>

- [<span data-ttu-id="1abeb-151">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="1abeb-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="1abeb-152">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="1abeb-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="1abeb-153">Testo</span><span class="sxs-lookup"><span data-stu-id="1abeb-153">Text</span></span>](optimizing-performance-text.md)
