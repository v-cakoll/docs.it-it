---
title: Rispondere ai clic sui controlli Button
description: Informazioni su come rispondere a Windows Forms clic sui pulsanti. L'uso più semplice di un controllo pulsante Windows Forms consiste nell'eseguire codice quando si fa clic sul pulsante.
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
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619728"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Procedura: rispondere alla selezione dei pulsanti di Windows Form
L'uso più semplice di un <xref:System.Windows.Forms.Button> controllo Windows Forms consiste nell'eseguire codice quando si fa clic sul pulsante.  
  
 Se si fa clic su un <xref:System.Windows.Forms.Button> controllo, viene generato anche un numero di altri eventi, ad esempio gli <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseDown> eventi, e <xref:System.Windows.Forms.Control.MouseUp> . Se si intende alleghi i gestori eventi per questi eventi correlati, assicurarsi che le azioni non siano in conflitto. Se, ad esempio, si fa clic sul pulsante per cancellare le informazioni digitate dall'utente in una casella di testo, la sospensione del puntatore del mouse sul pulsante non dovrebbe visualizzare una descrizione comando con le informazioni attualmente inesistenti.  
  
 Se l'utente tenta di fare doppio clic sul <xref:System.Windows.Forms.Button> controllo, ogni clic viene elaborato separatamente, ovvero il controllo non supporta l'evento di doppio clic.  
  
### <a name="to-respond-to-a-button-click"></a>Per rispondere a un clic del pulsante  
  
- Nel pulsante `Click` <xref:System.EventHandler> scrivere il codice da eseguire. `Button1_Click`deve essere associato al controllo. Per altre informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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

- [Cenni preliminari sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Controllo Button](button-control-windows-forms.md)
