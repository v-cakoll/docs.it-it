---
title: 'Procedura: Rispondere alla selezione dei pulsanti Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: a10eaa3ea62df9301a53f5609b503bfabcb50a46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110071"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Procedura: Rispondere alla selezione dei pulsanti Windows Forms
L'utilizzo di base di un form Windows <xref:System.Windows.Forms.Button> controllo consiste nell'eseguire codice quando si fa clic sul pulsante.  
  
 Facendo clic su un <xref:System.Windows.Forms.Button> controllo genera inoltre un numero di altri eventi, ad esempio il <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, e <xref:System.Windows.Forms.Control.MouseUp> eventi. Se si prevede di collegare i gestori eventi per questi eventi correlati, assicurarsi che le relative azioni non sono in conflitto. Ad esempio, se facendo clic sul pulsante Cancella le informazioni che l'utente ha digitato in una casella di testo, quando si posiziona il puntatore del mouse su pulsante non visualizzerà una descrizione comando con le informazioni ora inesistente.  
  
 Se l'utente tenta di fare doppio clic il <xref:System.Windows.Forms.Button> controllo, ogni clic verranno elaborate separatamente; vale a dire, il controllo non supporta l'evento doppio clic.  
  
### <a name="to-respond-to-a-button-click"></a>Per rispondere a un clic del pulsante  
  
-   Nel pulsante `Click` <xref:System.EventHandler> scrivere il codice da eseguire. `Button1_Click` deve essere associato al controllo. Per altre informazioni, vedere [Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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

- [Panoramica del controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Controllo Button](button-control-windows-forms.md)
