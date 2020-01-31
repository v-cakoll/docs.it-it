---
title: Associare un menu di scelta rapida al componente NotifyIcon
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
ms.openlocfilehash: 392c04f73feaec201033ad76f9419a0e070bec70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742054"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Procedura: associare un menu di scelta rapida a un componente NotifyIcon di Windows Form
> [!NOTE]
> Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si desidera.  
  
 Il componente <xref:System.Windows.Forms.NotifyIcon> Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni. In genere, le applicazioni consentono di fare clic con il pulsante destro del mouse su questa icona per inviare comandi all'applicazione che rappresenta. Associando un componente <xref:System.Windows.Forms.ContextMenu> al componente <xref:System.Windows.Forms.NotifyIcon>, è possibile aggiungere questa funzionalità alle applicazioni.  
  
> [!NOTE]
> Se si desidera che l'applicazione venga ridotta a icona all'avvio durante la visualizzazione di un'istanza del componente <xref:System.Windows.Forms.NotifyIcon> nella barra delle applicazioni, impostare la proprietà <xref:System.Windows.Forms.Form.WindowState%2A> del form principale su <xref:System.Windows.Forms.FormWindowState.Minimized> e verificare che la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> del componente <xref:System.Windows.Forms.NotifyIcon> sia impostata su `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Per associare un menu di scelta rapida al componente NotifyIcon in fase di progettazione  
  
1. Aggiungere un componente <xref:System.Windows.Forms.NotifyIcon> al form e impostare le proprietà importanti, ad esempio le proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A> e <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  
  
     Per ulteriori informazioni, vedere [procedura: aggiungere icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2. Aggiungere un componente <xref:System.Windows.Forms.ContextMenu> al Windows Form.  
  
     Aggiungere voci di menu al menu di scelta rapida che rappresenta i comandi che si desidera rendere disponibili in fase di esecuzione. Questo è anche il momento opportuno per aggiungere miglioramenti del menu a queste voci di menu, ad esempio le chiavi di accesso.  
  
3. Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del componente <xref:System.Windows.Forms.NotifyIcon> sul menu di scelta rapida aggiunto.  
  
     Con questa proprietà impostata, il menu di scelta rapida viene visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Per associare un menu di scelta rapida al componente NotifyIcon a livello di codice  
  
1. Creare un'istanza della classe <xref:System.Windows.Forms.NotifyIcon> e una classe <xref:System.Windows.Forms.ContextMenu>, con le impostazioni delle proprietà necessarie per l'applicazione (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> e le proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> per il componente <xref:System.Windows.Forms.NotifyIcon>, le voci di menu per il componente <xref:System.Windows.Forms.ContextMenu>).  
  
2. Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del componente <xref:System.Windows.Forms.NotifyIcon> sul menu di scelta rapida aggiunto.  
  
     Con questa proprietà impostata, il menu di scelta rapida viene visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.  
  
    > [!NOTE]
    > Nell'esempio di codice seguente viene creata una struttura di menu di base. Sarà necessario personalizzare le scelte di menu per quelle adatte all'applicazione che si sta sviluppando. Inoltre, sarà necessario scrivere il codice per gestire gli eventi <xref:System.Windows.Forms.MenuItem.Click> per queste voci di menu.  
  
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
> È necessario inizializzare `notifyIcon1` e `contextMenu1,` che è possibile eseguire includendo le istruzioni seguenti nel costruttore del modulo:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Procedura: Aggiungere icone alla barra delle applicazioni con il componente NotifyIcon di Windows Form](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Panoramica sul componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
