---
title: 'Procedura: Creare un elenco di finestre MDI con MenuStrip (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: 229afc879be6407340e2fca6c3b2474475bcb5a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611962"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="537aa-102">Procedura: Creare un elenco di finestre MDI con MenuStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="537aa-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="537aa-103">Usare l'interfaccia a documenti multipli (MDI) per creare applicazioni che possono aprire i documenti diverse alla stessa ora e copia e Incolla il contenuto da un documento a altro.</span><span class="sxs-lookup"><span data-stu-id="537aa-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="537aa-104">Questa procedura illustra come creare un elenco di tutti i form figlio attivo nel menu finestra dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="537aa-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="537aa-105">Per creare un elenco di finestre MDI con MenuStrip</span><span class="sxs-lookup"><span data-stu-id="537aa-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="537aa-106">Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="537aa-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="537aa-107">Aggiungere un tipo <xref:System.Windows.Forms.MenuStrip> al form.</span><span class="sxs-lookup"><span data-stu-id="537aa-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="537aa-108">Aggiungere due voci di menu di primo livello per il <xref:System.Windows.Forms.MenuStrip> e impostare loro <xref:System.Windows.Forms.Control.Text%2A> delle proprietà per `&File` e `&Window`.</span><span class="sxs-lookup"><span data-stu-id="537aa-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="537aa-109">Aggiungere una voce del sottomenu alla voce di menu `&File` e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Open`.</span><span class="sxs-lookup"><span data-stu-id="537aa-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="537aa-110">Impostare il <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà del <xref:System.Windows.Forms.MenuStrip> per il `&Window` <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="537aa-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="537aa-111">Aggiungere un modulo al progetto e aggiungere il controllo desiderato, ad esempio un'altra <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="537aa-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="537aa-112">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="537aa-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="537aa-113">All'interno del gestore di evento, inserire codice simile al seguente per creare e visualizzare le nuove istanze di `Form2` come finestre figlio MDI di `Form1`.</span><span class="sxs-lookup"><span data-stu-id="537aa-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="537aa-114">Inserire codice simile al seguente nel `&New` <xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="537aa-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="537aa-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="537aa-115">Compiling the Code</span></span>  
 <span data-ttu-id="537aa-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="537aa-116">This example requires:</span></span>  
  
- <span data-ttu-id="537aa-117">Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.</span><span class="sxs-lookup"><span data-stu-id="537aa-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="537aa-118">Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="537aa-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="537aa-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="537aa-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537aa-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="537aa-120">See also</span></span>

- [<span data-ttu-id="537aa-121">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="537aa-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="537aa-122">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="537aa-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="537aa-123">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="537aa-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
