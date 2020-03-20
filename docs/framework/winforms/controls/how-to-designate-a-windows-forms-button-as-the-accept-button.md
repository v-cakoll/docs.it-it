---
title: Designare un pulsante come pulsante Accetta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142147"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Procedura: designare un pulsante Windows Form come pulsante di conferma
In qualsiasi Windows Form è <xref:System.Windows.Forms.Button> possibile designare un controllo come pulsante di accettazione, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto INVIO, viene fatto clic sul pulsante predefinito indipendentemente dall'altro controllo del form ha lo stato attivo.  
  
> [!NOTE]
> Le eccezioni a questo sono quando il controllo con lo stato attivo è un altro pulsante, in tal caso, verrà fatto clic sul pulsante con lo stato attivo, o una casella di testo su più righe o un controllo personalizzato che intercetta il tasto INVIO.  
  
### <a name="to-designate-the-accept-button"></a>Per designare il pulsante di accettazione  
  
1. Impostare la <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà del <xref:System.Windows.Forms.Button> form sul controllo appropriato.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Cenni preliminari sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: impostare un pulsante Windows Form come pulsante di annullamento](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Controllo Button](button-control-windows-forms.md)
