---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di conferma'
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
ms.openlocfilehash: 1e24e410681b03a92c8c48b187dde569eccdc1c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222146"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Procedura: Designare un pulsante Windows Forms come pulsante di conferma
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di conferma, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto INVIO, viene scelto il pulsante predefinito indipendentemente da quale altro controllo sul form ha lo stato attivo.  
  
> [!NOTE]
>  Le eccezioni a questo si verifica se il controllo con lo stato attivo è un altro pulsante, in tal caso, verrà fatto clic sul pulsante con lo stato attivo, o una casella di testo su più righe o un controllo personalizzato che intercetta il tasto INVIO.  
  
### <a name="to-designate-the-accept-button"></a>Per designare il pulsante accept  
  
1.  Impostare la maschera <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà appropriata <xref:System.Windows.Forms.Button> controllo.  
  
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
- [Panoramica del controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Forms come pulsante di annullamento](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Controllo Button](button-control-windows-forms.md)
