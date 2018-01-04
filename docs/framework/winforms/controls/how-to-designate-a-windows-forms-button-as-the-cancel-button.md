---
title: 'Procedura: impostare un pulsante Windows Form come pulsante di annullamento'
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
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3f61828b4c8b65ae984685610d6d8609953376a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Procedura: impostare un pulsante Windows Form come pulsante di annullamento
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento. Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo nel form ha lo stato attivo, viene scelto un pulsante Annulla. Il pulsante di annullamento viene in genere programmato per consentire all'utente di abbandonare l'operazione senza intraprendere alcuna azione.  
  
### <a name="to-designate-the-cancel-button"></a>Per designare il pulsante Annulla  
  
1.  Imposta la proprietà <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà appropriati <xref:System.Windows.Forms.Button> controllo.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Panoramica sul controllo Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Modalità di selezione di un controllo Button di Windows Form](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedura: Designare un pulsante Windows Form come pulsante di conferma](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
