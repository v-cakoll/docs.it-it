---
title: 'Procedura: creare form figlio MDI'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2bbbe8dbbfa6b2aebd3834314f0f56b7c7643c21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="f05eb-102">Procedura: creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f05eb-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="f05eb-103">Form figlio MDI sono un elemento fondamentale di [Multiple-Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), come questi moduli sono il fulcro dell'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f05eb-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="f05eb-104">Nella procedura che segue vengono creati form figlio MDI che visualizzano un controllo <xref:System.Windows.Forms.RichTextBox>, analogo alla maggior parte delle applicazioni per l'elaborazione di testi.</span><span class="sxs-lookup"><span data-stu-id="f05eb-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="f05eb-105">Sostituendo il controllo <xref:System.Windows.Forms> con altri controlli, ad esempio con <xref:System.Windows.Forms.DataGridView> o con più controlli, è possibile creare finestre figlio MDI e applicazioni MDI con differenti possibilità.</span><span class="sxs-lookup"><span data-stu-id="f05eb-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f05eb-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f05eb-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f05eb-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f05eb-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f05eb-108">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f05eb-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="f05eb-109">Per creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f05eb-109">To create MDI child forms</span></span>  
  
1.  <span data-ttu-id="f05eb-110">Creare un nuovo progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f05eb-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="f05eb-111">In **finestre delle proprietà** per il form, impostare il relativo <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà `true`e il relativo `WindowsState` proprietà `Maximized`.</span><span class="sxs-lookup"><span data-stu-id="f05eb-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="f05eb-112">Il form viene così designato come contenitore MDI per le finestre figlio.</span><span class="sxs-lookup"><span data-stu-id="f05eb-112">This designates the form as an MDI container for child windows.</span></span>  
  
2.  <span data-ttu-id="f05eb-113">Dalla `Toolbox` trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form.</span><span class="sxs-lookup"><span data-stu-id="f05eb-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="f05eb-114">Impostare il relativo `Text` proprietà **File**.</span><span class="sxs-lookup"><span data-stu-id="f05eb-114">Set its `Text` property to **File**.</span></span>  
  
