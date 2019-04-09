---
title: 'Procedura: Creare figure da linee, curve e forme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: eeaf478375e08734b20d83b6f3c8030732495013
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224910"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="5e8f1-102">Procedura: Creare figure da linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="5e8f1-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="5e8f1-103">Per una figura di creare, costruire un <xref:System.Drawing.Drawing2D.GraphicsPath>, quindi chiamare i metodi, ad esempio <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, per aggiungere le primitive nel percorso.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e8f1-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e8f1-104">Example</span></span>  
 <span data-ttu-id="5e8f1-105">Gli esempi di codice seguente creano i percorsi contenenti cifre:</span><span class="sxs-lookup"><span data-stu-id="5e8f1-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="5e8f1-106">Nel primo esempio crea un percorso che abbia una sola figura.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="5e8f1-107">Nella figura è costituito da un singolo arco. Punto finale dell'arco dispone di un angolo di apertura della-180 gradi, in senso antiorario nel sistema di coordinate predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="5e8f1-108">Nel secondo esempio viene creato un percorso con due cifre.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="5e8f1-109">La prima figura fa un arco seguito da una riga.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="5e8f1-110">La seconda figura è una riga seguita da una curva seguita da una riga.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="5e8f1-111">La prima figura viene lasciata aperta, e la seconda figura è chiusa.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e8f1-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5e8f1-112">Compiling the Code</span></span>  
 <span data-ttu-id="5e8f1-113">Negli esempi precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5e8f1-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8f1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e8f1-114">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="5e8f1-115">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="5e8f1-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="5e8f1-116">Utilizzo di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="5e8f1-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
