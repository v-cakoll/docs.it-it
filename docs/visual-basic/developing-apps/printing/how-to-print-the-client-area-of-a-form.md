---
title: "Procedura: stampare l'area client di un form (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- client area [Visual Basic], printing
ms.assetid: c06c9c0e-bc07-48cd-9596-e29a2ff96236
ms.openlocfilehash: 361db89f0880a03273aac7fc36b5c5faa825486f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583991"
---
# <a name="how-to-print-the-client-area-of-a-form-visual-basic"></a>Procedura: stampare l'area client di un form (Visual Basic)
Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> consente di stampare rapidamente un'immagine di un form senza usare un componente <xref:System.Drawing.Printing.PrintDocument> . La procedura seguente illustra come stampare solo l'area client di un form, senza la barra del titolo, i bordi e le barre di scorrimento.  
  
 I controlli PowerPacks non sono più inclusi in Visual Studio, ma è possibile scaricarli dall' [Area download](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-the-client-area-of-a-form"></a>Per stampare l'area client di un form  
  
1.  Nella **casella degli strumenti**fare clic sulla scheda **Visual Basic PowerPacks** e quindi trascinare il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> nel form.  
  
     Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> viene aggiunto alla barra dei componenti.  
  
2.  Nella finestra **Proprietà** impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> su <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Aggiungere il codice seguente nel gestore eventi appropriato (ad esempio nel gestore eventi `Click` per un controllo **Print**`Button`).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.ClientAreaOnly)  
    ```  
  
    > [!NOTE]
    >  In alcuni sistemi operativi il testo o la grafica disegnati mediante i metodi <xref:System.Drawing.Graphics> potrebbero non essere stampati correttamente. In questo caso, usare il metodo di stampa compatibile: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [Componente PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [Procedura: Stampare aree client e non client di un form](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [Procedura: Stampare un form scorrevole](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
