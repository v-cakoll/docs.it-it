---
title: 'Procedura: riempire una forma con un colore a tinta unita'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: 7f719417a6a1226d7dc4d600518711ba31920a6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521323"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="400ac-102">Procedura: riempire una forma con un colore a tinta unita</span><span class="sxs-lookup"><span data-stu-id="400ac-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="400ac-103">Per riempire una forma con un colore a tinta unita, creare un <xref:System.Drawing.SolidBrush> dell'oggetto e quindi passare tale <xref:System.Drawing.SolidBrush> oggetto come argomento a uno dei metodi di riempimento della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="400ac-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="400ac-104">Nell'esempio seguente viene illustrato come compilare un'ellisse con il colore rosso.</span><span class="sxs-lookup"><span data-stu-id="400ac-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="400ac-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="400ac-105">Example</span></span>  
 <span data-ttu-id="400ac-106">Nel codice seguente, il <xref:System.Drawing.SolidBrush.%23ctor%2A> costruttore accetta un <xref:System.Drawing.Color> oggetto come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="400ac-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="400ac-107">I valori per il <xref:System.Drawing.Color.FromArgb%2A> metodo rappresentano i componenti alfa, rossi, verde e blu del colore.</span><span class="sxs-lookup"><span data-stu-id="400ac-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="400ac-108">Ognuno di questi valori deve essere compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="400ac-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="400ac-109">Il primo 255 indica che il colore è completamente opaco, e il secondo 255 indica che il componente rosso intensità completo.</span><span class="sxs-lookup"><span data-stu-id="400ac-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="400ac-110">Due zeri indicano che i componenti verdi e blu dispongano di intensità pari a 0.</span><span class="sxs-lookup"><span data-stu-id="400ac-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="400ac-111">I quattro numeri (0, 0, 100, 60) passato al <xref:System.Drawing.Graphics.FillEllipse%2A> metodo specificare la posizione e le dimensioni del rettangolo di delimitazione dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="400ac-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="400ac-112">Il rettangolo ha un angolo superiore sinistro di (0, 0), una larghezza pari a 100 e l'altezza di 60.</span><span class="sxs-lookup"><span data-stu-id="400ac-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="400ac-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="400ac-113">Compiling the Code</span></span>  
 <span data-ttu-id="400ac-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="400ac-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400ac-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="400ac-115">See Also</span></span>  
 [<span data-ttu-id="400ac-116">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="400ac-116">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
