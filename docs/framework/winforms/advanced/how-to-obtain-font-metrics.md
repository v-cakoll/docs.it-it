---
title: 'Procedura: recuperare i criteri di misurazione dei caratteri'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b45f3f903c02d056fc457b652b01fb7b59413a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="d8b2b-102">Procedura: recuperare i criteri di misurazione dei caratteri</span><span class="sxs-lookup"><span data-stu-id="d8b2b-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="d8b2b-103">La <xref:System.Drawing.FontFamily> classe fornisce i seguenti metodi che recuperano diverse metriche per una particolare famiglia o combinazione di stile:</span><span class="sxs-lookup"><span data-stu-id="d8b2b-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="d8b2b-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="d8b2b-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="d8b2b-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="d8b2b-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="d8b2b-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="d8b2b-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="d8b2b-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="d8b2b-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="d8b2b-108">I numeri restituiti da questi metodi sono in unità di progettazione di tipo di carattere, in modo che siano indipendenti le dimensioni e l'unità di un particolare <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="d8b2b-109">Nella figura seguente mostra le varie metriche.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="d8b2b-110">![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="d8b2b-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b2b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8b2b-111">Example</span></span>  
 <span data-ttu-id="d8b2b-112">L'esempio seguente mostra le metriche per lo stile normale della famiglia di caratteri Arial.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="d8b2b-113">Il codice crea inoltre un <xref:System.Drawing.Font> oggetto (in base alla famiglia Arial) con dimensioni 16 pixel e visualizza le metriche (in pixel) per questo specifico <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="d8b2b-114">Nella figura seguente mostra l'output del codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="d8b2b-115">![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="d8b2b-115">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="d8b2b-116">Tenere presente le prime due righe di output nell'illustrazione precedente.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="d8b2b-117">Il <xref:System.Drawing.Font> oggetto restituisce una dimensione di 16 e <xref:System.Drawing.FontFamily> restituisce un'altezza em pari a 2048.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="d8b2b-118">Questi due numeri (16 e 2.048) sono fondamentali per la conversione tra unità di progettazione caratteri e le unità (in questo caso pixel) del <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="d8b2b-119">Ad esempio, è possibile convertire l'ascent di unità di progettazione pixel come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d8b2b-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="d8b2b-120">![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="d8b2b-120">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="d8b2b-121">Il codice seguente posiziona testo verticale impostando il <xref:System.Drawing.PointF.Y%2A> membro dati di un <xref:System.Drawing.PointF> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="d8b2b-122">La coordinata y viene aumentata di `font.Height` per ogni nuova riga di testo.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="d8b2b-123">Il <xref:System.Drawing.Font.Height%2A> proprietà di un <xref:System.Drawing.Font> object restituisce l'interlinea, in pixel, per questo specifico <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="d8b2b-124">In questo esempio, il numero restituito da <xref:System.Drawing.Font.Height%2A> è 19.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="d8b2b-125">Si noti che questo è lo stesso come numero (arrotondato per eccesso a un numero intero) ottenuto tramite la conversione della metrica interlinea in pixel.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="d8b2b-126">Si noti che l'altezza em (detto anche dimensione o dimensione em) non è la somma della parte ascendente e la parte discendente.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="d8b2b-127">La somma della parte superiore e la parte discendente viene chiamata l'altezza della cella.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="d8b2b-128">Altezza della cella meno lo spazio iniziale interno è uguale all'altezza em.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="d8b2b-129">Altezza della cella più esterno iniziale è uguale all'interlinea.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d8b2b-130">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d8b2b-130">Compiling the Code</span></span>  
 <span data-ttu-id="d8b2b-131">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="d8b2b-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b2b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b2b-132">See Also</span></span>  
 [<span data-ttu-id="d8b2b-133">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="d8b2b-133">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="d8b2b-134">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="d8b2b-134">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
