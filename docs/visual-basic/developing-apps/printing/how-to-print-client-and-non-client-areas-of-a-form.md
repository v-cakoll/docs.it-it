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
# <a name="how-to-print-client-and-non-client-areas-of-a-form-visual-basic"></a>Procedura: stampare aree client e non client di un form (Visual Basic)
Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> consente di stampare rapidamente un'immagine di un form così come viene visualizzata sullo schermo senza usare un componente <xref:System.Drawing.Printing.PrintDocument> . La procedura seguente illustra come stampare un form, incluse l'area client e l'area non client. L'area non client include la barra del titolo, i bordi e le barre di scorrimento.  
  
 I controlli PowerPacks non sono più inclusi in Visual Studio, ma è possibile scaricarli dall' [Area download](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-both-the-client-and-the-non-client-areas-of-a-form"></a>Per stampare le aree client e non client di un form  
  
1.  Nella **casella degli strumenti**fare clic sulla scheda **Visual Basic PowerPacks** e quindi trascinare il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> nel form.  
  
     Il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> viene aggiunto alla barra dei componenti.  
  
2.  Nella finestra **Proprietà** impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> su <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Aggiungere il codice seguente nel gestore eventi appropriato (ad esempio, nel gestore eventi `Click` per un `Button`di stampa).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  In alcuni sistemi operativi il testo o la grafica disegnati mediante i metodi <xref:System.Drawing.Graphics> potrebbero non essere stampati correttamente. In questo caso, usare il metodo di stampa compatibile: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [Componente PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [Procedura: Stampare un form scorrevole](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
