---
title: Cenni preliminari sul controllo MenuStrip (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 46a3a25415db77ee261f5fb1c3bf114b2275a2d4
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733450"
---
# <a name="menustrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo MenuStrip (Windows Form)
I menu espongono le funzionalità agli utenti con i comandi raggruppati in base a un tema comune.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo è stato introdotto nella versione 2,0 del .NET Framework. Con il <xref:System.Windows.Forms.MenuStrip> controllo è possibile creare facilmente menu come quelli disponibili in Microsoft Office.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo supporta l'interfaccia a documenti multipli (MDI) e l'Unione di menu, le descrizioni comandi e l'overflow. È possibile migliorare l'usabilità e la leggibilità dei menu aggiungendo chiavi di accesso, tasti di scelta rapida, segni di spunta, immagini e barre dei separatori.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo sostituisce e aggiunge funzionalità <xref:System.Windows.Forms.MainMenu> al controllo; tuttavia, il <xref:System.Windows.Forms.MainMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se lo si sceglie.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Modalità di utilizzo del controllo MenuStrip  
 Usare il <xref:System.Windows.Forms.MenuStrip> controllo per:  
  
- Consente di creare menu facilmente personalizzati e di uso comune che supportano funzionalità avanzate di interfaccia utente e layout, ad esempio ordinamento e allineamento di testo e immagini, operazioni di trascinamento della selezione, MDI, overflow e modalità alternative di accesso ai comandi di menu.  
  
- Supportare l'aspetto e il comportamento tipici del sistema operativo.  
  
- Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo in cui si gestiscono gli eventi per altri controlli.  
  
 Nella tabella seguente vengono illustrate alcune proprietà particolarmente <xref:System.Windows.Forms.MenuStrip> importanti di e delle classi associate.  
  
|Proprietà|DESCRIZIONE|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ottiene o imposta l' <xref:System.Windows.Forms.ToolStripMenuItem> oggetto utilizzato per visualizzare un elenco di form figlio MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Ottiene o imposta il modo in cui i menu figlio vengono uniti ai menu padre nelle applicazioni MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Ottiene o imposta la posizione di un elemento unito all'interno di un menu in applicazioni MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Ottiene o imposta un valore che indica se il form è un contenitore per form figlio MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ottiene o imposta un valore che indica se vengono visualizzate le <xref:System.Windows.Forms.MenuStrip>descrizioni comandi per.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.MenuStrip> supporta la funzionalità di overflow.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Ottiene o imposta i tasti di scelta rapida associati <xref:System.Windows.Forms.ToolStripMenuItem>a.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ottiene o imposta un valore che indica se i tasti di scelta rapida associati a <xref:System.Windows.Forms.ToolStripMenuItem> sono visualizzati accanto <xref:System.Windows.Forms.ToolStripMenuItem>a.|  
  
 Nella tabella seguente vengono illustrate <xref:System.Windows.Forms.MenuStrip> le principali classi complementari.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Rappresenta un'opzione selezionabile visualizzata in un <xref:System.Windows.Forms.MenuStrip> oggetto <xref:System.Windows.Forms.ContextMenuStrip>o.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Viene visualizzato un menu di scelta rapida.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco visualizzato quando l'utente fa clic su <xref:System.Windows.Forms.ToolStripDropDownButton> o su una voce di menu di livello superiore.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Fornisce la funzionalità di base per i <xref:System.Windows.Forms.ToolStripItem> controlli derivati da che visualizzano gli elementi a discesa quando vengono selezionate.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
