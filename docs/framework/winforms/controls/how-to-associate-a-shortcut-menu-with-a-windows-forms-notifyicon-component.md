---
title: 'Procedura: Associare un Menu di scelta rapida a un componente NotifyIcon di Windows Form'
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
ms.openlocfilehash: e9e50aee63ec36ac005daabed27c3ac3c42a4dc9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720384"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Procedura: Associare un Menu di scelta rapida a un componente NotifyIcon di Windows Form
> [!NOTE]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere la funzionalità per il <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.  
  
 Il <xref:System.Windows.Forms.NotifyIcon> componente viene visualizzata un'icona nell'area di notifica dello stato della barra delle applicazioni. In genere, le applicazioni consentono di fare doppio clic su questa icona per l'invio di comandi per l'applicazione da essa rappresentata. Associando un <xref:System.Windows.Forms.ContextMenu> componente con il <xref:System.Windows.Forms.NotifyIcon> componente, è possibile aggiungere questa funzionalità alle applicazioni.  
  
> [!NOTE]
>  Se si vuole che l'applicazione da ridurre al minimo all'avvio durante la visualizzazione di un'istanza del <xref:System.Windows.Forms.NotifyIcon> componente nella barra degli strumenti, impostare il form principale <xref:System.Windows.Forms.Form.WindowState%2A> proprietà <xref:System.Windows.Forms.FormWindowState.Minimized> e assicurarsi che il <xref:System.Windows.Forms.NotifyIcon> componente <xref:System.Windows.Forms.NotifyIcon.Visible%2A> proprietà è impostato su `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Per associare un menu di scelta rapida con il componente NotifyIcon in fase di progettazione  
  
1.  Aggiungere un <xref:System.Windows.Forms.NotifyIcon> al form e impostare le proprietà importanti, ad esempio il <xref:System.Windows.Forms.NotifyIcon.Icon%2A> e <xref:System.Windows.Forms.NotifyIcon.Visible%2A> proprietà.  
  
     Per altre informazioni, vedere [Procedura: Aggiungere le icone dell'applicazione alla barra delle applicazioni con il Windows Form sul componente NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Aggiungere un <xref:System.Windows.Forms.ContextMenu> al Windows Form.  
  
     Aggiungere le voci di menu al menu di scelta rapida che rappresentano i comandi che si desidera rendere disponibili in fase di esecuzione. Questo è il momento giusto per aggiungere i miglioramenti di menu per queste voci di menu, ad esempio le chiavi di accesso.  
  
3.  Impostare il <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> proprietà del <xref:System.Windows.Forms.NotifyIcon> componente al menu di scelta rapida che è stato aggiunto.  
  
     Con questa proprietà è impostata, verrà visualizzato il menu di scelta rapida quando si fa clic sull'icona della barra delle applicazioni.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Per associare un menu di scelta rapida con il componente NotifyIcon a livello di codice  
  
1.  Creare un'istanza del <xref:System.Windows.Forms.NotifyIcon> classe e un <xref:System.Windows.Forms.ContextMenu> (classe), con qualsiasi impostazione di proprietà sono necessarie per l'applicazione (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> e <xref:System.Windows.Forms.NotifyIcon.Visible%2A> le proprietà per il <xref:System.Windows.Forms.NotifyIcon> componente, voci di menu per il <xref:System.Windows.Forms.ContextMenu> componente).  
  
2.  Impostare il <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> proprietà del <xref:System.Windows.Forms.NotifyIcon> componente al menu di scelta rapida che è stato aggiunto.  
  
     Con questa proprietà è impostata, verrà visualizzato il menu di scelta rapida quando si fa clic sull'icona della barra delle applicazioni.  
  
    > [!NOTE]
    >  Esempio di codice seguente crea una struttura menu di base. È necessario personalizzare le opzioni di menu a quelle che rientrano l'applicazione che si sta sviluppando. Inoltre, è opportuno scrivere codice per gestire il <xref:System.Windows.Forms.MenuItem.Click> gli eventi per queste voci di menu.  
  
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
>  È necessario inizializzare `notifyIcon1` e `contextMenu1,` a questo scopo, includendo le istruzioni seguenti nel costruttore del form:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Procedura: Aggiungere le icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon di Windows Form](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Panoramica sul componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
