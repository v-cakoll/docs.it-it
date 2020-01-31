---
title: Designare un pulsante come pulsante Annulla
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743256"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Procedura: Impostare un pulsante Windows Form come pulsante di annullamento
In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante Annulla. Quando l'utente preme il tasto ESC, viene fatto clic su un pulsante Annulla, indipendentemente da quale altro controllo nel form abbia lo stato attivo. Un pulsante di questo tipo è in genere programmato per consentire all'utente di uscire rapidamente da un'operazione senza eseguire il commit in alcuna azione.  
  
### <a name="to-designate-the-cancel-button"></a>Per impostare il pulsante Annulla  
  
1. Impostare la proprietà <xref:System.Windows.Forms.Form.CancelButton%2A> del modulo sul controllo <xref:System.Windows.Forms.Button> appropriato.  
  
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

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Form come pulsante di conferma](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Controllo Button](button-control-windows-forms.md)
