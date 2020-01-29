---
title: 'Procedura: inserire un MenuStrip in un menu a discesa MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736410"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="a178f-102">Procedura: inserire un MenuStrip in un menu a discesa MDI (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="a178f-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="a178f-103">In alcune applicazioni, il tipo di una finestra figlio di interfaccia a documenti multipli (MDI, Multiple Document Interface) può essere diverso dalla finestra padre MDI.</span><span class="sxs-lookup"><span data-stu-id="a178f-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="a178f-104">Ad esempio, il padre MDI potrebbe essere un foglio di calcolo, mentre il figlio MDI potrebbe essere un grafico.</span><span class="sxs-lookup"><span data-stu-id="a178f-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="a178f-105">In tal caso, è consigliabile aggiornare il contenuto del menu del padre MDI con il contenuto del menu del figlio MDI in quanto vengono attivate finestre figlio MDI di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="a178f-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="a178f-106">Nella procedura seguente vengono utilizzate le proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> per inserire un gruppo di voci di menu dal menu figlio MDI nella parte a discesa del menu MDI padre.</span><span class="sxs-lookup"><span data-stu-id="a178f-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="a178f-107">Chiudendo la finestra figlio MDI vengono rimosse le voci di menu inserite dall'elemento padre MDI.</span><span class="sxs-lookup"><span data-stu-id="a178f-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="a178f-108">Per inserire un MenuStrip in un menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="a178f-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="a178f-109">Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a178f-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="a178f-110">Aggiungere <xref:System.Windows.Forms.MenuStrip> a `Form1` e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> di <xref:System.Windows.Forms.MenuStrip> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a178f-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="a178f-111">Aggiungere una voce di menu di primo livello a `Form1`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.Control.Text%2A> su `&File`.</span><span class="sxs-lookup"><span data-stu-id="a178f-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="a178f-112">Aggiungere tre voci di sottomenu alla voce di menu `&File` e impostare le relative proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Open`, `&Import from`e `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="a178f-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="a178f-113">Aggiungere due voci di sottomenu alla voce di sottomenu `&Import from` e impostare le relative proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Word` e `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="a178f-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="a178f-114">Aggiungere un form al progetto, aggiungere <xref:System.Windows.Forms.MenuStrip> al form e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> del `Form2`<xref:System.Windows.Forms.MenuStrip> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a178f-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="a178f-115">Aggiungere una voce di menu di primo livello a `Form2`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&File`.</span><span class="sxs-lookup"><span data-stu-id="a178f-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="a178f-116">Aggiungere voci di sottomenu al menu `&File` di `Form2` nell'ordine seguente: un <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`e un altro <xref:System.Windows.Forms.ToolStripSeparator>.</span><span class="sxs-lookup"><span data-stu-id="a178f-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="a178f-117">Impostare le proprietà <xref:System.Windows.Forms.MergeAction> e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> delle voci di menu `Form2` come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a178f-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a178f-118">Voce di menu Form2</span><span class="sxs-lookup"><span data-stu-id="a178f-118">Form2 menu item</span></span>|<span data-ttu-id="a178f-119">Valore MergeAction</span><span class="sxs-lookup"><span data-stu-id="a178f-119">MergeAction value</span></span>|<span data-ttu-id="a178f-120">Valore MergeIndex</span><span class="sxs-lookup"><span data-stu-id="a178f-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="a178f-121">File</span><span class="sxs-lookup"><span data-stu-id="a178f-121">File</span></span>|<span data-ttu-id="a178f-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="a178f-122">MatchOnly</span></span>|<span data-ttu-id="a178f-123">-1</span><span class="sxs-lookup"><span data-stu-id="a178f-123">-1</span></span>|  
    |<span data-ttu-id="a178f-124">Separator</span><span class="sxs-lookup"><span data-stu-id="a178f-124">Separator</span></span>|<span data-ttu-id="a178f-125">INS</span><span class="sxs-lookup"><span data-stu-id="a178f-125">Insert</span></span>|<span data-ttu-id="a178f-126">2</span><span class="sxs-lookup"><span data-stu-id="a178f-126">2</span></span>|  
    |<span data-ttu-id="a178f-127">Salva</span><span class="sxs-lookup"><span data-stu-id="a178f-127">Save</span></span>|<span data-ttu-id="a178f-128">INS</span><span class="sxs-lookup"><span data-stu-id="a178f-128">Insert</span></span>|<span data-ttu-id="a178f-129">3\.</span><span class="sxs-lookup"><span data-stu-id="a178f-129">3</span></span>|  
    |<span data-ttu-id="a178f-130">Salva e chiudi</span><span class="sxs-lookup"><span data-stu-id="a178f-130">Save and Close</span></span>|<span data-ttu-id="a178f-131">INS</span><span class="sxs-lookup"><span data-stu-id="a178f-131">Insert</span></span>|<span data-ttu-id="a178f-132">4</span><span class="sxs-lookup"><span data-stu-id="a178f-132">4</span></span>|  
    |<span data-ttu-id="a178f-133">Separator</span><span class="sxs-lookup"><span data-stu-id="a178f-133">Separator</span></span>|<span data-ttu-id="a178f-134">INS</span><span class="sxs-lookup"><span data-stu-id="a178f-134">Insert</span></span>|<span data-ttu-id="a178f-135">5</span><span class="sxs-lookup"><span data-stu-id="a178f-135">5</span></span>|  
  
10. <span data-ttu-id="a178f-136">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="a178f-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="a178f-137">Nel gestore eventi inserire codice simile all'esempio di codice riportato di seguito per creare e visualizzare nuove istanze di `Form2` come finestre figlio MDI di `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a178f-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
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
  
12. <span data-ttu-id="a178f-138">Inserire codice analogo al seguente esempio di codice nel `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a178f-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a178f-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a178f-139">Compiling the Code</span></span>  
 <span data-ttu-id="a178f-140">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a178f-140">This example requires:</span></span>  
  
- <span data-ttu-id="a178f-141">Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.</span><span class="sxs-lookup"><span data-stu-id="a178f-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="a178f-142">Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="a178f-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="a178f-143">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a178f-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a178f-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a178f-144">See also</span></span>

- [<span data-ttu-id="a178f-145">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="a178f-145">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="a178f-146">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="a178f-146">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="a178f-147">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="a178f-147">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
