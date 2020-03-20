---
title: Determinare su quale pannello nel controllo StatusBar è stato fatto clic
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182368"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Procedura: individuare il pannello selezionato nel controllo StatusBar Windows Form
> [!IMPORTANT]
> I <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> controlli e sostituiscono <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> aggiungono funzionalità ai controlli e ; Tuttavia, <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> i controlli e vengono mantenuti sia per la compatibilità con le versioni precedenti che per l'utilizzo futuro, se lo si desidera.  
  
 Per programmare il controllo [StatusBar Control](statusbar-control-windows-forms.md) in modo che <xref:System.Windows.Forms.StatusBar.PanelClick> risponda ai clic dell'utente, utilizzare un'istruzione case all'interno dell'evento. L'evento contiene un argomento (argomento panel), che <xref:System.Windows.Forms.StatusBarPanel>contiene un riferimento all'oggetto clicked . Utilizzando questo riferimento, potete determinare l'indice del pannello su cui è stato fatto clic e programmare di conseguenza.  
  
> [!NOTE]
> Assicurarsi <xref:System.Windows.Forms.StatusBar> che la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà del `true`controllo sia impostata su .  
  
### <a name="to-determine-which-panel-was-clicked"></a>Per determinare su quale pannello è stato fatto clic  
  
1. <xref:System.Windows.Forms.StatusBar.PanelClick> Nel gestore eventi, `Select Case` utilizzare un'istruzione `switch case` (in Visual Basic) o (Visual Cè o Visual Cè) per determinare su quale pannello è stato fatto clic esaminando l'indice del pannello su cui è stato fatto clic negli argomenti dell'evento.  
  
     Nell'esempio di codice riportato di seguito <xref:System.Windows.Forms.StatusBar> è `StatusBar1`necessaria <xref:System.Windows.Forms.StatusBarPanel> la `StatusBarPanel1` presenza, nel form, di un controllo , , e di due oggetti e `StatusBarPanel2`di .  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     (Visual C, Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Procedura: Impostare la dimensione dei pannelli della barra di stato](how-to-set-the-size-of-status-bar-panels.md)
- [Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione](walkthrough-updating-status-bar-information-at-run-time.md)
- [Cenni preliminari sul controllo StatusBar](statusbar-control-overview-windows-forms.md)
