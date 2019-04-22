---
title: 'Procedura: Visualizzare le finestre di dialogo per Windows Forms'
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
ms.openlocfilehash: b99f2273dae88faf86448da6e1d2986a83803abf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773818"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Procedura: Visualizzare le finestre di dialogo per Windows Forms
Visualizzare una finestra di dialogo nello stesso modo che visualizzare qualsiasi altra forma in un'applicazione. Form di avvio viene caricata automaticamente quando viene eseguita l'applicazione. Per rendere un secondo form o finestra di dialogo visualizzata nell'applicazione, scrivere codice per caricare e visualizzarlo. In modo analogo, per consentire il form o finestra di dialogo casella scomparsa, scrivere il codice per scaricare o nasconderlo.  
  
### <a name="to-display-a-dialog-box"></a>Per visualizzare una finestra di dialogo  
  
1. Passare al gestore dell'evento a cui si desidera aprire la finestra di dialogo. Questa situazione può verificarsi quando un comando di menu è selezionato, quando viene selezionato un pulsante o quando si verifica qualsiasi altro evento.  
  
2. Nel gestore dell'evento, aggiungere codice per aprire la finestra di dialogo. In questo esempio, un evento click del pulsante consente di visualizzare la finestra di dialogo:  
  
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
