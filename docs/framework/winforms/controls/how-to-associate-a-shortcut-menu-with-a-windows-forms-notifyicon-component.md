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
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="15b66-102">Procedura: associare un menu di scelta rapida a un componente NotifyIcon di Windows Form</span><span class="sxs-lookup"><span data-stu-id="15b66-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="15b66-103">Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="15b66-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="15b66-104">Il componente <xref:System.Windows.Forms.NotifyIcon> Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="15b66-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="15b66-105">In genere, le applicazioni consentono di fare clic con il pulsante destro del mouse su questa icona per inviare comandi all'applicazione che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="15b66-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="15b66-106">Associando un componente <xref:System.Windows.Forms.ContextMenu> al componente <xref:System.Windows.Forms.NotifyIcon>, è possibile aggiungere questa funzionalità alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="15b66-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15b66-107">Se si desidera che l'applicazione venga ridotta a icona all'avvio durante la visualizzazione di un'istanza del componente <xref:System.Windows.Forms.NotifyIcon> nella barra delle applicazioni, impostare la proprietà <xref:System.Windows.Forms.Form.WindowState%2A> del form principale su <xref:System.Windows.Forms.FormWindowState.Minimized> e verificare che la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> del componente <xref:System.Windows.Forms.NotifyIcon> sia impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="15b66-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="15b66-108">Per associare un menu di scelta rapida al componente NotifyIcon in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="15b66-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="15b66-109">Aggiungere un componente <xref:System.Windows.Forms.NotifyIcon> al form e impostare le proprietà importanti, ad esempio le proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A> e <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="15b66-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="15b66-110">Per ulteriori informazioni, vedere [procedura: aggiungere icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="15b66-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="15b66-111">Aggiungere un componente <xref:System.Windows.Forms.ContextMenu> al Windows Form.</span><span class="sxs-lookup"><span data-stu-id="15b66-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="15b66-112">Aggiungere voci di menu al menu di scelta rapida che rappresenta i comandi che si desidera rendere disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="15b66-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="15b66-113">Questo è anche il momento opportuno per aggiungere miglioramenti del menu a queste voci di menu, ad esempio le chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="15b66-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="15b66-114">Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del componente <xref:System.Windows.Forms.NotifyIcon> sul menu di scelta rapida aggiunto.</span><span class="sxs-lookup"><span data-stu-id="15b66-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="15b66-115">Con questa proprietà impostata, il menu di scelta rapida viene visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="15b66-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="15b66-116">Per associare un menu di scelta rapida al componente NotifyIcon a livello di codice</span><span class="sxs-lookup"><span data-stu-id="15b66-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="15b66-117">Creare un'istanza della classe <xref:System.Windows.Forms.NotifyIcon> e una classe <xref:System.Windows.Forms.ContextMenu>, con le impostazioni delle proprietà necessarie per l'applicazione (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> e le proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> per il componente <xref:System.Windows.Forms.NotifyIcon>, le voci di menu per il componente <xref:System.Windows.Forms.ContextMenu>).</span><span class="sxs-lookup"><span data-stu-id="15b66-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="15b66-118">Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del componente <xref:System.Windows.Forms.NotifyIcon> sul menu di scelta rapida aggiunto.</span><span class="sxs-lookup"><span data-stu-id="15b66-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="15b66-119">Con questa proprietà impostata, il menu di scelta rapida viene visualizzato quando si fa clic sull'icona sulla barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="15b66-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="15b66-120">Nell'esempio di codice seguente viene creata una struttura di menu di base.</span><span class="sxs-lookup"><span data-stu-id="15b66-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="15b66-121">Sarà necessario personalizzare le scelte di menu per quelle adatte all'applicazione che si sta sviluppando.</span><span class="sxs-lookup"><span data-stu-id="15b66-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="15b66-122">Inoltre, sarà necessario scrivere il codice per gestire gli eventi <xref:System.Windows.Forms.MenuItem.Click> per queste voci di menu.</span><span class="sxs-lookup"><span data-stu-id="15b66-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
> <span data-ttu-id="15b66-123">È necessario inizializzare `notifyIcon1` e `contextMenu1,` che è possibile eseguire includendo le istruzioni seguenti nel costruttore del modulo:</span><span class="sxs-lookup"><span data-stu-id="15b66-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="15b66-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15b66-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="15b66-125">Procedura: Aggiungere icone alla barra delle applicazioni con il componente NotifyIcon di Windows Form</span><span class="sxs-lookup"><span data-stu-id="15b66-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="15b66-126">Componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="15b66-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="15b66-127">Panoramica sul componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="15b66-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
