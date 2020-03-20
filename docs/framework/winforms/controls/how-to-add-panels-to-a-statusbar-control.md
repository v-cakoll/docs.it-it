---
title: 'Procedura: aggiungere pannelli a un controllo StatusBar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: 386c8cae425c458ddf4c446a454ae4213761e651
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142199"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a>Procedura: aggiungere pannelli a un controllo StatusBar
> [!IMPORTANT]
> I <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> controlli e sostituiscono <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> aggiungono funzionalità ai controlli e ; Tuttavia, <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> i controlli e vengono mantenuti sia per la compatibilità con le versioni precedenti che per l'utilizzo futuro, se lo si desidera.  
  
 L'area programmabile all'interno di un <xref:System.Windows.Forms.StatusBarPanel> [StatusBar Control](statusbar-control-windows-forms.md) controllo è costituito da istanze della classe. Questi vengono aggiunti tramite <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> aggiunte alla classe.  
  
### <a name="to-add-panels-to-a-status-bar"></a>Per aggiungere pannelli a una barra di stato  
  
1. In una procedura, creare pannelli della barra <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>di stato aggiungendoli al file . Specificare le impostazioni delle proprietà per i <xref:System.Windows.Forms.StatusBar.Panels%2A> singoli pannelli utilizzando il relativo indice passato tramite la proprietà.  
  
     Nell'esempio di codice seguente, il percorso impostato per il percorso dell'icona è la cartella **Documenti.** Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa cartella. La scelta di questa posizione consente inoltre agli utenti con livelli di accesso minimi al sistema di eseguire in modo sicuro l'applicazione. Nell'esempio seguente è <xref:System.Windows.Forms.StatusBar> necessario un form con un controllo già aggiunto.  
  
    > [!NOTE]
    > Il <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> è una raccolta in base zero, pertanto il codice deve procedere di conseguenza.  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Finestra di dialogo Editor dell'insieme](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))
- [Procedura: Impostare la dimensione dei pannelli della barra di stato](how-to-set-the-size-of-status-bar-panels.md)
- [Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione](walkthrough-updating-status-bar-information-at-run-time.md)
- [Procedura: individuare il pannello selezionato nel controllo StatusBar Windows Form](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Cenni preliminari sul controllo StatusBar](statusbar-control-overview-windows-forms.md)
