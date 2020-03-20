---
title: 'Procedura: visualizzare le finestre di dialogoHow to: Display Dialog Boxes'
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
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181978"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Procedura: visualizzare le finestre di dialogo per Windows Form
Si visualizza una finestra di dialogo nello stesso modo in cui si visualizza qualsiasi altro form in un'applicazione. Il form di avvio viene caricato automaticamente quando viene eseguita l'applicazione. Per visualizzare un secondo form o una finestra di dialogo nell'applicazione, scrivere il codice per caricarlo e visualizzarlo. Analogamente, per far scomparire il form o la finestra di dialogo, scrivere il codice per scaricarlo o nasconderlo.  
  
### <a name="to-display-a-dialog-box"></a>Per visualizzare una finestra di dialogo  
  
1. Passare al gestore eventi con cui si desidera aprire la finestra di dialogo. Ciò può verificarsi quando viene selezionato un comando di menu, quando si fa clic su un pulsante o quando si verifica qualsiasi altro evento.  
  
2. Nel gestore eventi aggiungere il codice per aprire la finestra di dialogo. In questo esempio, un evento clic sul pulsante viene utilizzato per visualizzare la finestra di dialogo:In this example, a button-click event is used to show the dialog box:  
  
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
