---
title: Associazione di un menu di scelta rapida al componente NotifyIcon
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
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182260"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Procedura: associare un menu di scelta rapida a un componente NotifyIcon di Windows Form
> [!NOTE]
> Anche <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> se e sostituire <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> aggiungere funzionalità <xref:System.Windows.Forms.MainMenu> ai controlli e delle versioni precedenti, e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti sia per la compatibilità con le versioni precedenti e l'uso futuro, se lo si desidera.  
  
 Il <xref:System.Windows.Forms.NotifyIcon> componente visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni. In genere, le applicazioni consentono di fare clic con il pulsante destro del mouse su questa icona per inviare comandi all'applicazione che rappresenta. Associando un <xref:System.Windows.Forms.ContextMenu> componente <xref:System.Windows.Forms.NotifyIcon> al componente, è possibile aggiungere questa funzionalità alle applicazioni.  
  
> [!NOTE]
> Se si desidera che l'applicazione venga ridotta a <xref:System.Windows.Forms.NotifyIcon> icona all'avvio durante la <xref:System.Windows.Forms.Form.WindowState%2A> visualizzazione <xref:System.Windows.Forms.FormWindowState.Minimized> di un'istanza del componente nella barra delle applicazioni, impostare la proprietà del form principale su e assicurarsi che la <xref:System.Windows.Forms.NotifyIcon> proprietà del <xref:System.Windows.Forms.NotifyIcon.Visible%2A> componente sia impostata su . `true`  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Per associare un menu di scelta rapida al componente NotifyIcon in fase di progettazioneTo associate a shortcut menu with the NotifyIcon component at design time  
  
1. Aggiungere <xref:System.Windows.Forms.NotifyIcon> un componente al form e impostare le <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> proprietà importanti, ad esempio le proprietà e .  
  
     Per ulteriori informazioni, vedere [Procedura: aggiungere icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon di Windows Form](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2. Aggiungere <xref:System.Windows.Forms.ContextMenu> un componente al Windows Form.  
  
     Aggiungere voci di menu al menu di scelta rapida che rappresenta i comandi che si desidera rendere disponibili in fase di esecuzione. Questo è anche un buon momento per aggiungere miglioramenti di menu a queste voci di menu, come i tasti di scelta.  
  
3. Impostare <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> la <xref:System.Windows.Forms.NotifyIcon> proprietà del componente sul menu di scelta rapida aggiunto.  
  
     Con questa proprietà impostata, il menu di scelta rapida verrà visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Per associare un menu di scelta rapida al componente NotifyIcon a livello di codiceTo associate a shortcut menu with the NotifyIcon component programmatically  
  
1. Creare un'istanza <xref:System.Windows.Forms.NotifyIcon> della <xref:System.Windows.Forms.ContextMenu> classe e una classe, con le<xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> impostazioni delle <xref:System.Windows.Forms.NotifyIcon> proprietà necessarie per <xref:System.Windows.Forms.ContextMenu> l'applicazione (e le proprietà per il componente, le voci di menu per il componente).  
  
2. Impostare <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> la <xref:System.Windows.Forms.NotifyIcon> proprietà del componente sul menu di scelta rapida aggiunto.  
  
     Con questa proprietà impostata, il menu di scelta rapida verrà visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.  
  
    > [!NOTE]
    > Esempio di codice seguente crea una struttura di menu di base. Sarà necessario personalizzare le scelte di menu per quelle che si adattano all'applicazione che si sta sviluppando. Inoltre, è necessario scrivere codice per <xref:System.Windows.Forms.MenuItem.Click> gestire gli eventi per queste voci di menu.  
  
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
> È necessario `notifyIcon1` `contextMenu1,` inizializzare e che è possibile eseguire includendo le istruzioni seguenti nel costruttore del form:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Procedura: aggiungere icone alla barra delle applicazioni mediante il componente NotifyIcon Windows Form](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Cenni preliminari sul componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
