---
title: Introduzione all'oggetto GlyphRun e all'elemento Glyphs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa868b520224b27b3cd2b3dc99431728ad8ea527
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="1a889-102">Introduzione all'oggetto GlyphRun e all'elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="1a889-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="1a889-103">Questo argomento viene descritto il <xref:System.Windows.Media.GlyphRun> oggetto e il <xref:System.Windows.Documents.Glyphs> elemento.</span><span class="sxs-lookup"><span data-stu-id="1a889-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="1a889-104">Introduzione a GlyphRun</span><span class="sxs-lookup"><span data-stu-id="1a889-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1a889-105">fornisce il supporto di testo avanzato, incluso il markup a livello di glifo con accesso diretto a <xref:System.Windows.Documents.Glyphs> per i clienti che desiderano intercettare e mantenere il testo dopo la formattazione.</span><span class="sxs-lookup"><span data-stu-id="1a889-105"> provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="1a889-106">Queste funzionalità forniscono il supporto fondamentale per i diversi requisiti di rendering del testo in ognuno degli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="1a889-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1.  <span data-ttu-id="1a889-107">Visualizzazione di documenti a formato fisso.</span><span class="sxs-lookup"><span data-stu-id="1a889-107">Screen display of fixed-format documents.</span></span>  
  
2.  <span data-ttu-id="1a889-108">Scenari di stampa.</span><span class="sxs-lookup"><span data-stu-id="1a889-108">Print scenarios.</span></span>  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="1a889-109"> come linguaggio della stampante.</span><span class="sxs-lookup"><span data-stu-id="1a889-109"> as a device printer language.</span></span>  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]<span data-ttu-id="1a889-110">.</span><span class="sxs-lookup"><span data-stu-id="1a889-110">.</span></span>  
  
    -   <span data-ttu-id="1a889-111">Driver della stampante precedenti, output delle applicazioni [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] in formato fisso.</span><span class="sxs-lookup"><span data-stu-id="1a889-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    -   <span data-ttu-id="1a889-112">Formato dello spooling di stampa.</span><span class="sxs-lookup"><span data-stu-id="1a889-112">Print spool format.</span></span>  
  
