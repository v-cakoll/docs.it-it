---
title: 'Procedura: visualizzare le finestre di dialogo'
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
ms.openlocfilehash: dd04a06eaa0dd7583ef2f72edb4cffa99aaaa60c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739457"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Procedura: Visualizzare le finestre di dialogo per Windows Form
Viene visualizzata una finestra di dialogo in modo analogo alla visualizzazione di qualsiasi altro modulo in un'applicazione. Il modulo di avvio viene caricato automaticamente quando viene eseguita l'applicazione. Per fare in modo che nell'applicazione venga visualizzato un secondo form o una finestra di dialogo, scrivere il codice per caricarlo e visualizzarlo. Analogamente, per far scomparire il form o la finestra di dialogo, scrivere il codice per scaricarlo o nasconderlo.  
  
### <a name="to-display-a-dialog-box"></a>Per visualizzare una finestra di dialogo  
  
1. Passare al gestore eventi con il quale si desidera aprire la finestra di dialogo. Questa situazione può verificarsi quando si seleziona un comando di menu, quando si fa clic su un pulsante o quando si verifica un altro evento.  
  
2. Nel gestore eventi aggiungere il codice per aprire la finestra di dialogo. In questo esempio viene usato un evento clic del pulsante per visualizzare la finestra di dialogo:  
  
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
