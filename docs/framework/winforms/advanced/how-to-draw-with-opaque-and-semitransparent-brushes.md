---
title: 'Procedura: Disegnare con pennelli opachi e semitrasparenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: ebb2f1008d267c4b5dcf36a7a4aae749fe73bb59
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716880"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="4bc3d-102">Procedura: Disegnare con pennelli opachi e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="4bc3d-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="4bc3d-103">Quando si riempie una forma, è necessario passare un oggetto <xref:System.Drawing.Brush> a uno dei metodi di riempimento della classe <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4bc3d-104">L'unico parametro del costruttore <xref:System.Drawing.SolidBrush.%23ctor%2A> è un oggetto <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="4bc3d-105">Per riempire una forma opaca, impostare il componente alfa del colore su 255.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="4bc3d-106">Per riempire una forma semitrasparente, impostare il componente alfa su un valore qualsiasi compreso tra 1 e 254.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="4bc3d-107">Quando si riempie una forma semitrasparente, il colore della forma viene sfumato con i colori dello sfondo.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="4bc3d-108">Il componente alfa specifica come si combinano i colori della forma e dello sfondo. I valori alfa vicini a 0 rendono più intensi i colori di sfondo, mentre i valori alfa più vicini a 255 rendono più intenso il colore della forma.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bc3d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bc3d-109">Example</span></span>  
 <span data-ttu-id="4bc3d-110">L'esempio seguente disegna una bitmap e quindi riempie tre ellissi che si sovrappongono alla bitmap.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="4bc3d-111">Per la prima ellisse si usa un componente alfa con un valore pari a 255, quindi l'ellisse risulta opaca.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="4bc3d-112">Per la seconda e la terza ellisse si usa un componente alfa con un valore pari a 128, quindi le ellissi risultano semitrasparenti. L'immagine di sfondo è visibile attraverso le ellissi.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="4bc3d-113">La chiamata che imposta la proprietà <xref:System.Drawing.Graphics.CompositingQuality%2A> determina la sfumatura della terza ellissi ottenuta in combinazione con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="4bc3d-114">L'immagine seguente illustra l'output del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="4bc3d-115">![Opache e semitrasparenti](./media/compqualellipse.png "compqualellipse")</span><span class="sxs-lookup"><span data-stu-id="4bc3d-115">![Opaque and Semitransparent](./media/compqualellipse.png "compqualellipse")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4bc3d-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4bc3d-116">Compiling the Code</span></span>  
 <span data-ttu-id="4bc3d-117">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="4bc3d-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc3d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bc3d-118">See also</span></span>
- [<span data-ttu-id="4bc3d-119">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4bc3d-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4bc3d-120">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="4bc3d-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="4bc3d-121">Procedura: Assegnare al controllo uno sfondo trasparente</span><span class="sxs-lookup"><span data-stu-id="4bc3d-121">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="4bc3d-122">Procedura: Disegnare linee opache e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="4bc3d-122">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)
