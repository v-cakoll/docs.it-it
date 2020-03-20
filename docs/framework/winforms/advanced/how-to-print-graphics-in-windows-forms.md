---
title: 'Procedura: stampare elementi graficiHow to: Print Graphics'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182527"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Procedura: stampare grafica in Windows Form
Spesso, è consigliabile stampare grafica nell'applicazione basata su Windows. La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare oggetti a un dispositivo, ad esempio uno schermo o una stampante.  
  
### <a name="to-print-graphics"></a>Per stampare elementi grafici  
  
1. Aggiungere <xref:System.Drawing.Printing.PrintDocument> un componente al form.  
  
2. <xref:System.Drawing.Printing.PrintDocument.PrintPage> Nel gestore eventi <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> utilizzare la <xref:System.Drawing.Printing.PrintPageEventArgs> proprietà della classe per indicare alla stampante il tipo di grafica da stampare.  
  
     Esempio di codice seguente viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione. Il rettangolo ha la seguente posizione e dimensioni: a partire da 100, 150 con una larghezza di 250 e un'altezza di 250.  
  
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
  
     (Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)
