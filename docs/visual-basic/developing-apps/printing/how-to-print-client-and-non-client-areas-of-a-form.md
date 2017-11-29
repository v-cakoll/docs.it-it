---
title: 'Procedura: stampare aree client e non client di un form (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- title bar [Visual Basic], printing
- printing
- borders [Visual Basic], printing
- entire form
- non-client area [Visual Basic], printing
ms.assetid: 856bb0e4-dbc3-47e2-81cd-4b376cf07757
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6dd9c42118491784d71f545c25fd3a376f66e79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-client-and-non-client-areas-of-a-form-visual-basic"></a><span data-ttu-id="65315-102">Procedura: stampare aree client e non client di un form (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65315-102">How to: Print Client and Non-Client Areas of a Form (Visual Basic)</span></span>
<span data-ttu-id="65315-103">Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> consente di stampare rapidamente un'immagine di un form così come viene visualizzata sullo schermo senza usare un componente <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="65315-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="65315-104">La procedura seguente illustra come stampare un form, incluse l'area client e l'area non client.</span><span class="sxs-lookup"><span data-stu-id="65315-104">The following procedure shows how to print a form, including both the client area and the non-client area.</span></span> <span data-ttu-id="65315-105">L'area non client include la barra del titolo, i bordi e le barre di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="65315-105">The non-client area includes the title bar, borders, and scroll bars.</span></span>  
  
 <span data-ttu-id="65315-106">I controlli PowerPacks non sono più inclusi in Visual Studio, ma è possibile scaricarli dall' [Area download](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="65315-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-both-the-client-and-the-non-client-areas-of-a-form"></a><span data-ttu-id="65315-107">Per stampare le aree client e non client di un form</span><span class="sxs-lookup"><span data-stu-id="65315-107">To print both the client and the non-client areas of a form</span></span>  
  
1.  <span data-ttu-id="65315-108">Nella **casella degli strumenti**fare clic sulla scheda **Visual Basic PowerPacks** e quindi trascinare il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> nel form.</span><span class="sxs-lookup"><span data-stu-id="65315-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="65315-109">Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> viene aggiunto alla barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="65315-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="65315-110">Nella finestra **Proprietà** impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> su <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="65315-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="65315-111">Aggiungere il codice seguente nel gestore eventi appropriato (ad esempio, nel gestore eventi `Click` per un `Button`di stampa).</span><span class="sxs-lookup"><span data-stu-id="65315-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a Print `Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="65315-112">In alcuni sistemi operativi il testo o la grafica disegnati mediante i metodi <xref:System.Drawing.Graphics> potrebbero non essere stampati correttamente.</span><span class="sxs-lookup"><span data-stu-id="65315-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="65315-113">In questo caso, usare il metodo di stampa compatibile: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`).</span><span class="sxs-lookup"><span data-stu-id="65315-113">In this case, use the compatible printing method: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65315-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65315-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="65315-115">Componente PrintForm</span><span class="sxs-lookup"><span data-stu-id="65315-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="65315-116">Procedura: Stampare un form scorrevole</span><span class="sxs-lookup"><span data-stu-id="65315-116">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
