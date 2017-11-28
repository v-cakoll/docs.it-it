---
title: 'Procedura: inserire un MenuStrip in un menu a discesa MDI (Windows Form)'
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
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2befec35090cf69c6a12cfe24c3512ae9a9b1bfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="a0017-102">Procedura: inserire un MenuStrip in un menu a discesa MDI (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="a0017-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="a0017-103">In alcune applicazioni, il tipo di una finestra figlio di interfaccia a documenti multipli (MDI, Multiple Document Interface) può essere diverso dalla finestra padre MDI.</span><span class="sxs-lookup"><span data-stu-id="a0017-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="a0017-104">Ad esempio, il padre MDI potrebbe essere un foglio di calcolo, mentre il figlio MDI potrebbe essere un grafico.</span><span class="sxs-lookup"><span data-stu-id="a0017-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="a0017-105">In tal caso, è consigliabile aggiornare il contenuto del menu del padre MDI con il contenuto del menu del figlio MDI in quanto vengono attivate finestre figlio MDI di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="a0017-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="a0017-106">La procedura seguente usa il <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> proprietà per inserire un gruppo di voci di menu dal menu del figlio MDI nella parte del menu a discesa del menu del padre MDI.</span><span class="sxs-lookup"><span data-stu-id="a0017-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="a0017-107">Chiudere la finestra figlio MDI rimuove le voci di menu inserite dall'elemento padre MDI.</span><span class="sxs-lookup"><span data-stu-id="a0017-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="a0017-108">Per inserire un MenuStrip in un menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="a0017-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1.  <span data-ttu-id="a0017-109">Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a0017-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="a0017-110">Aggiungere <xref:System.Windows.Forms.MenuStrip> a `Form1` e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> di <xref:System.Windows.Forms.MenuStrip> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a0017-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="a0017-111">Aggiungere una voce di menu di primo livello a `Form1`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.Control.Text%2A> su `&File`.</span><span class="sxs-lookup"><span data-stu-id="a0017-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4.  <span data-ttu-id="a0017-112">Aggiungere tre voci di sottomenu per il `&File` voce di menu e impostare i relativi <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà `&Open`, `&Import from`, e `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="a0017-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5.  <span data-ttu-id="a0017-113">Aggiungere due voci di sottomenu per il `&Import from` voce di sottomenu e impostare i relativi <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà `&Word` e `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="a0017-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6.  <span data-ttu-id="a0017-114">Aggiungere un form al progetto, aggiungere <xref:System.Windows.Forms.MenuStrip> al form e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> del `Form2`<xref:System.Windows.Forms.MenuStrip> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a0017-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="a0017-115">Aggiungere una voce di menu di primo livello a `Form2`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&File`.</span><span class="sxs-lookup"><span data-stu-id="a0017-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8.  <span data-ttu-id="a0017-116">Aggiungere le voci di sottomenu per il `&File` dal menu di `Form2` nell'ordine seguente: un <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close``and Save`e un altro <xref:System.Windows.Forms.ToolStripSeparator>.</span><span class="sxs-lookup"><span data-stu-id="a0017-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close``and Save`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="a0017-117">Impostare il <xref:System.Windows.Forms.MergeAction> e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> le proprietà del `Form2` voci di menu, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a0017-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a0017-118">Voce di menu Form2</span><span class="sxs-lookup"><span data-stu-id="a0017-118">Form2 menu item</span></span>|<span data-ttu-id="a0017-119">Valore di MergeAction</span><span class="sxs-lookup"><span data-stu-id="a0017-119">MergeAction value</span></span>|<span data-ttu-id="a0017-120">Valore di MergeIndex</span><span class="sxs-lookup"><span data-stu-id="a0017-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="a0017-121">File</span><span class="sxs-lookup"><span data-stu-id="a0017-121">File</span></span>|<span data-ttu-id="a0017-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="a0017-122">MatchOnly</span></span>|<span data-ttu-id="a0017-123">-1</span><span class="sxs-lookup"><span data-stu-id="a0017-123">-1</span></span>|  
    |<span data-ttu-id="a0017-124">Separatore</span><span class="sxs-lookup"><span data-stu-id="a0017-124">Separator</span></span>|<span data-ttu-id="a0017-125">INS</span><span class="sxs-lookup"><span data-stu-id="a0017-125">Insert</span></span>|<span data-ttu-id="a0017-126">2</span><span class="sxs-lookup"><span data-stu-id="a0017-126">2</span></span>|  
    |<span data-ttu-id="a0017-127">Salva</span><span class="sxs-lookup"><span data-stu-id="a0017-127">Save</span></span>|<span data-ttu-id="a0017-128">INS</span><span class="sxs-lookup"><span data-stu-id="a0017-128">Insert</span></span>|<span data-ttu-id="a0017-129">3</span><span class="sxs-lookup"><span data-stu-id="a0017-129">3</span></span>|  
    |<span data-ttu-id="a0017-130">Salva e chiudi</span><span class="sxs-lookup"><span data-stu-id="a0017-130">Save and Close</span></span>|<span data-ttu-id="a0017-131">INS</span><span class="sxs-lookup"><span data-stu-id="a0017-131">Insert</span></span>|<span data-ttu-id="a0017-132">4</span><span class="sxs-lookup"><span data-stu-id="a0017-132">4</span></span>|  
    |<span data-ttu-id="a0017-133">Separatore</span><span class="sxs-lookup"><span data-stu-id="a0017-133">Separator</span></span>|<span data-ttu-id="a0017-134">INS</span><span class="sxs-lookup"><span data-stu-id="a0017-134">Insert</span></span>|<span data-ttu-id="a0017-135">5</span><span class="sxs-lookup"><span data-stu-id="a0017-135">5</span></span>|  
  
10. <span data-ttu-id="a0017-136">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="a0017-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="a0017-137">Nel gestore eventi inserire codice simile all'esempio di codice riportato di seguito per creare e visualizzare nuove istanze di `Form2` come finestre figlio MDI di `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a0017-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="a0017-138">Inserire codice analogo al seguente esempio di codice nel `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a0017-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0017-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a0017-139">Compiling the Code</span></span>  
 <span data-ttu-id="a0017-140">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0017-140">This example requires:</span></span>  
  
-   <span data-ttu-id="a0017-141">Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.</span><span class="sxs-lookup"><span data-stu-id="a0017-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="a0017-142">Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="a0017-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="a0017-143">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a0017-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0017-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0017-144">See Also</span></span>  
 [<span data-ttu-id="a0017-145">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="a0017-145">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="a0017-146">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="a0017-146">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="a0017-147">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="a0017-147">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
