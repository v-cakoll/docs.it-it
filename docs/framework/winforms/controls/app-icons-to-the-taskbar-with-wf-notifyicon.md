---
title: "Procedura: Aggiungere le icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon di Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 04f6b98a2206371a2838b3a6952feeafcd788309
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714255"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="49eb7-102">Procedura: Aggiungere le icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon di Windows Form</span><span class="sxs-lookup"><span data-stu-id="49eb7-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="49eb7-103">I moduli di Windows <xref:System.Windows.Forms.NotifyIcon> componente consente di visualizzare una singola icona nell'area di notifica dello stato della barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="49eb7-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="49eb7-104">Per visualizzare le icone più nell'area di stato, è necessario disporre di più <xref:System.Windows.Forms.NotifyIcon> componenti nel form.</span><span class="sxs-lookup"><span data-stu-id="49eb7-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="49eb7-105">Per impostare l'icona visualizzata per un controllo, usare il <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="49eb7-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="49eb7-106">È anche possibile scrivere codice <xref:System.Windows.Forms.NotifyIcon.DoubleClick> gestore dell'evento in modo che si verifica un evento quando l'utente fa doppio clic sull'icona.</span><span class="sxs-lookup"><span data-stu-id="49eb7-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="49eb7-107">Ad esempio, si è stato possibile visualizzare una finestra di dialogo per l'utente debba configurare il processo in background rappresentato dall'icona.</span><span class="sxs-lookup"><span data-stu-id="49eb7-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49eb7-108">Il <xref:System.Windows.Forms.NotifyIcon> componente viene usato solo a fini di notifica per avvertire gli utenti che si è verificato un evento o azione o si è verificato un cambiamento dello stato di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="49eb7-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="49eb7-109">Utilizzare i menu, barre degli strumenti e altri elementi dell'interfaccia utente per l'interazione standard con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="49eb7-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="49eb7-110">Per impostare l'icona</span><span class="sxs-lookup"><span data-stu-id="49eb7-110">To set the icon</span></span>  
  
1.  <span data-ttu-id="49eb7-111">Assegnare un valore per il <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="49eb7-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="49eb7-112">Il valore deve essere di tipo `System.Drawing.Icon` e possono essere caricati da un file con estensione ico.</span><span class="sxs-lookup"><span data-stu-id="49eb7-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="49eb7-113">È possibile specificare il file dell'icona nel codice o facendo clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà nel  **Le proprietà** finestra e quindi selezionare il file nei **Open** finestra di dialogo visualizzata.</span><span class="sxs-lookup"><span data-stu-id="49eb7-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2.  <span data-ttu-id="49eb7-114">Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="49eb7-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="49eb7-115">Impostare il <xref:System.Windows.Forms.NotifyIcon.Text%2A> proprietà da una stringa di descrizione appropriata.</span><span class="sxs-lookup"><span data-stu-id="49eb7-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="49eb7-116">Nell'esempio di codice seguente, il percorso impostato per il percorso dell'icona è il **documenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="49eb7-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="49eb7-117">Poiché si può presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella, viene usato questo percorso.</span><span class="sxs-lookup"><span data-stu-id="49eb7-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="49eb7-118">Anche questa scelta consente agli utenti con livelli di accesso di sistema minimi eseguire in modo sicuro l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="49eb7-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="49eb7-119">Nell'esempio seguente richiede un modulo con un <xref:System.Windows.Forms.NotifyIcon> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="49eb7-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="49eb7-120">È inoltre necessario un file di icona denominato `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="49eb7-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="49eb7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49eb7-121">See also</span></span>
- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="49eb7-122">Procedura: Associare un Menu di scelta rapida a un componente NotifyIcon di Windows Form</span><span class="sxs-lookup"><span data-stu-id="49eb7-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="49eb7-123">Componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="49eb7-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="49eb7-124">Panoramica sul componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="49eb7-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
