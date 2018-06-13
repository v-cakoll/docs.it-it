---
title: 'Procedura: aggiungere elementi per il perfezionamento di ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 37843d27211bd07c2749b3e6fc14ec03d7bf570d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529720"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="d8f9e-102">Procedura: aggiungere elementi per il perfezionamento di ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="d8f9e-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="d8f9e-103">È possibile migliorare l'utilizzabilità di <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> controlli nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8f9e-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="d8f9e-104">Aggiungere segni di spunta per specificare se una funzionalità è attivata o disattivata, ad esempio se un righello viene visualizzato lungo il margine di un'applicazione di elaborazione testi, o per indicare quali file in un elenco di file sono visualizzate, ad esempio come in un **finestra** dal menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="d8f9e-105">Aggiungere le immagini per rappresentare visivamente i comandi di menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="d8f9e-106">Visualizzare i tasti di scelta rapida per fornire un'alternativa al mouse per l'esecuzione di comandi.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="d8f9e-107">Ad esempio, premere CTRL + C esegue il **copia** comando.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="d8f9e-108">Visualizzare i tasti per fornire un'alternativa al mouse per lo spostamento di menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="d8f9e-109">Ad esempio, premere ALT + F sceglie il **File** menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="d8f9e-110">Visualizzare le barre di separazione per raggruppare i comandi correlati e rendere più leggibili menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="d8f9e-111">Per visualizzare un segno di spunta in un comando di menu</span><span class="sxs-lookup"><span data-stu-id="d8f9e-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="d8f9e-112">Impostare il relativo <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="d8f9e-113">Consente inoltre di impostare il <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="d8f9e-114">Utilizzare questa procedura solo se si desidera che il comando di menu da visualizzare per impostazione predefinita, indipendentemente dal fatto se è selezionata.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="d8f9e-115">Per visualizzare un segno di spunta che modifica lo stato con ogni clic</span><span class="sxs-lookup"><span data-stu-id="d8f9e-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="d8f9e-116">Impostare il comando di menu <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="d8f9e-117">Per aggiungere un'immagine a un comando di menu</span><span class="sxs-lookup"><span data-stu-id="d8f9e-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="d8f9e-118">Impostare il comando di menu <xref:System.Windows.Forms.ToolStripItem.Image%2A> proprietà sul nome dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="d8f9e-119">Se il <xref:System.Windows.Forms.ToolStripItemDisplayStyle> di questo comando di menu è impostata su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, l'immagine non può essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8f9e-120">Margine dell'immagine può inoltre visualizzare un segno di spunta se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="d8f9e-121">Inoltre, è possibile impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà dell'immagine da `true`, e l'immagine verrà visualizzata con un bordo tratteggiato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="d8f9e-122">Per visualizzare un tasto di scelta rapida per un comando di menu</span><span class="sxs-lookup"><span data-stu-id="d8f9e-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="d8f9e-123">Impostare il comando di menu <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> proprietà per la combinazione di tasti desiderata, ad esempio CTRL + O per il **aprire** comando di menu e impostare il <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="d8f9e-124">Per visualizzare i tasti di scelta rapida personalizzati per un comando di menu</span><span class="sxs-lookup"><span data-stu-id="d8f9e-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="d8f9e-125">Impostare il comando di menu <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> proprietà per la combinazione di tasti desiderata, ad esempio CTRL + MAIUSC + O anziché MAIUSC + CTRL + O e set di <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="d8f9e-126">Per visualizzare una chiave di accesso per un comando di menu</span><span class="sxs-lookup"><span data-stu-id="d8f9e-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="d8f9e-127">Quando si imposta la <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà per il comando di menu, immettere una e commerciale (&) prima della lettera che si desidera costituirà la chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="d8f9e-128">Ad esempio, se si digita `&Open` come il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà di una voce di menu comporterà un comando di menu che viene visualizzato come **O**penna.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as **O**pen.</span></span>  
  
     <span data-ttu-id="d8f9e-129">Per passare a questo comando di menu, premere ALT per attivare il <xref:System.Windows.Forms.MenuStrip>, premere il tasto di scelta del nome del menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="d8f9e-130">Quando il menu viene aperto e visualizza gli elementi con chiavi di accesso, è sufficiente premere il tasto di scelta per selezionare il comando di menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8f9e-131">Evitare di definire i tasti di scelta duplicati, ad esempio la definizione ALT + F due volte nello stesso sistema di menu.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="d8f9e-132">Non è possibile garantire l'ordine di selezione dei tasti di scelta duplicati.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="d8f9e-133">Per visualizzare una barra di separazione tra i comandi di menu</span><span class="sxs-lookup"><span data-stu-id="d8f9e-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="d8f9e-134">Dopo aver definito il <xref:System.Windows.Forms.MenuStrip> e gli elementi che dovrà contenere, utilizzare il <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> metodo per aggiungere i comandi di menu e <xref:System.Windows.Forms.ToolStripSeparator> controlli per il <xref:System.Windows.Forms.MenuStrip> nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="d8f9e-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8f9e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8f9e-135">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="d8f9e-136">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="d8f9e-136">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
