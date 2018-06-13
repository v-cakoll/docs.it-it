---
title: 'Procedura: aggiungere e rimuovere schede tramite il controllo TabControl Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 938dbb4ae695f22d6daff417fbf7176800420aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525604"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Procedura: aggiungere e rimuovere schede tramite il controllo TabControl Windows Form
Per impostazione predefinita, un <xref:System.Windows.Forms.TabControl> controllo contiene due <xref:System.Windows.Forms.TabPage> controlli. È possibile accedere a queste schede tramite il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
### <a name="to-add-a-tab-programmatically"></a>Per aggiungere una scheda a livello di codice  
  
-   Utilizzare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> metodo il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a>Per rimuovere una scheda a livello di codice  
  
-   Per rimuovere le schede selezionate, utilizzare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> metodo il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
     oppure  
  
-   Per rimuovere tutte le schede, usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> metodo il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica del controllo TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Procedura: Aggiungere un controllo a un oggetto TabPage](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Procedura: Disabilitare le schede](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Procedura: Modificare l'aspetto del controllo TabControl di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
