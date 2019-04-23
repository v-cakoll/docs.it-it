---
title: Cenni preliminari sul controllo MenuStrip (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 7cd761697a09205294727043efc6cf73816803ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975598"
---
# <a name="menustrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo MenuStrip (Windows Form)
I menu che contiene i comandi che vengono raggruppati in base a un tema comune espongono funzionalità agli utenti.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo è una novità di questa versione di Visual Studio e .NET Framework. Con il controllo, è possibile creare con facilità i menu, ad esempio quelle disponibili in Microsoft Office.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo supporta l'interfaccia a documenti multipli (MDI) e unione di menu, le descrizioni comandi e overflow. È possibile migliorare l'usabilità e migliorare la leggibilità dei menu tramite l'aggiunta di chiavi di accesso, tasti di scelta rapida, segni di spunta, immagini e le barre di separazione.  
  
 Il <xref:System.Windows.Forms.MenuStrip> sostituisce e aggiunge funzionalità per il <xref:System.Windows.Forms.MainMenu> controllare; tuttavia, il <xref:System.Windows.Forms.MainMenu> controllo è stato mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se necessario.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Modi per usare il controllo MenuStrip  
 Usare il <xref:System.Windows.Forms.MenuStrip> controllo:  
  
-   Creare con facilità personalizzato, impiego frequente menu che supportano funzionalità avanzate di utente interfaccia e il layout, come testo e immagine di ordinamento e l'allineamento, operazioni di trascinamento e rilascio, MDI, overflow e modalità alternative di accedere ai comandi di menu.  
  
-   Supporta l'aspetto tipico e il comportamento del sistema operativo.  
  
-   Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo è possibile gestire gli eventi per altri controlli.  
  
 Nella tabella seguente mostra alcune proprietà particolarmente importante di <xref:System.Windows.Forms.MenuStrip> e classi associate.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ottiene o imposta il <xref:System.Windows.Forms.ToolStripMenuItem> che consente di visualizzare un elenco di form figlio MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Ottiene o imposta il modo in cui i menu figlio vengono uniti ai menu padre nelle applicazioni MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Ottiene o imposta la posizione di un elemento unito all'interno di un menu nelle applicazioni MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Ottiene o imposta un valore che indica se il form è un contenitore per form figlio MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ottiene o imposta un valore che indica se le descrizioni comandi vengono visualizzate per il <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.MenuStrip> supporta la funzionalità di overflow.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Ottiene o imposta i tasti di scelta rapida associati il <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ottiene o imposta un valore che indica se i tasti di scelta rapida sono associati i <xref:System.Windows.Forms.ToolStripMenuItem> sono visualizzati accanto al <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 La tabella seguente illustra l'importante <xref:System.Windows.Forms.MenuStrip> classi correlate.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Rappresenta un'opzione selezionabile visualizzata in una <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Viene visualizzato un menu di scelta rapida.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco che viene visualizzato quando l'utente sceglie un <xref:System.Windows.Forms.ToolStripDropDownButton> o una voce di menu di livello superiore.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Fornisce funzionalità di base per i controlli derivano da <xref:System.Windows.Forms.ToolStripItem> che visualizzano gli elementi di elenco a discesa quando si fa clic.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
