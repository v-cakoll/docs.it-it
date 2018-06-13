---
title: 'Procedura: visualizzare le finestre di dialogo per Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: a25fe86c4dde1fed69e192956d77615bf2a70402
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537424"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Procedura: visualizzare le finestre di dialogo per Windows Form
Viene visualizzata una finestra di dialogo nello stesso modo che visualizzare qualsiasi altra forma in un'applicazione. Il form di avvio carica automaticamente quando viene eseguita l'applicazione. Per rendere un secondo form o finestra di dialogo visualizzata nell'applicazione, scrivere codice per caricare e visualizzarlo. Analogamente, per rendere il modulo o finestra di dialogo casella scomparsa, scrivere il codice per scaricare o nasconderla.  
  
### <a name="to-display-a-dialog-box"></a>Per visualizzare una finestra di dialogo  
  
1.  Passare al gestore dell'evento a cui si desidera aprire la finestra di dialogo. Questa situazione può verificarsi quando un comando di menu è selezionato, quando viene premuto un pulsante o quando si verifica qualsiasi altro evento.  
  
2.  Nel gestore eventi, aggiungere il codice per aprire la finestra di dialogo. In questo esempio viene utilizzato un evento clic sul pulsante per visualizzare la finestra di dialogo:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
