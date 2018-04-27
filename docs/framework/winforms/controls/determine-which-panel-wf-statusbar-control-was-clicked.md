---
title: 'Procedura: individuare il pannello selezionato nel controllo StatusBar Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35dc392ed95a5dbe8182b1adbd05affea55d0baa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Procedura: individuare il pannello selezionato nel controllo StatusBar Windows Form
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si Scegliere.  
  
 Al programma il [controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) controllo per rispondere alle selezioni, utilizzare un'istruzione case all'interno di <xref:System.Windows.Forms.StatusBar.PanelClick> evento. L'evento contiene un argomento (pannello), che contiene un riferimento all'oggetto selezionato <xref:System.Windows.Forms.StatusBarPanel>. Utilizzando questo riferimento, è possibile determinare l'indice del pannello selezionato e programmare di conseguenza.  
  
> [!NOTE]
>  Verificare che il <xref:System.Windows.Forms.StatusBar> del controllo <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> è impostata su `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Per determinare il pannello selezionato  
  
1.  Nel <xref:System.Windows.Forms.StatusBar.PanelClick> gestore dell'evento, utilizzare un `Select Case` (in Visual Basic) o `switch case` (Visual c# o [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) istruzione per determinare il pannello selezionato esaminando l'indice del pannello selezionato negli argomenti dell'evento.  
  
     Esempio di codice seguente è necessario che il form di un <xref:System.Windows.Forms.StatusBar> controllo `StatusBar1`e due <xref:System.Windows.Forms.StatusBarPanel> oggetti, `StatusBarPanel1` e `StatusBarPanel2`.  
  
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
  
     (Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
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
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Procedura: Impostare la dimensione dei pannelli della barra di stato](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Cenni preliminari sul controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
