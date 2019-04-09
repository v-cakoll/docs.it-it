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
ms.openlocfilehash: 458347df7e17aabc1e9e21d66ad1b5a96200fe28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198556"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Procedura: Aggiungere elementi per il perfezionamento di ToolStripMenuItems
È possibile migliorare l'usabilità della <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> controlli nei modi seguenti:  
  
-   Aggiungere segni di spunta per specificare se una funzionalità è attivata o disattivata, ad esempio se un righello è visualizzato lungo il margine di un'applicazione di elaborazione di testo, o per indicare quali file in un elenco di file sono visualizzati, ad esempio in data una **finestra** menu di scelta.  
  
-   Aggiungere le immagini per rappresentare visivamente i comandi di menu.  
  
-   Visualizzare i tasti di scelta rapida per fornire un'alternativa al mouse per l'esecuzione di comandi. Ad esempio, se si preme CTRL + C esegue la **copia** comando.  
  
-   Visualizzare i tasti per fornire un'alternativa al mouse per la navigazione di menu. Ad esempio, premere ALT + F sceglie la **File** menu.  
  
-   Visualizzare le barre di separazione per raggruppare i comandi correlati e rendere più leggibili i menu.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Per visualizzare un segno di spunta su un comando di menu  
  
-   Impostare relativi <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà `true`.  
  
     Questo imposta anche il <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> proprietà `true`. Utilizzare questa procedura solo se si desidera che il comando di menu da visualizzare per impostazione predefinita, indipendentemente dal fatto che è selezionato.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Per visualizzare un segno di spunta che modifica lo stato con ogni clic  
  
-   Impostare il comando di menu <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà `true`.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Per aggiungere un'immagine a un comando di menu  
  
-   Impostare il comando di menu <xref:System.Windows.Forms.ToolStripItem.Image%2A> proprietà sul nome dell'immagine. Se il <xref:System.Windows.Forms.ToolStripItemDisplayStyle> di questo comando di menu è impostata su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, l'immagine non può essere visualizzata.  
  
> [!NOTE]
>  Il margine dell'immagine può anche visualizzare un segno di spunta se si desidera. Inoltre, è possibile impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà dell'immagine da `true`, e l'immagine verrà visualizzata con un bordo tratteggiato intorno a esso in fase di esecuzione.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Per visualizzare un tasto di scelta rapida per un comando di menu  
  
-   Impostare il comando di menu <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> proprietà per la combinazione della tastiera desiderato, ad esempio CTRL + O per il **Open** comando di menu e impostare il <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà `true`.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Per visualizzare i tasti di scelta rapida personalizzato per un comando di menu  
  
-   Impostare il comando di menu <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> proprietà per la combinazione della tastiera desiderato, ad esempio CTRL + MAIUSC + O anziché MAIUSC + CTRL + O e set di <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> proprietà `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Per visualizzare una chiave di accesso per un comando di menu  
  
-   Quando si imposta il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà per il comando di menu, immettere una e commerciale (&) davanti alla lettera che si desidera costituirà la chiave di accesso. Ad esempio, se si digita `&Open` come il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà di una voce di menu comporterà un comando di menu che viene visualizzato come <u>O</u>penna.
  
     Per spostarsi in questo comando di menu, premere ALT per attivare il <xref:System.Windows.Forms.MenuStrip>, premere il tasto di scelta del nome del menu. Quando il menu si apre e visualizza gli elementi con chiavi di accesso, è sufficiente premere il tasto di scelta per selezionare il comando di menu.  
  
> [!NOTE]
>  Evitare di definire tasti di scelta duplicati, ad esempio la definizione ALT + F due volte nello stesso sistema di menu. Non è possibile garantire l'ordine di selezione delle chiavi di accesso duplicati.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Per visualizzare una barra di separazione tra i comandi di menu  
  
-   Dopo aver definito i <xref:System.Windows.Forms.MenuStrip> e gli elementi che dovrà contenere, usare il <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> per aggiungere i comandi di menu e <xref:System.Windows.Forms.ToolStripSeparator> controlli al <xref:System.Windows.Forms.MenuStrip> nell'ordine desiderato.  
  
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
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)