3.  <span data-ttu-id="f05eb-115">Fare clic sui puntini di sospensione (...) accanto al **elementi** , proprietà e fare clic su **Aggiungi** per aggiungere due figlio voci di menu ToolStrip.</span><span class="sxs-lookup"><span data-stu-id="f05eb-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="f05eb-116">Impostare il `Text` proprietà di questi elementi su **New** e **finestra**.</span><span class="sxs-lookup"><span data-stu-id="f05eb-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4.  <span data-ttu-id="f05eb-117">In **Esplora**, fare clic sul progetto, scegliere **Aggiungi**, quindi selezionare **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f05eb-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5.  <span data-ttu-id="f05eb-118">Nel **Aggiungi nuovo elemento** nella finestra di dialogo **Windows Form** (in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) o **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) dal **modelli** riquadro.</span><span class="sxs-lookup"><span data-stu-id="f05eb-118">In the **Add New Item** dialog box, select **Windows Form** (in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="f05eb-119">Nel **nome** casella, come nome del form **Form2**.</span><span class="sxs-lookup"><span data-stu-id="f05eb-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="f05eb-120">Fare clic su di **aprire** pulsante per aggiungere il form al progetto.</span><span class="sxs-lookup"><span data-stu-id="f05eb-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f05eb-121">Il form figlio MDI creato in questo passaggio è un Windows Form standard.</span><span class="sxs-lookup"><span data-stu-id="f05eb-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="f05eb-122">Dispone pertanto di una proprietà <xref:System.Windows.Forms.Form.Opacity%2A> che consente di controllare la trasparenza del form.</span><span class="sxs-lookup"><span data-stu-id="f05eb-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="f05eb-123">La proprietà <xref:System.Windows.Forms.Form.Opacity%2A>, tuttavia, è stata progettata per le finestre di primo livello.</span><span class="sxs-lookup"><span data-stu-id="f05eb-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="f05eb-124">Per evitare problemi di disegno, non usarla con i form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="f05eb-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="f05eb-125">Il form costituirà il modello per i form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="f05eb-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="f05eb-126">Il **Progettazione Windows Form** visualizzata **Form2**.</span><span class="sxs-lookup"><span data-stu-id="f05eb-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6.  <span data-ttu-id="f05eb-127">Dal **della casella degli strumenti**, trascinare un **RichTextBox** al form.</span><span class="sxs-lookup"><span data-stu-id="f05eb-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7.  <span data-ttu-id="f05eb-128">Nel **proprietà** finestra, impostare il `Anchor` proprietà **superiore sinistra** e `Dock` proprietà **riempimento**.</span><span class="sxs-lookup"><span data-stu-id="f05eb-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="f05eb-129">In questo modo il controllo <xref:System.Windows.Forms.RichTextBox> riempirà completamente l'area del form figlio MDI, anche quando viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="f05eb-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8.  <span data-ttu-id="f05eb-130">Fare doppio clic il **New** voce di menu per creare un <xref:System.Windows.Forms.Control.Click> relativo gestore di evento.</span><span class="sxs-lookup"><span data-stu-id="f05eb-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="f05eb-131">Inserire codice simile al seguente per creare un nuovo form figlio MDI quando l'utente sceglie il **New** voce di menu.</span><span class="sxs-lookup"><span data-stu-id="f05eb-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f05eb-132">Nell'esempio che segue il gestore eventi gestisce l'evento <xref:System.Windows.Forms.Control.Click> per `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="f05eb-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="f05eb-133">Tenere presente che, a seconda delle specifiche di architettura dell'applicazione, il **New** voce di menu non siano `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="f05eb-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     <span data-ttu-id="f05eb-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] aggiungere la direttiva `#include` seguente all'inizio di Form1.h:</span><span class="sxs-lookup"><span data-stu-id="f05eb-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="f05eb-135">Nell'elenco all'inizio dell'elenco a discesa di **proprietà** finestra, selezionare il controllo MenuStrip che corrisponde alla **File** e impostare il <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà nella finestra <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="f05eb-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="f05eb-136">In questo modo il **finestra** menu per gestire un elenco di finestre figlio MDI aperte con un segno di spunta accanto alla finestra figlio attiva.</span><span class="sxs-lookup"><span data-stu-id="f05eb-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="f05eb-137">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f05eb-137">Press F5 to run the application.</span></span> <span data-ttu-id="f05eb-138">Selezionando **New** dal **File** menu, è possibile creare nuovi form figlio MDI di cui viene tenuta traccia nel **finestra** voce di menu.</span><span class="sxs-lookup"><span data-stu-id="f05eb-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f05eb-139">Quando un form figlio MDI con un componente <xref:System.Windows.Forms.MainMenu>, associato in genere a una struttura di voci di menu, viene aperto all'interno di un form padre MDI dotato di un componente <xref:System.Windows.Forms.MainMenu>, solitamente con struttura di voci di menu, le voci di menu vengono unite automaticamente se è stata impostata la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> ed eventualmente la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>.</span><span class="sxs-lookup"><span data-stu-id="f05eb-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="f05eb-140">Impostare la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> sia per i componenti <xref:System.Windows.Forms.MainMenu> che per tutte le voci di menu del form figlio su <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="f05eb-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="f05eb-141">Impostare anche la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> in modo che le voci di entrambi i menu appaiano nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="f05eb-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="f05eb-142">Tenere presente inoltre che quando si chiude un form padre MDI, ciascun form figlio MDI genera un evento <xref:System.Windows.Forms.Form.Closing> prima che venga generato l'evento <xref:System.Windows.Forms.Form.Closing> per il padre MDI.</span><span class="sxs-lookup"><span data-stu-id="f05eb-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="f05eb-143">L'annullamento di un evento <xref:System.Windows.Forms.Form.Closing> di un figlio MDI non impedisce la generazione dell'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI, ma l'argomento <xref:System.ComponentModel.CancelEventArgs> per l'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI verrà ora impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="f05eb-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="f05eb-144">È possibile imporre la chiusura del form padre MDI e di tutti i form figlio MDI impostando l'argomento <xref:System.ComponentModel.CancelEventArgs> su `false`.</span><span class="sxs-lookup"><span data-stu-id="f05eb-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05eb-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f05eb-145">See Also</span></span>  
 [<span data-ttu-id="f05eb-146">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="f05eb-146">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="f05eb-147">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="f05eb-147">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="f05eb-148">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="f05eb-148">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="f05eb-149">Procedura: Inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="f05eb-149">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="f05eb-150">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f05eb-150">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
