---
title: Aggiungere icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon
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
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746243"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="3b643-102">Procedura: aggiungere icone alla barra delle applicazioni mediante il componente NotifyIcon Windows Form</span><span class="sxs-lookup"><span data-stu-id="3b643-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>

<span data-ttu-id="3b643-103">Il componente Windows Forms <xref:System.Windows.Forms.NotifyIcon> Visualizza una singola icona nell'area di notifica dello stato della barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3b643-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="3b643-104">Per visualizzare più icone nell'area stato, è necessario che nel form siano presenti più componenti <xref:System.Windows.Forms.NotifyIcon>.</span><span class="sxs-lookup"><span data-stu-id="3b643-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="3b643-105">Per impostare l'icona visualizzata per un controllo, utilizzare la proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b643-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="3b643-106">È anche possibile scrivere codice nel gestore dell'evento <xref:System.Windows.Forms.NotifyIcon.DoubleClick> in modo che ciò accada quando l'utente fa doppio clic sull'icona.</span><span class="sxs-lookup"><span data-stu-id="3b643-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="3b643-107">È ad esempio possibile fare in modo che venga visualizzata una finestra di dialogo in cui l'utente può configurare il processo in background rappresentato dall'icona.</span><span class="sxs-lookup"><span data-stu-id="3b643-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>

> [!NOTE]
> <span data-ttu-id="3b643-108">Il componente <xref:System.Windows.Forms.NotifyIcon> viene utilizzato solo a scopo di notifica, per segnalare agli utenti che si è verificata un'azione o un evento o che è stata apportata una modifica allo stato di un determinato ordinamento.</span><span class="sxs-lookup"><span data-stu-id="3b643-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="3b643-109">È consigliabile utilizzare i menu, le barre degli strumenti e altri elementi dell'interfaccia utente per l'interazione standard con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3b643-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>

### <a name="to-set-the-icon"></a><span data-ttu-id="3b643-110">Per impostare l'icona</span><span class="sxs-lookup"><span data-stu-id="3b643-110">To set the icon</span></span>

1. <span data-ttu-id="3b643-111">Assegnare un valore alla proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b643-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="3b643-112">Il valore deve essere di tipo `System.Drawing.Icon` e può essere caricato da un file con estensione ico.</span><span class="sxs-lookup"><span data-stu-id="3b643-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="3b643-113">È possibile specificare il file icona nel codice o facendo clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A> nella finestra **Proprietà** e quindi selezionando il file nella finestra di dialogo **Apri** visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3b643-113">You can specify the icon file in code or by clicking the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>

2. <span data-ttu-id="3b643-114">Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="3b643-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>

3. <span data-ttu-id="3b643-115">Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Text%2A> su una stringa di descrizione comando appropriata.</span><span class="sxs-lookup"><span data-stu-id="3b643-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>

     <span data-ttu-id="3b643-116">Nell'esempio di codice seguente il percorso impostato per la posizione dell'icona è la cartella **documenti** .</span><span class="sxs-lookup"><span data-stu-id="3b643-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="3b643-117">Questo percorso viene usato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella.</span><span class="sxs-lookup"><span data-stu-id="3b643-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="3b643-118">La scelta di questa località consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="3b643-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="3b643-119">L'esempio seguente richiede un modulo con un controllo <xref:System.Windows.Forms.NotifyIcon> già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="3b643-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="3b643-120">Richiede anche un file di icona denominato `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="3b643-120">It also requires an icon file named `Icon.ico`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3b643-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b643-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="3b643-122">Procedura: Associare un menu di scelta rapida a un componente NotifyIcon di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3b643-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="3b643-123">Componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="3b643-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="3b643-124">Panoramica sul componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="3b643-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
