---
title: 'Procedura: Applicare trasformazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 46a57364e0c18cc4c9fe7884642cd0b718c20f31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208670"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="c89f8-102">Procedura: Applicare trasformazioni al testo</span><span class="sxs-lookup"><span data-stu-id="c89f8-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="c89f8-103">Le trasformazioni possono modificare la visualizzazione del testo nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c89f8-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="c89f8-104">Gli esempi seguenti usano diversi tipi di trasformazioni di rendering per modificare la visualizzazione di testo in un <xref:System.Windows.Controls.TextBlock> controllo.</span><span class="sxs-lookup"><span data-stu-id="c89f8-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c89f8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c89f8-105">Example</span></span>  
 <span data-ttu-id="c89f8-106">L'esempio seguente illustra la rotazione del testo intorno a un punto specifico del piano x-y bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="c89f8-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 ![Testo ruotato con RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 <span data-ttu-id="c89f8-108">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.RotateTransform> per ruotare il testo.</span><span class="sxs-lookup"><span data-stu-id="c89f8-108">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="c89f8-109">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valore pari a 90 Ruota l'elemento di 90 gradi in senso orario.</span><span class="sxs-lookup"><span data-stu-id="c89f8-109">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="c89f8-110">Nell'esempio seguente la seconda riga del testo è ridimensionata del 150% lungo l'asse x, mentre la terza riga del testo è ridimensionata del 150% lungo l'asse y.</span><span class="sxs-lookup"><span data-stu-id="c89f8-110">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![Testo ridimensionato con ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 <span data-ttu-id="c89f8-112">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare il testo rispetto alle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="c89f8-112">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="c89f8-113">Il ridimensionamento del testo non coincide con l'aumento delle dimensioni dei caratteri del testo.</span><span class="sxs-lookup"><span data-stu-id="c89f8-113">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="c89f8-114">Le dimensioni dei caratteri vengono calcolate in modo indipendente per fornire la migliore risoluzione a dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="c89f8-114">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="c89f8-115">Il testo ridimensionato mantiene invece le proporzioni del testo nelle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="c89f8-115">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="c89f8-116">Nell'esempio seguente il testo è inclinato lungo l'asse x.</span><span class="sxs-lookup"><span data-stu-id="c89f8-116">The following example shows text skewed along the x-axis.</span></span>  
  
 ![Testo inclinato con SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 <span data-ttu-id="c89f8-118">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.SkewTransform> per inclinare il testo.</span><span class="sxs-lookup"><span data-stu-id="c89f8-118">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="c89f8-119">L'inclinazione, nota anche come distorsione, è una trasformazione che estende lo spazio delle coordinate in modo non uniforme.</span><span class="sxs-lookup"><span data-stu-id="c89f8-119">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="c89f8-120">In questo esempio le due stringhe di testo sono inclinate di -30° e 30° lungo la coordinata x.</span><span class="sxs-lookup"><span data-stu-id="c89f8-120">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="c89f8-121">Nell'esempio seguente il testo è traslato, o spostato, lungo l'asse x e y.</span><span class="sxs-lookup"><span data-stu-id="c89f8-121">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 ![Offset del testo con TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 <span data-ttu-id="c89f8-123">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.TranslateTransform> per spostare il testo.</span><span class="sxs-lookup"><span data-stu-id="c89f8-123">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="c89f8-124">In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="c89f8-124">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="c89f8-125">Il <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> offre un'ampia gamma di funzionalità per ottenere effetti di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="c89f8-125">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="c89f8-126">Per altre informazioni, vedere [creare testo con ombreggiatura](how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="c89f8-126">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89f8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c89f8-127">See also</span></span>

- [<span data-ttu-id="c89f8-128">Applicare animazioni al testo</span><span class="sxs-lookup"><span data-stu-id="c89f8-128">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
