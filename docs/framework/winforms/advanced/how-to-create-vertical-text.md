---
title: 'Procedura: creare testo verticale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182552"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="2ef6e-102">Procedura: creare testo verticale</span><span class="sxs-lookup"><span data-stu-id="2ef6e-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="2ef6e-103">È possibile <xref:System.Drawing.StringFormat> utilizzare un oggetto per specificare che il testo venga disegnato verticalmente anziché orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ef6e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ef6e-104">Example</span></span>  
 <span data-ttu-id="2ef6e-105">Nell'esempio seguente viene <xref:System.Drawing.StringFormatFlags.DirectionVertical> assegnato <xref:System.Drawing.StringFormat.FormatFlags%2A> il <xref:System.Drawing.StringFormat> valore alla proprietà di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="2ef6e-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="2ef6e-106">Tale <xref:System.Drawing.StringFormat> oggetto viene <xref:System.Drawing.Graphics.DrawString%2A> passato al <xref:System.Drawing.Graphics> metodo della classe.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2ef6e-107">Il <xref:System.Drawing.StringFormatFlags.DirectionVertical> valore è un <xref:System.Drawing.StringFormatFlags> membro dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="2ef6e-108">La figura seguente mostra il testo verticale:</span><span class="sxs-lookup"><span data-stu-id="2ef6e-108">The following illustration shows the vertical text:</span></span>
  
 ![Immagine che mostra il testo del carattere verticale.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ef6e-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2ef6e-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="2ef6e-111">L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2ef6e-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef6e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ef6e-112">See also</span></span>

- [<span data-ttu-id="2ef6e-113">Procedura: creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="2ef6e-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