3.  <span data-ttu-id="1a889-113">Rappresentazione di documenti con formato fisso, inclusi i client di versioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e altri dispositivi di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1a889-113">Fixed-format document representation, including clients for previous versions of [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] and other computing devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a889-114"><xref:System.Windows.Documents.Glyphs>e <xref:System.Windows.Media.GlyphRun> sono progettati per scenari di stampa e di presentazione del documento di formato fisso.</span><span class="sxs-lookup"><span data-stu-id="1a889-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1a889-115">vengono forniti diversi elementi per il layout generale e [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenari, ad esempio <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="1a889-115"> provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="1a889-116">Per altre informazioni sugli scenari di layout e dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vedere [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="1a889-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="1a889-117">Oggetto GlyphRun</span><span class="sxs-lookup"><span data-stu-id="1a889-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="1a889-118">Il <xref:System.Windows.Media.GlyphRun> oggetto rappresenta una sequenza di glifi da una singola icona di un singolo tipo di carattere in una singola dimensione, con un unico stile di rendering.</span><span class="sxs-lookup"><span data-stu-id="1a889-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="1a889-119"><xref:System.Windows.Media.GlyphRun>include i dettagli relativi al tipo di carattere, ad esempio glifo <xref:System.Windows.Documents.Glyphs.Indices%2A> e posizioni dei singoli glifi.</span><span class="sxs-lookup"><span data-stu-id="1a889-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="1a889-120">Include inoltre originale [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] l'esecuzione è stato generato da informazioni di mapping dell'offset del buffer al glifo di caratteri e i flag per ogni carattere e ogni glifo di punti di codice.</span><span class="sxs-lookup"><span data-stu-id="1a889-120">It also includes the original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="1a889-121"><xref:System.Windows.Media.GlyphRun>ha un alto livello corrispondente <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="1a889-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="1a889-122"><xref:System.Windows.Documents.Glyphs>può essere utilizzato nell'albero degli elementi e in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup per rappresentare <xref:System.Windows.Media.GlyphRun> output.</span><span class="sxs-lookup"><span data-stu-id="1a889-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="1a889-123">Elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="1a889-123">The Glyphs Element</span></span>  
 <span data-ttu-id="1a889-124">Il <xref:System.Windows.Documents.Glyphs> elemento rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a889-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="1a889-125">La sintassi di codice seguente viene utilizzata per descrivere il <xref:System.Windows.Documents.Glyphs> elemento.</span><span class="sxs-lookup"><span data-stu-id="1a889-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="1a889-126">Le definizioni di proprietà seguenti corrispondono ai primi quattro attributi del markup di esempio.</span><span class="sxs-lookup"><span data-stu-id="1a889-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="1a889-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1a889-127">Property</span></span>|<span data-ttu-id="1a889-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a889-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="1a889-129">Specifica un identificatore di risorsa: nome del file Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], o riferimento a una risorsa nell'applicazione .exe o nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="1a889-129">Specifies a resource identifier: file name, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="1a889-130">Specifica le dimensioni del carattere nelle unità della superficie di disegno (l'impostazione predefinita è 0,96 pollici).</span><span class="sxs-lookup"><span data-stu-id="1a889-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="1a889-131">Specifica i flag per gli stili grassetto e corsivo.</span><span class="sxs-lookup"><span data-stu-id="1a889-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="1a889-132">Specifica il livello di layout bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="1a889-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="1a889-133">I valori pari e lo zero implicano un layout da sinistra a destra, mentre i valori dispari implicano un layout da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1a889-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="1a889-134">Proprietà Indices</span><span class="sxs-lookup"><span data-stu-id="1a889-134">Indices property</span></span>  
 <span data-ttu-id="1a889-135">Il <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà è una stringa di specifiche del glifo.</span><span class="sxs-lookup"><span data-stu-id="1a889-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="1a889-136">Quando una sequenza di glifi forma un cluster singolo, la specifica del primo glifo nel cluster viene preceduta da una specifica del numero di glifi e di punti di codice combinati per formare il cluster.</span><span class="sxs-lookup"><span data-stu-id="1a889-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="1a889-137">Il <xref:System.Windows.Documents.Glyphs.Indices%2A> proprietà raccoglie in una stringa le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="1a889-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
-   <span data-ttu-id="1a889-138">Indici del glifo</span><span class="sxs-lookup"><span data-stu-id="1a889-138">Glyph indices</span></span>  
  
-   <span data-ttu-id="1a889-139">Distanze di avanzamento del glifo</span><span class="sxs-lookup"><span data-stu-id="1a889-139">Glyph advance widths</span></span>  
  
-   <span data-ttu-id="1a889-140">Combinazione dei vettori di connessione dei glifi</span><span class="sxs-lookup"><span data-stu-id="1a889-140">Combining glyph attachment vectors</span></span>  
  
-   <span data-ttu-id="1a889-141">Mapping del cluster tra i punti di codice e i glifi</span><span class="sxs-lookup"><span data-stu-id="1a889-141">Cluster mapping from code points to glyphs</span></span>  
  
-   <span data-ttu-id="1a889-142">Flag del glifo</span><span class="sxs-lookup"><span data-stu-id="1a889-142">Glyph flags</span></span>  
  
 <span data-ttu-id="1a889-143">Ogni specifica del glifo presenta la forma seguente:</span><span class="sxs-lookup"><span data-stu-id="1a889-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="1a889-144">Metrica del glifo</span><span class="sxs-lookup"><span data-stu-id="1a889-144">Glyph Metrics</span></span>  
 <span data-ttu-id="1a889-145">Ogni glifo definisce la metrica che specifica la modalità di allineamento con altri <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="1a889-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="1a889-146">Nell'immagine seguente vengono definite le varie qualità tipografiche di due diversi caratteri glifi.</span><span class="sxs-lookup"><span data-stu-id="1a889-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="1a889-147">![Diagramma delle misure dei glifi](../../../../docs/framework/wpf/advanced/media/glyph-example.png "esempio_glifo")</span><span class="sxs-lookup"><span data-stu-id="1a889-147">![Diagraph of glyph measurements](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="1a889-148">Markup dei glifi</span><span class="sxs-lookup"><span data-stu-id="1a889-148">Glyphs Markup</span></span>  
 <span data-ttu-id="1a889-149">Esempio di codice seguente viene illustrato come utilizzare diverse proprietà del <xref:System.Windows.Documents.Glyphs> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a889-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1a889-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a889-150">See Also</span></span>  
 [<span data-ttu-id="1a889-151">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="1a889-151">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="1a889-152">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="1a889-152">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="1a889-153">per</span><span class="sxs-lookup"><span data-stu-id="1a889-153">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
