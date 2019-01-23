---
title: "Procedura: Stampare l'Area Client di un Form (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- client area [Visual Basic], printing
ms.assetid: c06c9c0e-bc07-48cd-9596-e29a2ff96236
ms.openlocfilehash: 2c808b480c38fc34006dcdf5832a814dfef1c62c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505627"
---
# <a name="how-to-print-the-client-area-of-a-form-visual-basic"></a><span data-ttu-id="abf9f-102">Procedura: Stampare l'Area Client di un Form (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abf9f-102">How to: Print the Client Area of a Form (Visual Basic)</span></span>
<span data-ttu-id="abf9f-103">Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> consente di stampare rapidamente un'immagine di un form senza usare un componente <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="abf9f-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="abf9f-104">La procedura seguente illustra come stampare solo l'area client di un form, senza la barra del titolo, i bordi e le barre di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="abf9f-104">The following procedure shows how to print just the client area of a form, without the title bar, borders, and scroll bars.</span></span>  
  
 <span data-ttu-id="abf9f-105">I controlli PowerPacks non sono più inclusi in Visual Studio, ma è possibile scaricarli dall' [Area download](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="abf9f-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-client-area-of-a-form"></a><span data-ttu-id="abf9f-106">Per stampare l'area client di un form</span><span class="sxs-lookup"><span data-stu-id="abf9f-106">To print the client area of a form</span></span>  
  
1.  <span data-ttu-id="abf9f-107">Nella **casella degli strumenti**fare clic sulla scheda **Visual Basic PowerPacks** e quindi trascinare il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> nel form.</span><span class="sxs-lookup"><span data-stu-id="abf9f-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="abf9f-108">Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> viene aggiunto alla barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="abf9f-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="abf9f-109">Nella finestra **Proprietà** impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> su <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="abf9f-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="abf9f-110">Aggiungere il codice seguente nel gestore eventi appropriato (ad esempio nel gestore eventi `Click` per un controllo **Print**`Button`).</span><span class="sxs-lookup"><span data-stu-id="abf9f-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.ClientAreaOnly)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="abf9f-111">In alcuni sistemi operativi il testo o la grafica disegnati mediante i metodi <xref:System.Drawing.Graphics> potrebbero non essere stampati correttamente.</span><span class="sxs-lookup"><span data-stu-id="abf9f-111">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="abf9f-112">In questo caso, usare il metodo di stampa compatibile: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`</span><span class="sxs-lookup"><span data-stu-id="abf9f-112">In this case, use the compatible printing method: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf9f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abf9f-113">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>
- [<span data-ttu-id="abf9f-114">Componente PrintForm</span><span class="sxs-lookup"><span data-stu-id="abf9f-114">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
- [<span data-ttu-id="abf9f-115">Procedura: Stampare aree client e non client di un form</span><span class="sxs-lookup"><span data-stu-id="abf9f-115">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [<span data-ttu-id="abf9f-116">Procedura: Stampare un form scorrevole</span><span class="sxs-lookup"><span data-stu-id="abf9f-116">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
