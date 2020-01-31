---
title: 'Procedura: stampare grafica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740650"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Procedura: Stampare grafica in Windows Form
Spesso è necessario stampare elementi grafici nell'applicazione basata su Windows. La classe <xref:System.Drawing.Graphics> fornisce metodi per disegnare oggetti in un dispositivo, ad esempio una schermata o una stampante.  
  
### <a name="to-print-graphics"></a>Per stampare grafica  
  
1. Aggiungere un componente <xref:System.Drawing.Printing.PrintDocument> al modulo.  
  
2. Nel gestore dell'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> usare la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs> per indicare alla stampante il tipo di grafica da stampare.  
  
     Nell'esempio di codice riportato di seguito viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione. Il rettangolo presenta il percorso e le dimensioni seguenti: a partire da 100, 150 con larghezza 250 e altezza 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Supporto per la stampa in Windows Forms](windows-forms-print-support.md)
