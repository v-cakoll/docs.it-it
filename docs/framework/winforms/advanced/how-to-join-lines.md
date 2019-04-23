---
title: 'Procedura: Unire le linee'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 445d7f12f57137c6b06a074eeaf0574eb027a723
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174915"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="d2fcd-102">Procedura: Unire le linee</span><span class="sxs-lookup"><span data-stu-id="d2fcd-102">How to: Join Lines</span></span>
<span data-ttu-id="d2fcd-103">Un join di riga è l'area comune in cui è costituito da due righe di cui end soddisfare o si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d2fcd-104">sono disponibili tre stili di linea join: decorato, rilievo e arrotondato.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-104">provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="d2fcd-105">Stile di linea join è una proprietà del <xref:System.Drawing.Pen> classe.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="d2fcd-106">Quando si specifica un stile della linea join per un <xref:System.Drawing.Pen> dell'oggetto, che verrà applicata a tutte le righe connessione in qualsiasi tipo di join <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto viene disegnato utilizzando la penna.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="d2fcd-107">La figura seguente mostra i risultati dell'esempio di join di linee in rilievo.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![Figura che mostra le righe unite in join.](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="d2fcd-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2fcd-109">Example</span></span>  
 <span data-ttu-id="d2fcd-110">È possibile specificare lo stile della linea join tramite il <xref:System.Drawing.Pen.LineJoin%2A> proprietà del <xref:System.Drawing.Pen> classe.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="d2fcd-111">Nell'esempio viene illustrato un join di linee in rilievo tra una riga orizzontale e una linea verticale.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="d2fcd-112">Nel codice seguente, il valore <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assegnato per il <xref:System.Drawing.Pen.LineJoin%2A> proprietà è un membro del <xref:System.Drawing.Drawing2D.LineJoin> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="d2fcd-113">Gli altri membri della <xref:System.Drawing.Drawing2D.LineJoin> enumerazione vengono <xref:System.Drawing.Drawing2D.LineJoin.Miter> e <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2fcd-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d2fcd-114">Compiling the Code</span></span>  
 <span data-ttu-id="d2fcd-115">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2fcd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2fcd-116">See also</span></span>

- [<span data-ttu-id="d2fcd-117">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="d2fcd-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
