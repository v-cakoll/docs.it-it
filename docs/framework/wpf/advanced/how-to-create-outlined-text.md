---
title: 'Procedura: creare testo con contorni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186863"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="fb7b7-102">Procedura: creare testo con contorni</span><span class="sxs-lookup"><span data-stu-id="fb7b7-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="fb7b7-103">Nella maggior parte dei casi, quando si [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aggiungono ornamenti alle stringhe di testo nell'applicazione, si utilizza il testo in termini di una raccolta di caratteri discreti o glifi.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="fb7b7-104">Ad esempio, è possibile creare un pennello <xref:System.Windows.Controls.Control.Foreground%2A> sfumato lineare e applicarlo alla proprietà di un <xref:System.Windows.Controls.TextBox> oggetto.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="fb7b7-105">Quando si visualizza o si modifica la casella di testo, il pennello sfumato lineare viene applicato automaticamente al set di caratteri corrente nella stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Testo visualizzato con pennello sfumato lineare](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="fb7b7-107">Tuttavia, è anche <xref:System.Windows.Media.Geometry> possibile convertire il testo in oggetti, consentendo di creare altri tipi di testo ricco di immagini.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="fb7b7-108">Ad esempio, è <xref:System.Windows.Media.Geometry> possibile creare un oggetto in base al contorno di una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Struttura di testo con pennello sfumato lineare](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="fb7b7-110">Quando il testo <xref:System.Windows.Media.Geometry> viene convertito in un oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="fb7b7-111">Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="fb7b7-112">Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="fb7b7-113">Gli esempi seguenti illustrano diversi modi per creare effetti visivi modificando la traccia e il riempimento del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Testo con colori diversi per tratto e riempimento](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="fb7b7-116">È anche possibile modificare il rettangolo del riquadro di delimitazione, o evidenziare, del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="fb7b7-117">Nell'esempio seguente viene illustrato un modo per creare effetti visivi modificando il tratto e l'evidenziazione del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Testo con pennello immagine applicato al tratto e all'evidenziazione](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="fb7b7-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb7b7-119">Example</span></span>  
 <span data-ttu-id="fb7b7-120">La chiave per convertire <xref:System.Windows.Media.Geometry> il testo in <xref:System.Windows.Media.FormattedText> un oggetto consiste nell'utilizzare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="fb7b7-121">Dopo aver creato questo oggetto, <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> è <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> possibile utilizzare i <xref:System.Windows.Media.Geometry> metodi e per convertire il testo in oggetti.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="fb7b7-122">Il primo metodo restituisce la geometria del testo formattato; il secondo metodo restituisce la geometria del riquadro di delimitazione del testo formattato.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="fb7b7-123">Nell'esempio di codice riportato di seguito viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e recuperare le geometrie del testo formattato e del relativo riquadro di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="fb7b7-124">Per visualizzare gli <xref:System.Windows.Media.Geometry> oggetti recuperati, è necessario <xref:System.Windows.Media.DrawingContext> accedere all'oggetto che visualizza il testo convertito.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="fb7b7-125">In questi esempi di codice, questa operazione viene eseguita creando un oggetto controllo personalizzato derivato da una classe che supporta il rendering definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="fb7b7-126">Per <xref:System.Windows.Media.Geometry> visualizzare gli oggetti nel controllo personalizzato, fornire un override per il <xref:System.Windows.UIElement.OnRender%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="fb7b7-127">Il metodo sottoposto <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> a override <xref:System.Windows.Media.Geometry> deve utilizzare il metodo per disegnare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="fb7b7-128">Per l'origine dell'oggetto controllo utente personalizzato di esempio, vedere [OutlineTextControl.cs per C'](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) e [OutlineTextControl.vb per Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span><span class="sxs-lookup"><span data-stu-id="fb7b7-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb7b7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb7b7-129">See also</span></span>

- [<span data-ttu-id="fb7b7-130">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="fb7b7-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
