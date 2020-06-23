---
title: 'Procedura: creare form figlio MDI'
description: Informazioni su come usare Visual Studio per creare un form figlio MDI (Multiple Document Interface) che visualizza un controllo RichTextBox.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 7fe5cde342f0f5ee078f888b7492cd4618bea5c4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903181"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="59561-103">Procedura: creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="59561-103">How to: Create MDI child forms</span></span>

<span data-ttu-id="59561-104">I form figlio MDI sono un elemento essenziale di [applicazioni con interfaccia a documenti multipli (MDI)](multiple-document-interface-mdi-applications.md), in quanto tali forme rappresentano il centro dell'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59561-104">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="59561-105">Nella procedura seguente si userà Visual Studio per creare un form figlio MDI che visualizza un <xref:System.Windows.Forms.RichTextBox> controllo, in modo analogo alla maggior parte delle applicazioni di elaborazione di testi.</span><span class="sxs-lookup"><span data-stu-id="59561-105">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="59561-106">Sostituendo il <xref:System.Windows.Forms> controllo con altri controlli, ad esempio il <xref:System.Windows.Forms.DataGridView> controllo o una combinazione di controlli, è possibile creare finestre figlio MDI (e, per estensione, applicazioni MDI) con diverse possibilità.</span><span class="sxs-lookup"><span data-stu-id="59561-106">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="59561-107">Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="59561-107">Create MDI child forms</span></span>

