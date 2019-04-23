---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di annullamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 8170190145e76a86f5343bc42b39be7fb9d61a0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344143"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Procedura: Designare un pulsante Windows Forms come pulsante di annullamento
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento. Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo sul form ha lo stato attivo, viene scelto un pulsante Annulla. Il pulsante di annullamento viene in genere programmate per consentire all'utente di abbandonare un'operazione senza il commit di alcuna azione.  
  
### <a name="to-designate-the-cancel-button"></a>Per designare il pulsante Annulla  
  
1. Impostare la maschera <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà appropriata <xref:System.Windows.Forms.Button> controllo.  
  
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
- [Procedura: Rispondere alle selezioni dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante di Windows Form come pulsante di conferma](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Controllo Button](button-control-windows-forms.md)
