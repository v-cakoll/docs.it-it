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
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182329"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="7ae95-102">Procedura: aggiungere elementi per il perfezionamento di ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="7ae95-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="7ae95-103">È possibile migliorare l'usabilità e <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> i controlli nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="7ae95-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="7ae95-104">Aggiungere segni di spunta per indicare se una funzione è attivata o disattivata, ad esempio se un righello viene visualizzato lungo il margine di un'applicazione di elaborazione testi o per indicare quale file in un elenco di file viene visualizzato, ad esempio in un menu **Finestra.**</span><span class="sxs-lookup"><span data-stu-id="7ae95-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="7ae95-105">Aggiungere immagini che rappresentano visivamente i comandi di menu.</span><span class="sxs-lookup"><span data-stu-id="7ae95-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="7ae95-106">Visualizzare i tasti di scelta rapida per fornire un'alternativa da tastiera al mouse per l'esecuzione di comandi.</span><span class="sxs-lookup"><span data-stu-id="7ae95-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="7ae95-107">Ad esempio, se si preme CTRL e C viene eseguito il comando **Copia.**</span><span class="sxs-lookup"><span data-stu-id="7ae95-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="7ae95-108">Visualizzare i tasti di scelta per fornire un'alternativa da tastiera al mouse per la navigazione nei menu.</span><span class="sxs-lookup"><span data-stu-id="7ae95-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="7ae95-109">Ad esempio, se si preme ALT e F viene scelto il menu **File.**</span><span class="sxs-lookup"><span data-stu-id="7ae95-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="7ae95-110">Mostra le barre di separazione per raggruppare i comandi correlati e rendere i menu più leggibili.</span><span class="sxs-lookup"><span data-stu-id="7ae95-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="7ae95-111">Per visualizzare un segno di spunta in un comando di menu</span><span class="sxs-lookup"><span data-stu-id="7ae95-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="7ae95-112">Impostarne <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> la `true`proprietà su .</span><span class="sxs-lookup"><span data-stu-id="7ae95-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="7ae95-113">In questo <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> modo `true`la proprietà viene impostata su .</span><span class="sxs-lookup"><span data-stu-id="7ae95-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="7ae95-114">Utilizzare questa procedura solo se si desidera che il comando di menu venga visualizzato come selezionato per impostazione predefinita, indipendentemente dal fatto che sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="7ae95-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="7ae95-115">Per visualizzare un segno di spunta che cambia stato con ogni clic</span><span class="sxs-lookup"><span data-stu-id="7ae95-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="7ae95-116">Impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> del `true`comando di menu su .</span><span class="sxs-lookup"><span data-stu-id="7ae95-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="7ae95-117">Per aggiungere un'immagine a un comando di menu</span><span class="sxs-lookup"><span data-stu-id="7ae95-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="7ae95-118">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Image%2A> del comando di menu sul nome dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="7ae95-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="7ae95-119">Se <xref:System.Windows.Forms.ToolStripItemDisplayStyle> la proprietà di questo <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> comando <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>di menu è impostata su o , l'immagine non può essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="7ae95-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ae95-120">Il margine dell'immagine può anche mostrare un segno di spunta se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="7ae95-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="7ae95-121">Inoltre, è possibile <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> impostare la `true`proprietà dell'immagine su e l'immagine verrà visualizzata con un bordo tratteggiato intorno ad essa in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7ae95-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="7ae95-122">Per visualizzare un tasto di scelta rapida per un comando di menu</span><span class="sxs-lookup"><span data-stu-id="7ae95-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="7ae95-123">Impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando di menu sulla combinazione di tasti desiderata, ad <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> esempio `true`CTRL-O per il comando di menu **Apri,** e la proprietà su .</span><span class="sxs-lookup"><span data-stu-id="7ae95-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="7ae95-124">Per visualizzare i tasti di scelta rapida personalizzati per un comando di menu</span><span class="sxs-lookup"><span data-stu-id="7ae95-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="7ae95-125">Impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> del comando di menu sulla combinazione di tasti desiderata, ad esempio CTRL-MAIUSC-O anziché MAIUSC, CTRL e O, e impostare la <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà su . `true`</span><span class="sxs-lookup"><span data-stu-id="7ae95-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="7ae95-126">Per visualizzare un tasto di scelta per un comando di menuTo display an access key for a menu command</span><span class="sxs-lookup"><span data-stu-id="7ae95-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="7ae95-127">Quando si <xref:System.Windows.Forms.ToolStripItem.Text%2A> imposta la proprietà per il comando di menu, immettere una e commerciale (&) prima della lettera che si desidera sottolineare come tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="7ae95-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="7ae95-128">Ad esempio, `&Open` digitando <xref:System.Windows.Forms.ToolStripItem.Text%2A> come proprietà di una voce di menu verrà visualizzato un comando di menu che viene visualizzato come <u>O</u>pen.</span><span class="sxs-lookup"><span data-stu-id="7ae95-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="7ae95-129">Per passare a questo comando di menu, <xref:System.Windows.Forms.MenuStrip>premere ALT per assegnare lo stato attivo a , quindi premere il tasto di scelta del nome del menu.</span><span class="sxs-lookup"><span data-stu-id="7ae95-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="7ae95-130">Quando il menu si apre e mostra gli elementi con i tasti di scelta, è sufficiente premere il tasto di scelta per selezionare il comando di menu.</span><span class="sxs-lookup"><span data-stu-id="7ae95-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ae95-131">Evitare di definire due volte i tasti di scelta duplicati, ad esempio definendo due volte ALT-F nello stesso sistema di menu.</span><span class="sxs-lookup"><span data-stu-id="7ae95-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="7ae95-132">L'ordine di selezione dei tasti di scelta duplicati non può essere garantito.</span><span class="sxs-lookup"><span data-stu-id="7ae95-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="7ae95-133">Per visualizzare una barra di separazione tra i comandi di menu</span><span class="sxs-lookup"><span data-stu-id="7ae95-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="7ae95-134">Dopo aver <xref:System.Windows.Forms.MenuStrip> definito l'utente e gli <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> elementi che conterrà, <xref:System.Windows.Forms.ToolStripSeparator> utilizzare <xref:System.Windows.Forms.MenuStrip> il metodo o per aggiungere i comandi di menu e i controlli all'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="7ae95-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7ae95-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ae95-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="7ae95-136">Cenni preliminari sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="7ae95-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
