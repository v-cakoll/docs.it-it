---
title: 'Procedura: Ottenere le misure dei tipi di carattere'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307431"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="76baf-102">Procedura: Ottenere le misure dei tipi di carattere</span><span class="sxs-lookup"><span data-stu-id="76baf-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="76baf-103">Il <xref:System.Drawing.FontFamily> classe fornisce i metodi seguenti che recuperano diverse metriche per una particolare famiglia/combinazione stile:</span><span class="sxs-lookup"><span data-stu-id="76baf-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
- <span data-ttu-id="76baf-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="76baf-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="76baf-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="76baf-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="76baf-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="76baf-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="76baf-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="76baf-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="76baf-108">I valori restituiti da questi metodi sono in unità di progettazione del tipo di carattere, in modo che siano indipendenti dalla dimensione e le unità di un determinato <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="76baf-108">The values returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="76baf-109">La figura seguente illustra le varie metriche:</span><span class="sxs-lookup"><span data-stu-id="76baf-109">The following illustration shows the various metrics:</span></span>
  
 ![Illustrazione delle metriche del tipo di carattere: ascent dei valori descent con e interlinea.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a><span data-ttu-id="76baf-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="76baf-111">Example</span></span>  
 <span data-ttu-id="76baf-112">L'esempio seguente mostra le metriche per lo stile regolare della famiglia del tipo di carattere Arial.</span><span class="sxs-lookup"><span data-stu-id="76baf-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="76baf-113">Il codice crea inoltre una <xref:System.Drawing.Font> oggetto (in base alla famiglia Arial) con dimensioni di 16 pixel e consente di visualizzare le metriche, in pixel, per quel particolare <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="76baf-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="76baf-114">Nella figura seguente mostra l'output del codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="76baf-114">The following illustration shows the output of the example code:</span></span>
  
 ![Output di codice di esempio delle metriche del tipo di carattere Arial.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 <span data-ttu-id="76baf-116">Tenere presente le prime due righe di output nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="76baf-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="76baf-117">Il <xref:System.Drawing.Font> object restituisce una dimensione pari a 16 e il <xref:System.Drawing.FontFamily> oggetto restituisce un'altezza em di 2048.</span><span class="sxs-lookup"><span data-stu-id="76baf-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="76baf-118">Questi due numeri (16 e 2,048) sono la chiave per la conversione tra unità di progettazione del tipo di carattere e le unità (in questo caso pixel) del <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="76baf-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="76baf-119">Ad esempio, è possibile convertire l'ascent di unità di progettazione pixel come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="76baf-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 ![Formula che mostra la conversione da unità di progettazione per pixel](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 <span data-ttu-id="76baf-121">Il codice seguente posiziona testo verticalmente impostando il <xref:System.Drawing.PointF.Y%2A> membro dati di un <xref:System.Drawing.PointF> oggetto.</span><span class="sxs-lookup"><span data-stu-id="76baf-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="76baf-122">La coordinata y è aumentata `font.Height` per ogni nuova riga di testo.</span><span class="sxs-lookup"><span data-stu-id="76baf-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="76baf-123">Il <xref:System.Drawing.Font.Height%2A> proprietà di un <xref:System.Drawing.Font> object restituisce l'interlinea, in pixel, per quel particolare <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="76baf-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="76baf-124">In questo esempio, il numero restituito da <xref:System.Drawing.Font.Height%2A> è 19.</span><span class="sxs-lookup"><span data-stu-id="76baf-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="76baf-125">Si noti che questo è lo stesso come numero (arrotondato per eccesso a un numero intero) ottenuto tramite la conversione della metrica di interlinea in pixel.</span><span class="sxs-lookup"><span data-stu-id="76baf-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="76baf-126">Si noti che l'altezza em (denominato anche dimensioni em o dimensioni) non è la somma dell'ascent e la parte discendente.</span><span class="sxs-lookup"><span data-stu-id="76baf-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="76baf-127">La somma dell'ascent e la parte discendente viene chiamata l'altezza della cella.</span><span class="sxs-lookup"><span data-stu-id="76baf-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="76baf-128">L'altezza della cella meno lo spazio iniziale interno è uguale all'altezza em.</span><span class="sxs-lookup"><span data-stu-id="76baf-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="76baf-129">L'altezza della cella più l'interlinea esterna è uguale alla distanza tra linee.</span><span class="sxs-lookup"><span data-stu-id="76baf-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="76baf-130">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="76baf-130">Compiling the Code</span></span>  
 <span data-ttu-id="76baf-131">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="76baf-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76baf-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76baf-132">See also</span></span>

- [<span data-ttu-id="76baf-133">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="76baf-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="76baf-134">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="76baf-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