1. <span data-ttu-id="59561-108">Creare un nuovo progetto di Windows Forms Application in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="59561-108">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="59561-109">Nella finestra **Proprietà** per il form impostare la relativa <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà su `true` e la relativa `WindowsState` proprietà su `Maximized` .</span><span class="sxs-lookup"><span data-stu-id="59561-109">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="59561-110">Il form viene così designato come contenitore MDI per le finestre figlio.</span><span class="sxs-lookup"><span data-stu-id="59561-110">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="59561-111">Dalla `Toolbox` trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form.</span><span class="sxs-lookup"><span data-stu-id="59561-111">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="59561-112">Impostarne la `Text` proprietà su **file**.</span><span class="sxs-lookup"><span data-stu-id="59561-112">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="59561-113">Fare clic sui puntini di sospensione (...) accanto alla proprietà **Items** e fare clic su **Aggiungi** per aggiungere due voci di menu della barra degli strumenti figlio.</span><span class="sxs-lookup"><span data-stu-id="59561-113">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="59561-114">Impostare la `Text` proprietà per questi elementi su **nuovo** e **finestra**.</span><span class="sxs-lookup"><span data-stu-id="59561-114">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="59561-115">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="59561-115">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="59561-116">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Windows Form** (in Visual Basic o in Visual C#) o **Windows Forms applicazione (.NET)** (in Visual C++) dal riquadro **modelli** .</span><span class="sxs-lookup"><span data-stu-id="59561-116">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="59561-117">Nella casella **nome** assegnare al modulo il nome **Form2**.</span><span class="sxs-lookup"><span data-stu-id="59561-117">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="59561-118">Selezionare **Apri** per aggiungere il modulo al progetto.</span><span class="sxs-lookup"><span data-stu-id="59561-118">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59561-119">Il form figlio MDI creato in questo passaggio è un Windows Form standard.</span><span class="sxs-lookup"><span data-stu-id="59561-119">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="59561-120">Dispone pertanto di una proprietà <xref:System.Windows.Forms.Form.Opacity%2A> che consente di controllare la trasparenza del form.</span><span class="sxs-lookup"><span data-stu-id="59561-120">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="59561-121">La proprietà <xref:System.Windows.Forms.Form.Opacity%2A>, tuttavia, è stata progettata per le finestre di primo livello.</span><span class="sxs-lookup"><span data-stu-id="59561-121">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="59561-122">Per evitare problemi di disegno, non usarla con i form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="59561-122">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="59561-123">Il form costituirà il modello per i form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="59561-123">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="59561-124">Viene visualizzata la **Progettazione Windows Form** , che visualizza **Form2**.</span><span class="sxs-lookup"><span data-stu-id="59561-124">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="59561-125">Dalla **casella degli strumenti**trascinare un controllo **RichTextBox** nel form.</span><span class="sxs-lookup"><span data-stu-id="59561-125">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="59561-126">Nella finestra **Proprietà** impostare la `Anchor` proprietà su **Top, Left** e la `Dock` proprietà su **Fill**.</span><span class="sxs-lookup"><span data-stu-id="59561-126">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="59561-127">In questo modo il controllo <xref:System.Windows.Forms.RichTextBox> riempirà completamente l'area del form figlio MDI, anche quando viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="59561-127">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="59561-128">Fare doppio clic sulla **nuova** voce di menu per creare un <xref:System.Windows.Forms.Control.Click> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="59561-128">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="59561-129">Inserire codice simile al seguente per creare un nuovo form figlio MDI quando l'utente fa clic sulla **nuova** voce di menu.</span><span class="sxs-lookup"><span data-stu-id="59561-129">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="59561-130">Nell'esempio che segue il gestore eventi gestisce l'evento <xref:System.Windows.Forms.Control.Click> per `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="59561-130">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="59561-131">Tenere presente che, a seconda delle specifiche dell'architettura dell'applicazione, la **nuova** voce di menu potrebbe non essere `MenuItem2` .</span><span class="sxs-lookup"><span data-stu-id="59561-131">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

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

   <span data-ttu-id="59561-132">In C++ aggiungere la direttiva seguente `#include` all'inizio di Form1. h:</span><span class="sxs-lookup"><span data-stu-id="59561-132">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="59561-133">Nell'elenco a discesa nella parte superiore della finestra **Proprietà** selezionare la striscia di menu che corrisponde alla striscia di menu **file** e impostare la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà sulla finestra <xref:System.Windows.Forms.ToolStripMenuItem> .</span><span class="sxs-lookup"><span data-stu-id="59561-133">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="59561-134">In questo modo il menu **finestra** consente di mantenere un elenco di finestre figlio MDI aperte con un segno di spunta accanto alla finestra figlio attiva.</span><span class="sxs-lookup"><span data-stu-id="59561-134">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="59561-135">Premere **F5** per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59561-135">Press **F5** to run the application.</span></span> <span data-ttu-id="59561-136">Selezionando **nuovo** dal menu **file** è possibile creare nuovi form figlio MDI, che vengono mantenuti traccia di nella voce di menu **finestra** .</span><span class="sxs-lookup"><span data-stu-id="59561-136">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59561-137">Quando un form figlio MDI con un componente <xref:System.Windows.Forms.MainMenu>, associato in genere a una struttura di voci di menu, viene aperto all'interno di un form padre MDI dotato di un componente <xref:System.Windows.Forms.MainMenu>, solitamente con struttura di voci di menu, le voci di menu vengono unite automaticamente se è stata impostata la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> ed eventualmente la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>.</span><span class="sxs-lookup"><span data-stu-id="59561-137">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="59561-138">Impostare la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> sia per i componenti <xref:System.Windows.Forms.MainMenu> che per tutte le voci di menu del form figlio su <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="59561-138">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="59561-139">Impostare anche la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> in modo che le voci di entrambi i menu appaiano nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="59561-139">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="59561-140">Tenere presente inoltre che quando si chiude un form padre MDI, ciascun form figlio MDI genera un evento <xref:System.Windows.Forms.Form.Closing> prima che venga generato l'evento <xref:System.Windows.Forms.Form.Closing> per il padre MDI.</span><span class="sxs-lookup"><span data-stu-id="59561-140">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="59561-141">L'annullamento di un evento <xref:System.Windows.Forms.Form.Closing> di un figlio MDI non impedisce la generazione dell'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI, ma l'argomento <xref:System.ComponentModel.CancelEventArgs> per l'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI verrà ora impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="59561-141">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="59561-142">È possibile imporre la chiusura del form padre MDI e di tutti i form figlio MDI impostando l'argomento <xref:System.ComponentModel.CancelEventArgs> su `false`.</span><span class="sxs-lookup"><span data-stu-id="59561-142">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="59561-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59561-143">See also</span></span>

- [<span data-ttu-id="59561-144">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="59561-144">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="59561-145">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="59561-145">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="59561-146">Procedura: determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="59561-146">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="59561-147">Procedura: inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="59561-147">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="59561-148">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="59561-148">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
