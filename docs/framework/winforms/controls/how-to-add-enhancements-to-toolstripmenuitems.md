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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Procedura: aggiungere elementi per il perfezionamento di ToolStripMenuItems
È possibile migliorare l'usabilità e <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> i controlli nei seguenti modi:  
  
- Aggiungere segni di spunta per indicare se una funzione è attivata o disattivata, ad esempio se un righello viene visualizzato lungo il margine di un'applicazione di elaborazione testi o per indicare quale file in un elenco di file viene visualizzato, ad esempio in un menu **Finestra.**  
  
- Aggiungere immagini che rappresentano visivamente i comandi di menu.  
  
- Visualizzare i tasti di scelta rapida per fornire un'alternativa da tastiera al mouse per l'esecuzione di comandi. Ad esempio, se si preme CTRL e C viene eseguito il comando **Copia.**  
  
- Visualizzare i tasti di scelta per fornire un'alternativa da tastiera al mouse per la navigazione nei menu. Ad esempio, se si preme ALT e F viene scelto il menu **File.**  
  
- Mostra le barre di separazione per raggruppare i comandi correlati e rendere i menu più leggibili.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Per visualizzare un segno di spunta in un comando di menu  
  
- Impostarne <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> la `true`proprietà su .  
  
     In questo <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> modo `true`la proprietà viene impostata su . Utilizzare questa procedura solo se si desidera che il comando di menu venga visualizzato come selezionato per impostazione predefinita, indipendentemente dal fatto che sia selezionato.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Per visualizzare un segno di spunta che cambia stato con ogni clic  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> del `true`comando di menu su .  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Per aggiungere un'immagine a un comando di menu  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Image%2A> del comando di menu sul nome dell'immagine. Se <xref:System.Windows.Forms.ToolStripItemDisplayStyle> la proprietà di questo <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> comando <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>di menu è impostata su o , l'immagine non può essere visualizzata.  
  
> [!NOTE]
> Il margine dell'immagine può anche mostrare un segno di spunta se lo si desidera. Inoltre, è possibile <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> impostare la `true`proprietà dell'immagine su e l'immagine verrà visualizzata con un bordo tratteggiato intorno ad essa in fase di esecuzione.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Per visualizzare un tasto di scelta rapida per un comando di menu  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando di menu sulla combinazione di tasti desiderata, ad <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> esempio `true`CTRL-O per il comando di menu **Apri,** e la proprietà su .  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Per visualizzare i tasti di scelta rapida personalizzati per un comando di menu  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> del comando di menu sulla combinazione di tasti desiderata, ad esempio CTRL-MAIUSC-O anziché MAIUSC, CTRL e O, e impostare la <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà su . `true`  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Per visualizzare un tasto di scelta per un comando di menuTo display an access key for a menu command  
  
- Quando si <xref:System.Windows.Forms.ToolStripItem.Text%2A> imposta la proprietà per il comando di menu, immettere una e commerciale (&) prima della lettera che si desidera sottolineare come tasto di scelta. Ad esempio, `&Open` digitando <xref:System.Windows.Forms.ToolStripItem.Text%2A> come proprietà di una voce di menu verrà visualizzato un comando di menu che viene visualizzato come <u>O</u>pen.
  
     Per passare a questo comando di menu, <xref:System.Windows.Forms.MenuStrip>premere ALT per assegnare lo stato attivo a , quindi premere il tasto di scelta del nome del menu. Quando il menu si apre e mostra gli elementi con i tasti di scelta, è sufficiente premere il tasto di scelta per selezionare il comando di menu.  
  
> [!NOTE]
> Evitare di definire due volte i tasti di scelta duplicati, ad esempio definendo due volte ALT-F nello stesso sistema di menu. L'ordine di selezione dei tasti di scelta duplicati non può essere garantito.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Per visualizzare una barra di separazione tra i comandi di menu  
  
- Dopo aver <xref:System.Windows.Forms.MenuStrip> definito l'utente e gli <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> elementi che conterrà, <xref:System.Windows.Forms.ToolStripSeparator> utilizzare <xref:System.Windows.Forms.MenuStrip> il metodo o per aggiungere i comandi di menu e i controlli all'ordine desiderato.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Cenni preliminari sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)
