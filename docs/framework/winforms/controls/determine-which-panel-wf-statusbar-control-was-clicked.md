---
title: Determinare il pannello in cui è stato fatto clic sul controllo StatusBar
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
ms.openlocfilehash: 94619f8bd426a42e5dafa0db99880e20d24f9963
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746019"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Procedura: individuare il pannello selezionato nel controllo StatusBar Windows Form
> [!IMPORTANT]
> I controlli <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel>; Tuttavia, se si sceglie, i controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro.  
  
 Per programmare il controllo di [controllo StatusBar](statusbar-control-windows-forms.md) per rispondere ai clic dell'utente, usare un'istruzione case all'interno dell'evento <xref:System.Windows.Forms.StatusBar.PanelClick>. L'evento contiene un argomento (argomento Panel), che contiene un riferimento al <xref:System.Windows.Forms.StatusBarPanel>selezionato. Utilizzando questo riferimento, è possibile determinare l'indice del pannello selezionato e programmare di conseguenza.  
  
> [!NOTE]
> Verificare che la proprietà <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> del controllo <xref:System.Windows.Forms.StatusBar> sia impostata su `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Per determinare il pannello selezionato  
  
1. Nel gestore dell'evento <xref:System.Windows.Forms.StatusBar.PanelClick> usare un'istruzione `Select Case` (in Visual Basic) o `switch case` (Visual C# o Visual C++) per determinare il pannello su cui è stato fatto clic, esaminando l'indice del pannello selezionato negli argomenti dell'evento.  
  
     Nell'esempio di codice seguente è richiesta la presenza, nel formato, di un controllo <xref:System.Windows.Forms.StatusBar>, `StatusBar1`e due oggetti <xref:System.Windows.Forms.StatusBarPanel>, `StatusBarPanel1` e `StatusBarPanel2`.  
  
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
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
- [Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione](walkthrough-updating-status-bar-information-at-run-time.md)
- [Cenni preliminari sul controllo StatusBar](statusbar-control-overview-windows-forms.md)
