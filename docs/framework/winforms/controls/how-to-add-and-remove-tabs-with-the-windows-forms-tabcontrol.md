---
title: Aggiungere e rimuovere schede con TabControl
description: Informazioni su come aggiungere e rimuovere schede con il controllo Windows Forms TabControl, che contiene due controlli TabPage. Accedere a queste schede tramite la proprietà TabPages.
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
ms.openlocfilehash: 7e67d0bbc13bd7d9c8835dc6fb9b9c5c9333b8bf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618077"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Procedura: aggiungere e rimuovere schede tramite il controllo TabControl Windows Form
Per impostazione predefinita, un <xref:System.Windows.Forms.TabControl> controllo contiene due <xref:System.Windows.Forms.TabPage> controlli. È possibile accedere a queste schede tramite la <xref:System.Windows.Forms.TabControl.TabPages%2A> Proprietà.  
  
### <a name="to-add-a-tab-programmatically"></a>Per aggiungere una scheda a livello di codice  
  
- Usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> metodo della <xref:System.Windows.Forms.TabControl.TabPages%2A> Proprietà.  
  
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
  
- Per rimuovere le schede selezionate, utilizzare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> metodo della <xref:System.Windows.Forms.TabControl.TabPages%2A> Proprietà.  
  
     -oppure-  
  
- Per rimuovere tutte le schede, usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> metodo della <xref:System.Windows.Forms.TabControl.TabPages%2A> Proprietà.  
  
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

- [Cenni preliminari sul controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: aggiungere un controllo a un oggetto TabPage](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: disabilitare le schede](how-to-disable-tab-pages.md)
- [Procedura: modificare l'aspetto del controllo TabControl Windows Form](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
