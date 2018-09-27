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
ms.openlocfilehash: dd006f669ab6f0186bbcc7d1c76f9852ab6e8f60
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399099"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a>Procedura: aggiungere pannelli a un controllo StatusBar
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungano funzionalità rispetto al <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si Scegliere.  
  
 L'area programmabile all'interno di un [controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) controllo è costituito da istanze del <xref:System.Windows.Forms.StatusBarPanel> classe. Questi vengono aggiunti tramite aggiunte al <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> classe.  
  
### <a name="to-add-panels-to-a-status-bar"></a>Per aggiungere pannelli a una barra di stato  
  
1.  In una procedura, creare pannelli della barra di stato vengono aggiunte al <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>. Specificare le impostazioni delle proprietà per singole pannelli utilizzando il relativo indice passato tramite la <xref:System.Windows.Forms.StatusBar.Panels%2A> proprietà.  
  
     Nell'esempio di codice seguente, il percorso impostato per il percorso dell'icona è il **documenti** cartella. Poiché si può presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella, viene usato questo percorso. Questa scelta consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire in modo sicuro l'applicazione. Nell'esempio seguente richiede un modulo con un <xref:System.Windows.Forms.StatusBar> controllo già aggiunto.  
  
    > [!NOTE]
    >  Il <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> è una raccolta in base zero, il codice dovrebbe procedere di conseguenza.  
  
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
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Finestra di dialogo Editor della raccolta](https://msdn.microsoft.com/library/53fb3aad-bffa-4da5-ac89-8438e6fc803c)  
 [Procedura: Impostare la dimensione dei pannelli della barra di stato](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [Cenni preliminari sul controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
