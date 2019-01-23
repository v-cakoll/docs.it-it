---
title: 'Procedura: Disegnare linee opache e semitrasparenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 6076ebf6cb75aa4fdb5cf5798b642597d8f84c80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559047"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="6768d-102">Procedura: Disegnare linee opache e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="6768d-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="6768d-103">Quando si disegna una linea, è necessario passare un oggetto <xref:System.Drawing.Pen> al metodo <xref:System.Drawing.Graphics.DrawLine%2A> della classe <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="6768d-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="6768d-104">Uno dei parametri del costruttore <xref:System.Drawing.Pen.%23ctor%2A> è un oggetto <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="6768d-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="6768d-105">Per disegnare una linea opaca, impostare il componente alfa del colore su 255.</span><span class="sxs-lookup"><span data-stu-id="6768d-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="6768d-106">Per disegnare una linea semitrasparente, impostare il componente alfa su un valore qualsiasi compreso tra 1 e 254.</span><span class="sxs-lookup"><span data-stu-id="6768d-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="6768d-107">Quando si disegna una linea semitrasparente su uno sfondo, il colore della linea viene sfumato con i colori dello sfondo.</span><span class="sxs-lookup"><span data-stu-id="6768d-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="6768d-108">Il componente alfa specifica come si combinano i colori della linea e dello sfondo. I valori alfa vicini a 0 rendono più intensi i colori di sfondo, mentre i valori alfa più vicini a 255 rendono più intenso il colore della linea.</span><span class="sxs-lookup"><span data-stu-id="6768d-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6768d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="6768d-109">Example</span></span>  
 <span data-ttu-id="6768d-110">L'esempio seguente disegna un'immagine bitmap e quindi tre linee che usano la stessa bitmap come sfondo.</span><span class="sxs-lookup"><span data-stu-id="6768d-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="6768d-111">Per la prima linea si usa un componente alfa con un valore pari a 255, quindi la linea risulta opaca.</span><span class="sxs-lookup"><span data-stu-id="6768d-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="6768d-112">Per la seconda e la terza linea si usa un componente alfa con un valore pari a 128, quindi le linee risultano semitrasparenti. L'immagine di sfondo è visibile attraverso le linee.</span><span class="sxs-lookup"><span data-stu-id="6768d-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="6768d-113">L'istruzione che imposta la proprietà <xref:System.Drawing.Graphics.CompositingQuality%2A> determina la sfumatura della terza riga ottenuta in combinazione con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="6768d-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="6768d-114">L'immagine seguente illustra l'output del codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6768d-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="6768d-115">![Opache e semitrasparenti](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span><span class="sxs-lookup"><span data-stu-id="6768d-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6768d-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6768d-116">Compiling the Code</span></span>  
 <span data-ttu-id="6768d-117">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6768d-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6768d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6768d-118">See also</span></span>
- [<span data-ttu-id="6768d-119">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="6768d-119">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="6768d-120">Procedura: Assegnare al controllo uno sfondo trasparente</span><span class="sxs-lookup"><span data-stu-id="6768d-120">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="6768d-121">Procedura: Disegnare con pennelli opachi e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="6768d-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)
