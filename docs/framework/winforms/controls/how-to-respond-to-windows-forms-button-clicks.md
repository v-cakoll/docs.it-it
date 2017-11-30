---
title: 'Procedura: rispondere alla selezione dei pulsanti di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 923eb7d1b1b5b442ce897619253a958019b239a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Procedura: rispondere alla selezione dei pulsanti di Windows Form
L'utilizzo di base di un Windows Form <xref:System.Windows.Forms.Button> controllo consiste nell'esecuzione di codice quando si fa clic sul pulsante.  
  
 Fare clic su un <xref:System.Windows.Forms.Button> controllo genera anche un numero di altri eventi, ad esempio il <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, e <xref:System.Windows.Forms.Control.MouseUp> eventi. Se si prevede di collegare gestori eventi per questi eventi correlati, assicurarsi che le relative azioni non sono in conflitto. Ad esempio, se facendo clic sul pulsante Cancella le informazioni che l'utente è tipizzata in una casella di testo, posizionando il puntatore del mouse sul pulsante dovrebbe non visualizzare una descrizione comandi che contiene queste informazioni ora-inesistente.  
  
 Se l'utente tenta di fare doppio clic su di <xref:System.Windows.Forms.Button> (controllo), verranno elaborati separatamente ogni clic; vale a dire, il controllo non supporta l'evento di doppio clic.  
  
### <a name="to-respond-to-a-button-click"></a>Per rispondere a un clic del pulsante  
  
-   Il pulsante `Click` <xref:System.EventHandler> scrivere il codice da eseguire. `Button1_Click`deve essere associato al controllo. Per ulteriori informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Form](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul controllo Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Modalità di selezione di un controllo Button di Windows Form](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
