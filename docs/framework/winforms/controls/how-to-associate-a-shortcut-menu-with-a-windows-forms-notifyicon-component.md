---
title: 'Procedura: Associare un menu di scelta rapida a un componente NotifyIcon di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: bf5602d0526fdd97f0cc14382339095a793f13c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922773"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Procedura: Associare un menu di scelta rapida a un componente NotifyIcon di Windows Forms
> [!NOTE]
> Anche <xref:System.Windows.Forms.MenuStrip> se <xref:System.Windows.Forms.ContextMenuStrip> e sostituiscono e aggiungono <xref:System.Windows.Forms.MainMenu> funzionalità <xref:System.Windows.Forms.ContextMenu> ai controlli e delle versioni precedenti <xref:System.Windows.Forms.ContextMenu> e vengono conservati per compatibilità con le versioni precedenti e per un uso futuro, <xref:System.Windows.Forms.MainMenu> se si sceglie.  
  
 Il <xref:System.Windows.Forms.NotifyIcon> componente Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni. In genere, le applicazioni consentono di fare clic con il pulsante destro del mouse su questa icona per inviare comandi all'applicazione che rappresenta. Associando un <xref:System.Windows.Forms.ContextMenu> componente <xref:System.Windows.Forms.NotifyIcon> al componente, è possibile aggiungere questa funzionalità alle applicazioni.  
  
> [!NOTE]
> Se si desidera che l'applicazione venga ridotta a icona all'avvio durante la visualizzazione di un' <xref:System.Windows.Forms.NotifyIcon> istanza del componente nella barra delle applicazioni, impostare la <xref:System.Windows.Forms.Form.WindowState%2A> proprietà del <xref:System.Windows.Forms.FormWindowState.Minimized> form principale su e <xref:System.Windows.Forms.NotifyIcon> assicurarsi che <xref:System.Windows.Forms.NotifyIcon.Visible%2A> la proprietà del componente è impostato su `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Per associare un menu di scelta rapida al componente NotifyIcon in fase di progettazione  
  
1. Aggiungere un <xref:System.Windows.Forms.NotifyIcon> componente al form e impostare le proprietà importanti, ad esempio le <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà e <xref:System.Windows.Forms.NotifyIcon.Visible%2A> .  
  
     Per altre informazioni, vedere [Procedura: Aggiungere le icone dell'applicazione alla barra delle applicazioni con il](app-icons-to-the-taskbar-with-wf-notifyicon.md)componente NotifyIcon Windows Forms.  
  
2. Aggiungere un <xref:System.Windows.Forms.ContextMenu> componente al Windows Form.  
  
     Aggiungere voci di menu al menu di scelta rapida che rappresenta i comandi che si desidera rendere disponibili in fase di esecuzione. Questo è anche il momento opportuno per aggiungere miglioramenti del menu a queste voci di menu, ad esempio le chiavi di accesso.  
  
3. Impostare la <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> proprietà <xref:System.Windows.Forms.NotifyIcon> del componente sul menu di scelta rapida aggiunto.  
  
     Con questa proprietà impostata, il menu di scelta rapida viene visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Per associare un menu di scelta rapida al componente NotifyIcon a livello di codice  
  
1. Creare un' <xref:System.Windows.Forms.NotifyIcon> istanza della classe e una <xref:System.Windows.Forms.ContextMenu> classe, con tutte le impostazioni delle proprietà necessarie per l'applicazione (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> e <xref:System.Windows.Forms.NotifyIcon.Visible%2A> le proprietà per <xref:System.Windows.Forms.NotifyIcon> il componente, le voci di <xref:System.Windows.Forms.ContextMenu> menu per il componente).  
  
2. Impostare la <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> proprietà <xref:System.Windows.Forms.NotifyIcon> del componente sul menu di scelta rapida aggiunto.  
  
     Con questa proprietà impostata, il menu di scelta rapida viene visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.  
  
    > [!NOTE]
    > Nell'esempio di codice seguente viene creata una struttura di menu di base. Sarà necessario personalizzare le scelte di menu per quelle adatte all'applicazione che si sta sviluppando. Inoltre, sarà necessario scrivere il codice per gestire gli <xref:System.Windows.Forms.MenuItem.Click> eventi per queste voci di menu.  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> È necessario `notifyIcon1` inizializzare `contextMenu1,` e, a tale scopo, includere le istruzioni seguenti nel costruttore del modulo:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Procedura: Aggiungere icone dell'applicazione alla barra delle applicazioni con il componente Windows Forms NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Panoramica sul componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
