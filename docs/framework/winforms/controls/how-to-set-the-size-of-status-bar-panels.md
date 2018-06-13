---
title: 'Procedura: impostare la dimensione dei pannelli della barra di stato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: d708b94d02b4f1c1e2f00101e6e394043a6057ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533780"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Procedura: impostare la dimensione dei pannelli della barra di stato
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStripStatusLabel> sostituisca il controllo <xref:System.Windows.Forms.StatusBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.StatusBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Ogni istanza del <xref:System.Windows.Forms.StatusBarPanel> classe all'interno di un [controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) controllo ha un numero di proprietà dinamiche che determinano la larghezza e il ridimensionamento in fase di esecuzione.  
  
### <a name="to-set-the-size-of-a-panel"></a>Per impostare le dimensioni di un pannello  
  
1.  In una routine, impostare il <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, e <xref:System.Windows.Forms.StatusBarPanel.Width%2A> proprietà (o qualsiasi sottoinsieme al suo interno) per la barra di stato visualizza pannelli utilizzando il relativo indice passato tramite la <xref:System.Windows.Forms.StatusBar.Panels%2A> proprietà del <xref:System.Windows.Forms.StatusBarPanel> insieme.  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [Cenni preliminari sul controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
