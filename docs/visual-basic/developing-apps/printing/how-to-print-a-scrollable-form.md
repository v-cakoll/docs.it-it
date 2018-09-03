---
title: 'Procedura: stampare un form scorrevole (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: 4a509b7c48f2bff705bc95e58fb88252cb8ca4b9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486620"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a><span data-ttu-id="9e5d7-102">Procedura: stampare un form scorrevole (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e5d7-102">How to: Print a Scrollable Form (Visual Basic)</span></span>
<span data-ttu-id="9e5d7-103">Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> consente di stampare rapidamente un'immagine di un form senza usare un componente <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="9e5d7-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="9e5d7-104">Per impostazione predefinita, viene stampata solo la parte visibile del form. Se un utente ha ridimensionato il form in fase di esecuzione, l'immagine potrebbe non essere stampata come previsto.</span><span class="sxs-lookup"><span data-stu-id="9e5d7-104">By default, only the currently visible part of the form is printed; if a user has resized the form at run time, the image may not print as intended.</span></span> <span data-ttu-id="9e5d7-105">La procedura seguente illustra come stampare l'intera area client di un form scorrevole, anche se il form è stato ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="9e5d7-105">The following procedure shows how to print the complete client area of a scrollable form, even if the form has been resized.</span></span>  
  
 <span data-ttu-id="9e5d7-106">I controlli PowerPacks non sono inclusi in Visual Studio, ma è possibile scaricarli dal [area download](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="9e5d7-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a><span data-ttu-id="9e5d7-107">Per stampare l'intera area client di un form scorrevole</span><span class="sxs-lookup"><span data-stu-id="9e5d7-107">To print the complete client area of a scrollable form</span></span>  
  
1.  <span data-ttu-id="9e5d7-108">Nella **casella degli strumenti**fare clic sulla scheda **Visual Basic PowerPacks** e quindi trascinare il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> nel form.</span><span class="sxs-lookup"><span data-stu-id="9e5d7-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="9e5d7-109">Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> verrà aggiunto alla barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="9e5d7-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component will be added to the component tray.</span></span>  
  
2.  <span data-ttu-id="9e5d7-110">Nella finestra **Proprietà** impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> su <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="9e5d7-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="9e5d7-111">Aggiungere il codice seguente nel gestore eventi appropriato (ad esempio nel gestore eventi `Click` per un controllo **Print**`Button`).</span><span class="sxs-lookup"><span data-stu-id="9e5d7-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9e5d7-112">In alcuni sistemi operativi il testo o la grafica disegnati mediante i metodi <xref:System.Drawing.Graphics> potrebbero non essere stampati correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e5d7-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="9e5d7-113">In questo caso, non sarà possibile eseguire la stampa con il parametro `Scrollable` .</span><span class="sxs-lookup"><span data-stu-id="9e5d7-113">In this case, you will not be able to print with the `Scrollable` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5d7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e5d7-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="9e5d7-115">Componente PrintForm</span><span class="sxs-lookup"><span data-stu-id="9e5d7-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="9e5d7-116">Procedura: Stampare l'area client di un form</span><span class="sxs-lookup"><span data-stu-id="9e5d7-116">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="9e5d7-117">Procedura: Stampare aree client e non client di un form</span><span class="sxs-lookup"><span data-stu-id="9e5d7-117">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
