---
title: 'Procedura: Aggiungere elementi per il perfezionamento di ToolStripMenuItems'
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
ms.openlocfilehash: 9e95c3623bf9bad8395f586392a0557ad1cde880
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912577"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Procedura: Aggiungere elementi per il perfezionamento di ToolStripMenuItems
È possibile migliorare l'usabilità dei <xref:System.Windows.Forms.MenuStrip> controlli <xref:System.Windows.Forms.ContextMenuStrip> e nei modi seguenti:  
  
- Aggiungere segni di spunta per indicare se una funzionalità viene attivata o disattivata, ad esempio se un righello viene visualizzato lungo il margine di un'applicazione di elaborazione di testo o per indicare quale file in un elenco di file viene visualizzato, ad esempio in un menu **finestra** .  
  
- Aggiungere immagini che rappresentano visivamente i comandi di menu.  
  
- Visualizzare i tasti di scelta rapida per fornire un'alternativa da tastiera al mouse per l'esecuzione di comandi. Ad esempio, se si preme CTRL + C viene eseguito il comando **Copy** .  
  
- Consente di visualizzare le chiavi di accesso per fornire un'alternativa da tastiera al mouse per la navigazione dei menu. Se ad esempio si preme ALT + F, scegliere il menu **file** .  
  
- Mostra barre di separazione per raggruppare i comandi correlati e rendere più leggibili i menu.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Per visualizzare un segno di spunta su un comando di menu  
  
- Impostare la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> relativa proprietà `true`su.  
  
     Viene inoltre impostata la <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> proprietà su `true`. Usare questa procedura solo se si vuole che il comando di menu venga visualizzato come selezionato per impostazione predefinita, indipendentemente dal fatto che sia selezionato.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Per visualizzare un segno di spunta che modifica lo stato con ogni clic  
  
- Impostare la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà del comando di menu `true`su.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Per aggiungere un'immagine a un comando di menu  
  
- Impostare la <xref:System.Windows.Forms.ToolStripItem.Image%2A> proprietà del comando di menu sul nome dell'immagine. Se la <xref:System.Windows.Forms.ToolStripItemDisplayStyle> proprietà di questo comando di menu è impostata <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>o, l'immagine non può essere visualizzata.  
  
> [!NOTE]
> Il margine dell'immagine può inoltre mostrare un segno di spunta se si sceglie. Inoltre, è possibile impostare la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà dell'immagine su `true`e l'immagine verrà visualizzata con un bordo tratteggiato in fase di esecuzione.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Per visualizzare un tasto di scelta rapida per un comando di menu  
  
- Impostare la <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> proprietà del comando di menu sulla combinazione di tasti desiderata, ad esempio CTRL + O per il comando di menu **Apri** e impostare <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> la proprietà `true`su.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Per visualizzare i tasti di scelta rapida personalizzati per un comando di menu  
  
- Impostare la <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> proprietà del comando di menu sulla combinazione di tasti desiderata, ad esempio CTRL + MAIUSC + o anziché MAIUSC + CTRL + o e impostare la <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà su `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Per visualizzare una chiave di accesso per un comando di menu  
  
- Quando si imposta la <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà per il comando di menu, immettere una e commerciale (&) prima della lettera che si desidera sottolineare come chiave di accesso. Se ad esempio si `&Open` digita come proprietàdiunavocedimenu,verràvisualizzatouncomandodimenuchevienevisualizzatocomeOPen.<xref:System.Windows.Forms.ToolStripItem.Text%2A> <u></u>
  
     Per passare a questo comando di menu, premere ALT per spostare lo <xref:System.Windows.Forms.MenuStrip>stato attivo su e premere il tasto di scelta del nome del menu. Quando si apre il menu e visualizza gli elementi con chiavi di accesso, è sufficiente premere il tasto di scelta per selezionare il comando di menu.  
  
> [!NOTE]
> Evitare di definire chiavi di accesso duplicate, ad esempio la definizione di ALT + F due volte nello stesso sistema di menu. Non è possibile garantire l'ordine di selezione delle chiavi di accesso duplicate.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Per visualizzare una barra di separazione tra i comandi di menu  
  
- Dopo <xref:System.Windows.Forms.MenuStrip> aver definito l'oggetto e gli elementi che conterranno, utilizzare <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> il <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> metodo o per <xref:System.Windows.Forms.MenuStrip> aggiungere i comandi di <xref:System.Windows.Forms.ToolStripSeparator> menu e i controlli a nell'ordine desiderato.  
  
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
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)
