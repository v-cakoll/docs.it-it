---
title: Designare un pulsante come pulsante accetta
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743276"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Procedura: Designare un pulsante Windows Form come pulsante di conferma
In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante accetta, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto invio, viene fatto clic sul pulsante predefinito, indipendentemente da quale altro controllo nel form abbia lo stato attivo.  
  
> [!NOTE]
> Le eccezioni a questo si verificano quando il controllo con lo stato attivo è un altro pulsante, in tal caso verrà fatto clic sul pulsante con lo stato attivo o su una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.  
  
### <a name="to-designate-the-accept-button"></a>Per impostare il pulsante accetta  
  
1. Impostare la proprietà <xref:System.Windows.Forms.Form.AcceptButton%2A> del modulo sul controllo <xref:System.Windows.Forms.Button> appropriato.  
  
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
- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Impostare un pulsante Windows Form come pulsante di annullamento](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Controllo Button](button-control-windows-forms.md)
