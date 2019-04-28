---
title: 'Procedura: Rimuovere un ToolStripMenuItem da un Menu a discesa MDI (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 7c84d260783e3a511b5ef6a651c71f1ee55acffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913159"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="f5b43-102">Procedura: Rimuovere un ToolStripMenuItem da un Menu a discesa MDI (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="f5b43-102">How to: Remove a ToolStripMenuItem from an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="f5b43-103">In alcune applicazioni, il tipo di una finestra figlio di interfaccia a documenti multipli (MDI, Multiple Document Interface) può essere diverso dalla finestra padre MDI.</span><span class="sxs-lookup"><span data-stu-id="f5b43-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="f5b43-104">Ad esempio, il padre MDI potrebbe essere un foglio di calcolo, mentre il figlio MDI potrebbe essere un grafico.</span><span class="sxs-lookup"><span data-stu-id="f5b43-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="f5b43-105">In tal caso, è consigliabile aggiornare il contenuto del menu del padre MDI con il contenuto del menu del figlio MDI in quanto vengono attivate finestre figlio MDI di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="f5b43-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="f5b43-106">La procedura seguente usa il <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> proprietà per rimuovere una voce di menu dalla parte a discesa del menu del padre MDI.</span><span class="sxs-lookup"><span data-stu-id="f5b43-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to remove a menu item from the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="f5b43-107">Chiudere la finestra figlio MDI Ripristina le voci di menu rimosso al menu del padre MDI.</span><span class="sxs-lookup"><span data-stu-id="f5b43-107">Closing the MDI child window restores the removed menu items to the MDI parent menu.</span></span>  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a><span data-ttu-id="f5b43-108">Per rimuovere un controllo MenuStrip da un menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="f5b43-108">To remove a MenuStrip from an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="f5b43-109">Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="f5b43-110">Aggiungere <xref:System.Windows.Forms.MenuStrip> a `Form1` e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> di <xref:System.Windows.Forms.MenuStrip> su `true`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="f5b43-111">Aggiungere una voce di menu di primo livello a `Form1`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.Control.Text%2A> su `&File`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="f5b43-112">Aggiungere tre voci di sottomenu per il `&File` voce di menu e set loro <xref:System.Windows.Forms.ToolStripItem.Text%2A> delle proprietà per `&Open`, `&Import from`, e `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="f5b43-113">Aggiungere due voci di sottomenu per il `&Import from` voce di sottomenu e set loro <xref:System.Windows.Forms.ToolStripItem.Text%2A> delle proprietà per `&Word` e `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="f5b43-114">Aggiungere un form al progetto, aggiungere <xref:System.Windows.Forms.MenuStrip> al form e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> del `Form2`<xref:System.Windows.Forms.MenuStrip> su `true`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="f5b43-115">Aggiungere una voce di menu di primo livello a `Form2`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&File`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="f5b43-116">Aggiungere un `&Import from` voce di sottomenu per il `&File` dal menu di `Form2`e aggiungere un `&Word` voce di sottomenu per il `&File` menu.</span><span class="sxs-lookup"><span data-stu-id="f5b43-116">Add an `&Import from` submenu item to the `&File` menu of `Form2`, and add an `&Word` submenu item to the `&File` menu.</span></span>  
  
9. <span data-ttu-id="f5b43-117">Impostare il <xref:System.Windows.Forms.MergeAction> e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> delle proprietà del `Form2` voci di menu, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f5b43-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="f5b43-118">Voce di menu Form2</span><span class="sxs-lookup"><span data-stu-id="f5b43-118">Form2 menu item</span></span>|<span data-ttu-id="f5b43-119">Valore MergeAction</span><span class="sxs-lookup"><span data-stu-id="f5b43-119">MergeAction value</span></span>|<span data-ttu-id="f5b43-120">Valore MergeIndex</span><span class="sxs-lookup"><span data-stu-id="f5b43-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="f5b43-121">File</span><span class="sxs-lookup"><span data-stu-id="f5b43-121">File</span></span>|<span data-ttu-id="f5b43-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="f5b43-122">MatchOnly</span></span>|<span data-ttu-id="f5b43-123">-1</span><span class="sxs-lookup"><span data-stu-id="f5b43-123">-1</span></span>|  
    |<span data-ttu-id="f5b43-124">Importare da</span><span class="sxs-lookup"><span data-stu-id="f5b43-124">Import from</span></span>|<span data-ttu-id="f5b43-125">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="f5b43-125">MatchOnly</span></span>|<span data-ttu-id="f5b43-126">-1</span><span class="sxs-lookup"><span data-stu-id="f5b43-126">-1</span></span>|  
    |<span data-ttu-id="f5b43-127">Word</span><span class="sxs-lookup"><span data-stu-id="f5b43-127">Word</span></span>|<span data-ttu-id="f5b43-128">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="f5b43-128">Remove</span></span>|<span data-ttu-id="f5b43-129">-1</span><span class="sxs-lookup"><span data-stu-id="f5b43-129">-1</span></span>|  
  
10. <span data-ttu-id="f5b43-130">Nelle `Form1`, creare un gestore eventi per il <xref:System.Windows.Forms.Control.Click> eventi del `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="f5b43-130">In `Form1`, create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="f5b43-131">All'interno del gestore di evento, inserire codice simile all'esempio di codice seguente per creare e visualizzare le nuove istanze di `Form2` come finestre figlio MDI di `Form1`:</span><span class="sxs-lookup"><span data-stu-id="f5b43-131">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`:</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
  
12. <span data-ttu-id="f5b43-132">Inserire codice analogo al seguente esempio di codice nel `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f5b43-132">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5b43-133">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f5b43-133">Compiling the Code</span></span>  
 <span data-ttu-id="f5b43-134">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5b43-134">This example requires:</span></span>  
  
- <span data-ttu-id="f5b43-135">Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-135">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="f5b43-136">Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="f5b43-136">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="f5b43-137">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5b43-137">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b43-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5b43-138">See also</span></span>

- [<span data-ttu-id="f5b43-139">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="f5b43-139">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="f5b43-140">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f5b43-140">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="f5b43-141">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="f5b43-141">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
