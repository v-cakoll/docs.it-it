---
title: 'Procedura: designare un pulsante Windows Form come pulsante di conferma'
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
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bf5f8dbf8718cb6a30883395d54c5cbc6bafaff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Procedura: designare un pulsante Windows Form come pulsante di conferma
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di conferma, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto INVIO, viene scelto il pulsante predefinito indipendentemente da quale altro controllo nel form ha lo stato attivo.  
  
> [!NOTE]
>  Le eccezioni si verifica se il controllo con lo stato attivo è un altro pulsante, in tal caso, verrà fatto clic sul pulsante con lo stato attivo, o una casella di testo o un controllo personalizzato che intercetta il tasto INVIO.  
  
### <a name="to-designate-the-accept-button"></a>Per designare il pulsante di conferma  
  
1.  Imposta la proprietà <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà appropriati <xref:System.Windows.Forms.Button> controllo.  
  
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
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Panoramica sul controllo Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Modalità di selezione di un controllo Button di Windows Form](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedura: Impostare un pulsante Windows Form come pulsante di annullamento](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
