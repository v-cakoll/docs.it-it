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
ms.openlocfilehash: 7d66bf147a220bdcdfd32a703d3407817a184a54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521472"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="91bb9-102">Procedura: creare testo verticale</span><span class="sxs-lookup"><span data-stu-id="91bb9-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="91bb9-103">È possibile utilizzare un <xref:System.Drawing.StringFormat> per specificare che il testo da disegnare verticalmente anziché in orizzontale.</span><span class="sxs-lookup"><span data-stu-id="91bb9-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91bb9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="91bb9-104">Example</span></span>  
 <span data-ttu-id="91bb9-105">Nell'esempio seguente viene assegnato il valore <xref:System.Drawing.StringFormatFlags.DirectionVertical> per il <xref:System.Drawing.StringFormat.FormatFlags%2A> proprietà di un <xref:System.Drawing.StringFormat> oggetto.</span><span class="sxs-lookup"><span data-stu-id="91bb9-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="91bb9-106">Che <xref:System.Drawing.StringFormat> oggetto viene passato per il <xref:System.Drawing.Graphics.DrawString%2A> metodo la <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="91bb9-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="91bb9-107">Il valore <xref:System.Drawing.StringFormatFlags.DirectionVertical> è membro il <xref:System.Drawing.StringFormatFlags> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="91bb9-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="91bb9-108">Nella figura seguente mostra il testo verticale.</span><span class="sxs-lookup"><span data-stu-id="91bb9-108">The following illustration shows the vertical text.</span></span>  
  
 <span data-ttu-id="91bb9-109">![Testo caratteri](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span><span class="sxs-lookup"><span data-stu-id="91bb9-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91bb9-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="91bb9-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="91bb9-111">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="91bb9-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91bb9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91bb9-112">See Also</span></span>  
 [<span data-ttu-id="91bb9-113">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="91bb9-113">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
