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
ms.openlocfilehash: fd86293c539bf58ac93894e0b879dddb984825e1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378946"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="5abb5-102">Procedura: Applicare trasformazioni al testo</span><span class="sxs-lookup"><span data-stu-id="5abb5-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="5abb5-103">Le trasformazioni possono modificare la visualizzazione del testo nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5abb5-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="5abb5-104">Gli esempi seguenti usano diversi tipi di trasformazioni di rendering per modificare la visualizzazione di testo in un <xref:System.Windows.Controls.TextBlock> controllo.</span><span class="sxs-lookup"><span data-stu-id="5abb5-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5abb5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5abb5-105">Example</span></span>  
 <span data-ttu-id="5abb5-106">L'esempio seguente illustra la rotazione del testo intorno a un punto specifico del piano x-y bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="5abb5-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 <span data-ttu-id="5abb5-107">![Testo ruotato con RotateTransform](./media/transformedtext01.jpg "TransformedText01")</span><span class="sxs-lookup"><span data-stu-id="5abb5-107">![Text rotated using a RotateTransform](./media/transformedtext01.jpg "TransformedText01")</span></span>  
<span data-ttu-id="5abb5-108">Esempio di testo ruotato di 90 gradi</span><span class="sxs-lookup"><span data-stu-id="5abb5-108">Example of text rotated 90 degrees</span></span>  
  
 <span data-ttu-id="5abb5-109">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.RotateTransform> per ruotare il testo.</span><span class="sxs-lookup"><span data-stu-id="5abb5-109">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="5abb5-110">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valore pari a 90 Ruota l'elemento di 90 gradi in senso orario.</span><span class="sxs-lookup"><span data-stu-id="5abb5-110">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="5abb5-111">Nell'esempio seguente la seconda riga del testo è ridimensionata del 150% lungo l'asse x, mentre la terza riga del testo è ridimensionata del 150% lungo l'asse y.</span><span class="sxs-lookup"><span data-stu-id="5abb5-111">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 <span data-ttu-id="5abb5-112">![Testo ridimensionato con ScaleTransform](./media/transformedtext02.jpg "TransformedText02")</span><span class="sxs-lookup"><span data-stu-id="5abb5-112">![Text scaled using a ScaleTransform](./media/transformedtext02.jpg "TransformedText02")</span></span>  
<span data-ttu-id="5abb5-113">Esempio di testo ridimensionato</span><span class="sxs-lookup"><span data-stu-id="5abb5-113">Example of scaled text</span></span>  
  
 <span data-ttu-id="5abb5-114">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare il testo rispetto alle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="5abb5-114">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="5abb5-115">Il ridimensionamento del testo non coincide con l'aumento delle dimensioni dei caratteri del testo.</span><span class="sxs-lookup"><span data-stu-id="5abb5-115">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="5abb5-116">Le dimensioni dei caratteri vengono calcolate in modo indipendente per fornire la migliore risoluzione a dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="5abb5-116">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="5abb5-117">Il testo ridimensionato mantiene invece le proporzioni del testo nelle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="5abb5-117">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="5abb5-118">Nell'esempio seguente il testo è inclinato lungo l'asse x.</span><span class="sxs-lookup"><span data-stu-id="5abb5-118">The following example shows text skewed along the x-axis.</span></span>  
  
 <span data-ttu-id="5abb5-119">![Testo inclinato con SkewTransform](./media/transformedtext03.jpg "TransformedText03")</span><span class="sxs-lookup"><span data-stu-id="5abb5-119">![Text skewed using a SkewTransform](./media/transformedtext03.jpg "TransformedText03")</span></span>  
<span data-ttu-id="5abb5-120">Esempio di testo inclinato</span><span class="sxs-lookup"><span data-stu-id="5abb5-120">Example of skewed text</span></span>  
  
 <span data-ttu-id="5abb5-121">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.SkewTransform> per inclinare il testo.</span><span class="sxs-lookup"><span data-stu-id="5abb5-121">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="5abb5-122">L'inclinazione, nota anche come distorsione, è una trasformazione che estende lo spazio delle coordinate in modo non uniforme.</span><span class="sxs-lookup"><span data-stu-id="5abb5-122">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="5abb5-123">In questo esempio le due stringhe di testo sono inclinate di -30° e 30° lungo la coordinata x.</span><span class="sxs-lookup"><span data-stu-id="5abb5-123">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="5abb5-124">Nell'esempio seguente il testo è traslato, o spostato, lungo l'asse x e y.</span><span class="sxs-lookup"><span data-stu-id="5abb5-124">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 <span data-ttu-id="5abb5-125">![Offset del testo con TranslateTransform](./media/transformedtext04.jpg "TransformedText04")</span><span class="sxs-lookup"><span data-stu-id="5abb5-125">![Text offset using a TranslateTransform](./media/transformedtext04.jpg "TransformedText04")</span></span>  
<span data-ttu-id="5abb5-126">Esempio di testo traslato</span><span class="sxs-lookup"><span data-stu-id="5abb5-126">Example of translated text</span></span>  
  
 <span data-ttu-id="5abb5-127">Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.TranslateTransform> per spostare il testo.</span><span class="sxs-lookup"><span data-stu-id="5abb5-127">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="5abb5-128">In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="5abb5-128">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="5abb5-129">Il <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> offre un'ampia gamma di funzionalità per ottenere effetti di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="5abb5-129">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="5abb5-130">Per altre informazioni, vedere [creare testo con ombreggiatura](how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="5abb5-130">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abb5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5abb5-131">See also</span></span>
- [<span data-ttu-id="5abb5-132">Applicare animazioni al testo</span><span class="sxs-lookup"><span data-stu-id="5abb5-132">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
