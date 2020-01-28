---
title: Rispondere ai clic sui controlli Button
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
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735721"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Procedura: Rispondere alla selezione dei pulsanti di Windows Form
L'uso più semplice di un controllo di <xref:System.Windows.Forms.Button> Windows Forms consiste nell'eseguire codice quando si fa clic sul pulsante.  
  
 Se si fa clic su un controllo <xref:System.Windows.Forms.Button> viene generato anche un numero di altri eventi, ad esempio gli eventi <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>e <xref:System.Windows.Forms.Control.MouseUp>. Se si intende alleghi i gestori eventi per questi eventi correlati, assicurarsi che le azioni non siano in conflitto. Se, ad esempio, si fa clic sul pulsante per cancellare le informazioni digitate dall'utente in una casella di testo, la sospensione del puntatore del mouse sul pulsante non dovrebbe visualizzare una descrizione comando con le informazioni attualmente inesistenti.  
  
 Se l'utente tenta di fare doppio clic sul controllo <xref:System.Windows.Forms.Button>, ogni clic verrà elaborato separatamente. ovvero, il controllo non supporta l'evento di doppio clic.  
  
### <a name="to-respond-to-a-button-click"></a>Per rispondere a un clic del pulsante  
  
- Nel `Click` del pulsante <xref:System.EventHandler> scrivere il codice per l'esecuzione. `Button1_Click` deve essere associato al controllo. Per altre informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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

- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Controllo Button](button-control-windows-forms.md)
